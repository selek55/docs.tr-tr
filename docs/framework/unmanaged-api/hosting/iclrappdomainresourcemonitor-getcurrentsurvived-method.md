---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 612e27120196d2920b75c030929af1807d4a336f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a>ICLRAppDomainResourceMonitor::GetCurrentSurvived Metodu
Çöp toplama engelleme son tam, derdi bitti ve geçerli uygulama etki alanı tarafından başvurulan bayt sayısını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwAppDomainId`  
 [in] İstenen uygulama etki alanı kimliği.  
  
 `pAppDomainBytesSurvived`  
 [out] Bu uygulama etki alanı tarafından tutulan son çöp toplamadan sonra derdi bitti bayt sayısı için bir işaretçi. Tam sonra bu sayı doğru ve eksiksiz koleksiyonudur. Kısa ömürlü bir koleksiyon sonra bu sayı olası eksik. Bu parametre olabilir `null`.  
  
 `pRuntimeBytesSurvived`  
 [out] Toplam son çöp koleksiyondan derdi bitti bayt sayısı için bir işaretçi. Sonra tam bir koleksiyon, bu sayı Yönetilen yığın tutulan bayt sayısını temsil eder. Kısa ömürlü bir koleksiyon sonra bu sayı kısa ömürlü kuşakta Canlı tutulur bayt sayısını temsil eder. Bu parametre olabilir `null`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yöntem başarıyla tamamlandı.|  
|COR_E_APPDOMAINUNLOADED|Uygulama etki alanı kaldırıldı veya yok.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çöp toplama engelleme yalnızca tam sonra İstatistikler güncelleştirilir; diğer bir deyişle, tüm nesli içerir ve uygulama koleksiyonunun çalışırken durdurur koleksiyonu oluşur. Örneğin, <xref:System.GC.Collect?displayProperty=nameWithType> yöntemi aşırı yüklemesini koleksiyon engelleme tam, gerçekleştirir. Eşzamanlı atık toplama arka planda gerçekleşir ve uygulamayı engellemez.  
  
 `GetCurrentSurvived` Yöntemdir yönetilen yönetilmeyen eşdeğerini <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> özelliği.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MetaHost.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRAppDomainResourceMonitor Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [Uygulama Etki Alanı Kaynak İzleme](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Barındırma](../../../../docs/framework/unmanaged-api/hosting/index.md)
