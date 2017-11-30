---
title: "CorOpenFlags Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c7599a4b85a166aedd7a2293b79699b3ef03d14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="089b7-102">CorOpenFlags Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="089b7-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="089b7-103">Bildirim dosyaları açma bağlı meta veri davranışını denetleyen bayrak değerleri içerir.</span><span class="sxs-lookup"><span data-stu-id="089b7-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="089b7-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="089b7-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="089b7-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="089b7-105">Members</span></span>  
  
|<span data-ttu-id="089b7-106">Üye</span><span class="sxs-lookup"><span data-stu-id="089b7-106">Member</span></span>|<span data-ttu-id="089b7-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="089b7-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="089b7-108">Dosya yalnızca okumak için açılmalı gösterir.</span><span class="sxs-lookup"><span data-stu-id="089b7-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="089b7-109">Dosya yazma için açılmış olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="089b7-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="089b7-110">Kullanıyorsanız `ofWrite` ne zaman bayrak .winmd dosyası açılırken, ayrıca geçirdiğiniz `ofNoTransform` bayrağı.</span><span class="sxs-lookup"><span data-stu-id="089b7-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="089b7-111">Okuma ve yazma için bir maske.</span><span class="sxs-lookup"><span data-stu-id="089b7-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="089b7-112">Dosya belleğe okuma olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="089b7-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="089b7-113">Meta veri kendi kopya korumanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="089b7-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="089b7-114">Kullanımdan kalktı.</span><span class="sxs-lookup"><span data-stu-id="089b7-114">Obsolete.</span></span> <span data-ttu-id="089b7-115">Bu bayrak göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="089b7-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="089b7-116">Kullanımdan kalktı.</span><span class="sxs-lookup"><span data-stu-id="089b7-116">Obsolete.</span></span> <span data-ttu-id="089b7-117">Bu bayrak göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="089b7-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="089b7-118">Dosya okuma ve, açılmalı gösteren bir çağrı `QueryInterface` için bir [Imetadataemit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) yapılamaz.</span><span class="sxs-lookup"><span data-stu-id="089b7-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="089b7-119">Bellek için bir çağrı kullanılarak ayrıldı gösterir [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) ve meta verileri ile serbest.</span><span class="sxs-lookup"><span data-stu-id="089b7-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="089b7-120">Kullanımdan kalktı.</span><span class="sxs-lookup"><span data-stu-id="089b7-120">Obsolete.</span></span> <span data-ttu-id="089b7-121">Bu bayrak göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="089b7-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="089b7-122">.Winmd dosyaların otomatik Dönüşümlerin devre dışı olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="089b7-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="089b7-123">Diğer bir deyişle, bir .NET Framework türü için bir Windows çalışma zamanı tür projeksiyonu devre dışı bırakılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="089b7-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="089b7-124">Daha fazla bilgi için bkz: [altındaki başlık .NET ve Windows çalışma zamanı ile](http://msdn.microsoft.com/magazine/jj651569.aspx).</span><span class="sxs-lookup"><span data-stu-id="089b7-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="089b7-125">İç kullanım için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="089b7-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="089b7-126">İç kullanım için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="089b7-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="089b7-127">İç kullanım için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="089b7-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="089b7-128">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="089b7-128">Requirements</span></span>  
 <span data-ttu-id="089b7-129">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="089b7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="089b7-130">**Başlık:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="089b7-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="089b7-131">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="089b7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="089b7-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="089b7-132">See Also</span></span>  
 [<span data-ttu-id="089b7-133">Meta veri numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="089b7-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)