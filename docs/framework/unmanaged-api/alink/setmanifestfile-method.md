---
title: "SetManifestFile Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink3.SetManifestFile
api_location: alink.dll
api_type: COM
f1_keywords: SetManifestFile
helpviewer_keywords: SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 807452326193d193f3bc603ebc7b74a5a0f1c281
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="1c4fe-102">SetManifestFile Yöntemi</span><span class="sxs-lookup"><span data-stu-id="1c4fe-102">SetManifestFile Method</span></span>
<span data-ttu-id="1c4fe-103">Bağlayıcı derleme oluşturduğunda kullanan bildirim dosyası sıfırlamak mı sağlar.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4fe-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1c4fe-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c4fe-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1c4fe-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="1c4fe-106">İçerikleri Win32 kaynakları blob'a put bildirim dosyasının adı.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c4fe-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="1c4fe-107">Return Value</span></span>  
 <span data-ttu-id="1c4fe-108">Yöntem başarılı olursa S_OK döndürür.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c4fe-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1c4fe-109">Remarks</span></span>  
 <span data-ttu-id="1c4fe-110">Bu için Win32ResBlob soran önce çağırın.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="1c4fe-111">Değeri `pszFile` parametredir içerikleri okuma ve kimliği, RT_MANIFEST Win32 kaynaklarla koymak bildirim dosyasının adı.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="1c4fe-112">Null parametresiyle çağrıldığında, daha önce okuma herhangi bildirimi temizlenir.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="1c4fe-113">Bu, başlangıç zamanı bağlayıcı durumunu sıfırlamak için sağlar.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c4fe-114">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1c4fe-114">Requirements</span></span>  
 <span data-ttu-id="1c4fe-115">ALink.h gerektirir</span><span class="sxs-lookup"><span data-stu-id="1c4fe-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4fe-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1c4fe-116">See Also</span></span>  
 [<span data-ttu-id="1c4fe-117">Ialink3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="1c4fe-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [<span data-ttu-id="1c4fe-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="1c4fe-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="1c4fe-119">Ialink arabirimi</span><span class="sxs-lookup"><span data-stu-id="1c4fe-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1c4fe-120">Al.exe (derleme bağlayıcı)</span><span class="sxs-lookup"><span data-stu-id="1c4fe-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)