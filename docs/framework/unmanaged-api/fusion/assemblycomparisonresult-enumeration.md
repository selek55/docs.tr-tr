---
title: "AssemblyComparisonResult Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyComparisonResult
api_location: fusion.dll
api_type: COM
f1_keywords: AssemblyComparisonResult
helpviewer_keywords: AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75c53e750ad031ccec944625be130547404767bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="6c68f-102">AssemblyComparisonResult Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="6c68f-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="6c68f-103">Tarafından belirlenen iki derleme kimlikleri, eşdeğer gösterir [Compareassemblyıdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) işlevi.</span><span class="sxs-lookup"><span data-stu-id="6c68f-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c68f-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6c68f-104">Syntax</span></span>  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="6c68f-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="6c68f-105">Members</span></span>  
  
|<span data-ttu-id="6c68f-106">Üye adı</span><span class="sxs-lookup"><span data-stu-id="6c68f-106">Member name</span></span>|<span data-ttu-id="6c68f-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c68f-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="6c68f-108">Tüm derleme karşılaştırma eşlemesinde alanlarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="6c68f-109">Derlemeleri derleme sürüm numaraları için .NET Framework sürüm 2.0, ortak dil çalışma zamanı (CLR) sürüm Birleştirici göre eşdeğer olarak değerlendiriliyor olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="6c68f-110">.NET Framework 2.0, derleme sürüm numaralarının CLR Birleştirici göre derlemelerin kısmi eşleşme gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="6c68f-111">Kısmi eşleşme derlemelerin gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="6c68f-112">Sürüm numaraları eski Birleştirici üzerinde temel derlemelerin kısmi eşleşme gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="6c68f-113">Yalnızca adlandırılmış derlemelerin kısmi eşleşme gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="6c68f-114">Derlemeleri eski sürümlerinde, .NET Framework sürüm numaralarının CLR Birleştirici göre eşdeğer olarak değerlendiriliyor olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="6c68f-115">Sürüm numaralarını yoksayıldı iki yalnızca adlandırılmış derlemeler arasında bir eşleşme gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="6c68f-116">Eşleşme iki derlemeler arasında oluştuğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="6c68f-117">İki derleme yalnızca kısmen eşleşen bunların sürüm numaralarını dışında eşleştiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="6c68f-118">İki derleme eşleşmiyor bunların sürüm numaralarını dışında eşleştiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="6c68f-119">Denkliği olmayan nedeni bilinmiyor gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c68f-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c68f-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="6c68f-120">Requirements</span></span>  
 <span data-ttu-id="6c68f-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c68f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c68f-122">**Başlık:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6c68f-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6c68f-123">**Kitaplığı:** bir kaynak olarak MsCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="6c68f-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c68f-124">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c68f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c68f-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6c68f-125">See Also</span></span>  
 [<span data-ttu-id="6c68f-126">Compareassemblyıdentity işlevi</span><span class="sxs-lookup"><span data-stu-id="6c68f-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [<span data-ttu-id="6c68f-127">Fusion numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="6c68f-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)