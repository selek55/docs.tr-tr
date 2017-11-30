---
title: "IAssemblyCache::InstallAssembly Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.InstallAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1207c2dc5b29b8de084ccb9145e886f34e8144b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="3a1b6-102">IAssemblyCache::InstallAssembly Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3a1b6-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="3a1b6-103">Belirtilen derleme genel derleme önbelleğinde yükler.</span><span class="sxs-lookup"><span data-stu-id="3a1b6-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1b6-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3a1b6-104">Syntax</span></span>  
  
```  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a1b6-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3a1b6-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="3a1b6-106">[in] Fusion.idl içinde tanımlı bayrak.</span><span class="sxs-lookup"><span data-stu-id="3a1b6-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="3a1b6-107">Aşağıdaki değerleri desteklenir:</span><span class="sxs-lookup"><span data-stu-id="3a1b6-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="3a1b6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="3a1b6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="3a1b6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="3a1b6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="3a1b6-110">[in] Bildirim yüklemek derleme yolu.</span><span class="sxs-lookup"><span data-stu-id="3a1b6-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="3a1b6-111">[in] A [fusıon_ınstall_reference](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) yükleme için verileri içeren yapısı.</span><span class="sxs-lookup"><span data-stu-id="3a1b6-111">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1b6-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3a1b6-112">Requirements</span></span>  
 <span data-ttu-id="3a1b6-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a1b6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1b6-114">**Başlık:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3a1b6-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3a1b6-115">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1b6-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3a1b6-116">See Also</span></span>  
 [<span data-ttu-id="3a1b6-117">Iassemblycache arabirimi</span><span class="sxs-lookup"><span data-stu-id="3a1b6-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)