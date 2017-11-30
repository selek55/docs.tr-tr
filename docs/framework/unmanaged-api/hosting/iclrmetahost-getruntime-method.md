---
title: ICLRMetaHost::GetRuntime Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type: apiref
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6ebfa1af4b824f4fcd4247cd7d0a667488f3e3ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="71637-102">ICLRMetaHost::GetRuntime Metodu</span><span class="sxs-lookup"><span data-stu-id="71637-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="71637-103">Alır [Iclrruntimeınfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) belirli bir ortak dil çalışma zamanı (CLR) sürümüne karşılık gelen arabirimi.</span><span class="sxs-lookup"><span data-stu-id="71637-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="71637-104">Bu yöntem yerini [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) ile kullanılan işlev [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) bayrağı.</span><span class="sxs-lookup"><span data-stu-id="71637-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71637-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="71637-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71637-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="71637-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="71637-107">[in] .NET Framework derleme sürüm biçimde meta verilerde depolanan "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="71637-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="71637-108">*A*, *B*, ve *X* ana sürüm, alt sürüm ve yapı numarası karşılık gelen ondalık sayılar.</span><span class="sxs-lookup"><span data-stu-id="71637-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71637-109">Bu parametre C:\Windows\Microsoft.NET\Framework veya C:\Windows\Microsoft.NET\Framework64 altında göründüğü gibi .NET Framework sürümü için dizin adı eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="71637-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="71637-110">Örnek değerler şunlardır: "v1.0.3705", "v1.1.4322", "v2.0.50727" ve "v4.0. *X*", burada *X* yüklü yapı sayısına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="71637-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="71637-111">"V" öneki gereklidir.</span><span class="sxs-lookup"><span data-stu-id="71637-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="71637-112">[in] İstenen arabirim tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="71637-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="71637-113">Şu anda, bu parametre için tek geçerli değer IID_ICLRRuntimeInfo ' dir.</span><span class="sxs-lookup"><span data-stu-id="71637-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="71637-114">[out] Bir işaretçi [Iclrruntimeınfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) istenen çalışma zamanına karşılık gelen arabirim.</span><span class="sxs-lookup"><span data-stu-id="71637-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71637-115">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="71637-115">Return Value</span></span>  
 <span data-ttu-id="71637-116">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="71637-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71637-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71637-117">HRESULT</span></span>|<span data-ttu-id="71637-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="71637-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71637-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="71637-119">S_OK</span></span>|<span data-ttu-id="71637-120">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="71637-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="71637-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="71637-121">E_POINTER</span></span>|<span data-ttu-id="71637-122">`pwzVersion`veya `ppRuntime` null.</span><span class="sxs-lookup"><span data-stu-id="71637-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71637-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="71637-123">Remarks</span></span>  
 <span data-ttu-id="71637-124">Bu yöntem tutarlı bir şekilde eski arabirimleriyle gibi etkileşimde bulunan [Icorruntimehost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) arabirimi ve eski işlevler kullanım dışı gibi `CorBindTo*` işlevleri (bkz [kullanım dışı CLR barındırma işlevleri](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) API barındırma .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="71637-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="71637-125">Diğer bir deyişle, eski API ile yüklenen çalışma zamanları yeni API görünür ve yeni API ile yüklenen çalışma zamanları eski API için görünür.</span><span class="sxs-lookup"><span data-stu-id="71637-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="71637-126">biçimindeki telefon numarasıdır.</span><span class="sxs-lookup"><span data-stu-id="71637-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71637-127">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="71637-127">Requirements</span></span>  
 <span data-ttu-id="71637-128">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71637-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71637-129">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="71637-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71637-130">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="71637-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71637-131">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71637-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71637-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="71637-132">See Also</span></span>  
 [<span data-ttu-id="71637-133">Iclrmetahost arabirimi</span><span class="sxs-lookup"><span data-stu-id="71637-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="71637-134">Kullanım dışı CLR barındırma arabirimleri ve coclass'ları</span><span class="sxs-lookup"><span data-stu-id="71637-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [<span data-ttu-id="71637-135">CLR barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="71637-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="71637-136">Kullanım dışı CLR barındırma işlevleri</span><span class="sxs-lookup"><span data-stu-id="71637-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="71637-137">Barındırma</span><span class="sxs-lookup"><span data-stu-id="71637-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)