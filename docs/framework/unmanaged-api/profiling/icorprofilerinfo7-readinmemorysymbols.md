---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type: COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9ada9f629c3a3c3d8b7c32ebc180c4788b6f6d3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="f4d21-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="f4d21-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="f4d21-103">[Desteklenen [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] ve sonraki sürümlerinde]</span><span class="sxs-lookup"><span data-stu-id="f4d21-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="f4d21-104">Bayt bir bellek içi simgesi akıştan okur.</span><span class="sxs-lookup"><span data-stu-id="f4d21-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d21-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="f4d21-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4d21-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="f4d21-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f4d21-107">[in] Bellek içi akış içeren modül tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="f4d21-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="f4d21-108">[in] Başlatılacağı bayt okuma bellek içi akışındaki uzaklığı.</span><span class="sxs-lookup"><span data-stu-id="f4d21-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="f4d21-109">[out] Veri kopyalanacak arabellek için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="f4d21-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="f4d21-110">Arabellek olmalıdır `countSymbolBytes` alanı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f4d21-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="f4d21-111">[in] Kopyalanacak bayt sayısı.</span><span class="sxs-lookup"><span data-stu-id="f4d21-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="f4d21-112">[out] Yöntem döndüğünde, gerçek okunan bayt sayısını içerir.</span><span class="sxs-lookup"><span data-stu-id="f4d21-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4d21-113">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="f4d21-113">Return Value</span></span>  
 <span data-ttu-id="f4d21-114">`S_OK`, sıfır olmayan bir bayt sayısı okuyorsanız.</span><span class="sxs-lookup"><span data-stu-id="f4d21-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="f4d21-115">`CORPROF_E_MODULE_IS_DYNAMIC`, modül kullanarak oluşturduysanız <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="f4d21-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4d21-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f4d21-116">Remarks</span></span>  
 <span data-ttu-id="f4d21-117">`ReadInMemorySymbols` Yöntemi çalışır okumak `countSymbolBytes` uzaklıkta başlayan veri `symbolsReadOffset` bellek içi akışındaki.</span><span class="sxs-lookup"><span data-stu-id="f4d21-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="f4d21-118">Veriler kopyalanır `pSymbolBytes`, olması beklenen `countSymbolBytes` alanı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f4d21-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="f4d21-119">`pCountSymbolsBytesRead`Gerçek, daha az olabilir, okunan bayt sayısını içeren daha `countSymbolBytes` akışın sonuna ulaşıldı durumunda.</span><span class="sxs-lookup"><span data-stu-id="f4d21-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4d21-120">Geçerli uygulama Reflection.Emit desteklemez.</span><span class="sxs-lookup"><span data-stu-id="f4d21-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="f4d21-121">Modül Reflection.Emit kullanılarak oluşturulup oluşturulmadığını, yöntem `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="f4d21-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d21-122">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="f4d21-122">Requirements</span></span>  
 <span data-ttu-id="f4d21-123">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4d21-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d21-124">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4d21-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4d21-125">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4d21-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4d21-126">**.NET framework sürümleri:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4d21-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d21-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f4d21-127">See Also</span></span>  
 [<span data-ttu-id="f4d21-128">ICorProfilerInfo7 arabirimi</span><span class="sxs-lookup"><span data-stu-id="f4d21-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)