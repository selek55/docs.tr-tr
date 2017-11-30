---
title: "RUNTIME_INFO_FLAGS Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 697111efbb4e3f705c881ec677f781b6e3e6959d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="1df8c-102">RUNTIME_INFO_FLAGS Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="1df8c-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="1df8c-103">Ortak dil çalışma zamanı (CLR) hakkında bilgiler döndürülmelidir belirtmek değerlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df8c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1df8c-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="1df8c-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="1df8c-105">Members</span></span>  
  
|<span data-ttu-id="1df8c-106">Üye</span><span class="sxs-lookup"><span data-stu-id="1df8c-106">Member</span></span>|<span data-ttu-id="1df8c-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1df8c-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="1df8c-108">Dizin bilgilerini eklenmeyeceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="1df8c-109">Sürüm bilgileri eklenmeyeceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="1df8c-110">Bir hata iletişim kutusu hata yapması üzerine gösterilmesi gereken değil olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="1df8c-111">Belirten arama etkilerini [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) SEM_FAILCRITICALERRORS bayrağı işlevi geçersiz.</span><span class="sxs-lookup"><span data-stu-id="1df8c-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="1df8c-112">Diğer bir deyişle, bir yükleme iletişim kutusu başarısızlık gizlenen yerine gösterilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="1df8c-113">Çalışma zamanı AMD 64 uyumlu sürümü hakkında bilgi için bir istek gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="1df8c-114">Çalışma zamanı IA-64-compatible sürümü hakkında bilgi için bir istek gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="1df8c-115">Çalışma zamanı x86 uyumlu sürümü hakkında bilgi için bir istek gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="1df8c-116">Sürüm yükseltme bilgileri ekleneceğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1df8c-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1df8c-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1df8c-117">Remarks</span></span>  
 <span data-ttu-id="1df8c-118">Aşağıdaki platform mimarisi bayrakları belirtilen yalnızca birer birer olabilir ve birleştirilemez:</span><span class="sxs-lookup"><span data-stu-id="1df8c-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="1df8c-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="1df8c-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="1df8c-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="1df8c-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="1df8c-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="1df8c-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df8c-122">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1df8c-122">Requirements</span></span>  
 <span data-ttu-id="1df8c-123">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1df8c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df8c-124">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1df8c-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1df8c-125">**Kitaplığı:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1df8c-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1df8c-126">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df8c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df8c-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1df8c-127">See Also</span></span>  
 [<span data-ttu-id="1df8c-128">Barındırma numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="1df8c-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)