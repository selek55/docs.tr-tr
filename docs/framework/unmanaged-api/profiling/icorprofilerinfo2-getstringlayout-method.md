---
title: ICorProfilerInfo2::GetStringLayout Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStringLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52a1b9218feb76f7653f747aa52c44284293221f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="7a822-102">ICorProfilerInfo2::GetStringLayout Metodu</span><span class="sxs-lookup"><span data-stu-id="7a822-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="7a822-103">Bir dize nesnesi düzeni hakkındaki bilgileri alır.</span><span class="sxs-lookup"><span data-stu-id="7a822-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="7a822-104">Bu yöntem de kullanım dışı [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]ve yerine geçen [Icorprofilerınfo3::getstringlayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7a822-104">This method is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], and is superseded by the [ICorProfilerInfo3::GetStringLayout2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a822-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7a822-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a822-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="7a822-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="7a822-107">[out] Konuma göre uzaklığını gösteren bir işaretçi `ObjectID` dize uzunluğu depolayan işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="7a822-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="7a822-108">Uzunluk olarak saklanan bir `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="7a822-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a822-109">Bu parametre dize uzunluğu kendisini arabelleği uzunluğunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="7a822-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="7a822-110">Arabelleğin uzunluğu artık kullanılamıyor.</span><span class="sxs-lookup"><span data-stu-id="7a822-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="7a822-111">[out] Konuma göre uzaklığını gösteren bir işaretçi `ObjectID` dize uzunluğu depolayan işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="7a822-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="7a822-112">Uzunluk olarak saklanan bir `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="7a822-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="7a822-113">[out] Bağıntı arabellek uzaklığı bir işaretçi `ObjectID` geniş karakter dizesi depolayan işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="7a822-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a822-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7a822-114">Remarks</span></span>  
 <span data-ttu-id="7a822-115">`GetStringLayout` Yöntemi göreli uzaklıkları alır `ObjectID` aşağıdaki depolandığı konumun işaretçi:</span><span class="sxs-lookup"><span data-stu-id="7a822-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
-   <span data-ttu-id="7a822-116">Dizesinin arabellek uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="7a822-116">The length of the string's buffer.</span></span>  
  
-   <span data-ttu-id="7a822-117">Dize uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="7a822-117">The length of the string itself.</span></span>  
  
-   <span data-ttu-id="7a822-118">Geniş karakterler gerçek dizesi içeren bir arabellek.</span><span class="sxs-lookup"><span data-stu-id="7a822-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="7a822-119">Null ile sonlandırılmış dizeler olabilir.</span><span class="sxs-lookup"><span data-stu-id="7a822-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a822-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="7a822-120">Requirements</span></span>  
 <span data-ttu-id="7a822-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a822-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a822-122">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a822-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a822-123">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a822-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a822-124">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a822-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a822-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7a822-125">See Also</span></span>  
 [<span data-ttu-id="7a822-126">Icorprofilerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="7a822-126">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="7a822-127">Icorprofilerınfo2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="7a822-127">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)