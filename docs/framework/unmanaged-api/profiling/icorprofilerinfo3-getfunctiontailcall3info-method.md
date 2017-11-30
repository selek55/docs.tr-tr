---
title: ICorProfilerInfo3::GetFunctionTailcall3Info Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aae55a9e183c9e013603218ba217be79b2425e46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="43aa6-102">ICorProfilerInfo3::GetFunctionTailcall3Info Metodu</span><span class="sxs-lookup"><span data-stu-id="43aa6-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="43aa6-103">Yığın çerçevesi için Profil Oluşturucu tarafından bildirilen işlevinin sağlar [Functiontailcall3withınfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="43aa6-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="43aa6-104">Bu yöntem yalnızca sırasında çağrılabilir `FunctionTailcall3WithInfo` geri çağırma.</span><span class="sxs-lookup"><span data-stu-id="43aa6-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43aa6-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="43aa6-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43aa6-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="43aa6-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="43aa6-107">[in] `FunctionID` İşlevinin döndürüyor.</span><span class="sxs-lookup"><span data-stu-id="43aa6-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="43aa6-108">[in] Verilen yığın çerçevesi ilgili bilgileri temsil eder donuk işleci.</span><span class="sxs-lookup"><span data-stu-id="43aa6-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="43aa6-109">Profil Oluşturucu aynı sağlamalıdır `eltInfo` , verilen Profil Oluşturucu tarafından için `FunctionTailcall3WithInfo` işlevi.</span><span class="sxs-lookup"><span data-stu-id="43aa6-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="43aa6-110">[out] Verilen yığın çerçevesi genel türler bilgilerini temsil eden bir donuk tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="43aa6-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="43aa6-111">Bu işleme yalnızca sırasında geçerli `FunctionTailcall3WithInfo` profil oluşturucu çağırıldığı geri çağırma `GetFunctionTailcall3Info` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="43aa6-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43aa6-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="43aa6-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43aa6-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="43aa6-113">Requirements</span></span>  
 <span data-ttu-id="43aa6-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43aa6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43aa6-115">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43aa6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43aa6-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43aa6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43aa6-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43aa6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43aa6-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="43aa6-118">See Also</span></span>  
 [<span data-ttu-id="43aa6-119">Functionenter3withınfo</span><span class="sxs-lookup"><span data-stu-id="43aa6-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="43aa6-120">Functionleave3withınfo</span><span class="sxs-lookup"><span data-stu-id="43aa6-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="43aa6-121">Functiontailcall3withınfo</span><span class="sxs-lookup"><span data-stu-id="43aa6-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="43aa6-122">Icorprofilerınfo3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="43aa6-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="43aa6-123">Profil oluşturma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="43aa6-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="43aa6-124">Profil oluşturma</span><span class="sxs-lookup"><span data-stu-id="43aa6-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)