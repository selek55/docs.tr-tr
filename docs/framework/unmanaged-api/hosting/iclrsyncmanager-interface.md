---
title: ICLRSyncManager Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f75a9b532e91966d6b0be9ac6602080eac896ed8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager Arabirimi
İstenen görevler hakkında bilgi almak ve kendi eşitleme uygulamasında kilitlenmeleri algılamak için konak izin yöntemleri tanımlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|Ortak dil çalışma zamanı (CLR) oluşturma yineleyici Okuyucu-Yazıcı kilit Bekleyen Görevler belirlemek için kullanılacak ana bilgisayar için istek sayısı.|  
|[DeleteRWLockOwnerIterator Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|CLR yapılan bir çağrı tarafından oluşturulan bir yineleyici destroy istekleri `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|Belirtilen İzleyici sahibi görev alır.|  
|[GetRWLockOwnerNext Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|Geçerli Okuyucu-Yazıcı kilidi beklerken sonraki görev alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Thread>  
 [IHostSyncManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Yönetilen ve yönetilmeyen iş parçacığı oluşturma](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
