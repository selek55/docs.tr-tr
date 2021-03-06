---
title: "ICorProfilerInfo::SetEnterLeaveFunctionHooks Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e41fdf02f299d118fce025e2a5a3314feb134971
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks Yöntemi
Profil Oluşturucu uygulanan işlevler "girin", "bırakın" ve "tailcall" kancaları yönetilen işlevlerin çağrılacak belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pFuncEnter`  
 [in] Bir işaretçi olarak kullanılacak uygulama [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) geri çağırma.  
  
 `pFuncLeave`  
 [in] Bir işaretçi olarak kullanılacak uygulama [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) geri çağırma.  
  
 `pFuncTailcall`  
 [in] Bir işaretçi olarak kullanılacak uygulama [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) geri çağırma.  
  
## <a name="remarks"></a>Açıklamalar  
 .NET Framework sürüm 1.0, her işlev işaretçisi karşılık gelen geri aramanın devre dışı bırakmak için null olabilir.  
  
 Geri aramalar yalnızca bir dizi aynı anda etkin olabilir. Bu nedenle, bir profil oluşturucu her ikisi de çağırırsa `SetEnterLeaveFunctionHooks` ve [Icorprofilerınfo2::setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), ardından `SetEnterLeaveFunctionHooks2` önceliklidir.  
  
 `SetEnterLeaveFunctionHooks` Yöntemi yalnızca profil oluşturucu 's çağrılabilir [Icorprofilercallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) geri çağırma.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
