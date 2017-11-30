---
title: "ICorRuntimeHost::UnloadDomain Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.UnloadDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 054615e08da785f34be59c52488b8a4dcc2d7d98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="a62d2-102">ICorRuntimeHost::UnloadDomain Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a62d2-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="a62d2-103">Belirtilen uygulama etki alanından geçerli işlem kaldırır.</span><span class="sxs-lookup"><span data-stu-id="a62d2-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62d2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a62d2-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a62d2-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a62d2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a62d2-106">[in] Bir işaretçi türü <xref:System._AppDomain?displayProperty=nameWithType> boşaltılması için etki alanını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a62d2-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a62d2-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a62d2-107">Return Value</span></span>  
  
|<span data-ttu-id="a62d2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a62d2-108">HRESULT</span></span>|<span data-ttu-id="a62d2-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a62d2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a62d2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a62d2-110">S_OK</span></span>|<span data-ttu-id="a62d2-111">İşlem başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="a62d2-111">The operation was successful.</span></span>|  
|<span data-ttu-id="a62d2-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a62d2-112">S_FALSE</span></span>|<span data-ttu-id="a62d2-113">İşlemi tamamlayamadı.</span><span class="sxs-lookup"><span data-stu-id="a62d2-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a62d2-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a62d2-114">E_FAIL</span></span>|<span data-ttu-id="a62d2-115">Bilinmeyen, geri dönülemez bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="a62d2-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a62d2-116">Ortak dil çalışma zamanı (CLR), artık bir yöntem E_FAIL döndürürse, işlemde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="a62d2-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a62d2-117">Barındırma hiçbir API'leri yapılan sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="a62d2-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a62d2-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a62d2-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a62d2-119">CLR süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="a62d2-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a62d2-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a62d2-120">Requirements</span></span>  
 <span data-ttu-id="a62d2-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a62d2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a62d2-122">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a62d2-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a62d2-123">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="a62d2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a62d2-124">**.NET framework sürümü:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a62d2-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62d2-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a62d2-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="a62d2-126">Icorruntimehost arabirimi</span><span class="sxs-lookup"><span data-stu-id="a62d2-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)