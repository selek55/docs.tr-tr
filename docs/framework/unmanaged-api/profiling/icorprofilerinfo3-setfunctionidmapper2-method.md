---
title: "ICorProfilerInfo3::SetFunctionIDMapper2 Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: adc23b8774737f9884ded7ec1e3a891ed8b63b2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="911b7-102">ICorProfilerInfo3::SetFunctionIDMapper2 Yöntemi</span><span class="sxs-lookup"><span data-stu-id="911b7-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="911b7-103">Eşlenecek adlı profil oluşturucu uygulanan işlevini belirten `FunctionID` değerleri profil oluşturucu için 's geçirilen alternatif değerler için giriş/çıkış kancaları işlev.</span><span class="sxs-lookup"><span data-stu-id="911b7-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="911b7-104">Bu yöntemin genişlettiği [Icorprofilerınfo::setfunctionıdmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) yöntemi profil oluşturucular çalışma zamanları arasında belirsizliğini ortadan kaldırmak için kullanabilir ek veri parametreye sahip.</span><span class="sxs-lookup"><span data-stu-id="911b7-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911b7-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="911b7-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="911b7-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="911b7-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="911b7-107">[in] Bir işaretçi bir [Functionıdmapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) eşlemek için adlı uygulama `FunctionID` alternatif değerlerine değerleri.</span><span class="sxs-lookup"><span data-stu-id="911b7-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="911b7-108">[in] Her geçirilen bir işaretçi [Functionıdmapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) işlev çağrısı geçerli çalışma zamanı tarafından yapılır.</span><span class="sxs-lookup"><span data-stu-id="911b7-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="911b7-109">Profil Oluşturucu çalışma zamanları arasında belirsizliğini ortadan kaldırmak için bu bilgileri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="911b7-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="911b7-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="911b7-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="911b7-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="911b7-111">Remarks</span></span>  
 <span data-ttu-id="911b7-112">Profil Oluşturucu'nın işlevi giriş/çıkış kancaları alternatifleri FunctionID değerleri geçirilir ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), ve [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; veya [Functionenter3withınfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [Functionleave3withınfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), ve [Functiontailcall3withınfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) tarafından belirtilen [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) veya [Setenterleavefunctionhooks3withınfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="911b7-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="911b7-113">`FunctionIDMapper2` Yöntemi yalnızca bir kez ayarlanabilir; bunu ayarladığınız öneririz [Icorprofilercallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="911b7-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911b7-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="911b7-114">Requirements</span></span>  
 <span data-ttu-id="911b7-115">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="911b7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911b7-116">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="911b7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="911b7-117">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="911b7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="911b7-118">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911b7-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="911b7-119">See Also</span></span>  
 [<span data-ttu-id="911b7-120">Setfunctionıdmapper</span><span class="sxs-lookup"><span data-stu-id="911b7-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="911b7-121">Icorprofilerınfo3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="911b7-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="911b7-122">Profil oluşturma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="911b7-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="911b7-123">Profil oluşturma</span><span class="sxs-lookup"><span data-stu-id="911b7-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)