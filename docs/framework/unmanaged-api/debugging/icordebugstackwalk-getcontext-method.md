---
title: ICorDebugStackWalk::GetContext Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 080ce39422faee4e1228bd87bf994080fab4de71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext Metodu
Geçerli kare bağlamının döndürür [Icordebugstackwalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `contextFlags`  
 [in] (WinNT.h içinde tanımlanmıştır) bağlamı arabelleğine istenen içeriği gösterir bayraklar.  
  
 `contextBufSize`  
 [in] Bağlamı arabelleğine tahsis edilen boyutu.  
  
 `contextSize`  
 [out] Bağlam gerçek boyutu. Bu değer bağlam arabellek boyutu eşit veya daha az olmalıdır.  
  
 `contextBuf`  
 [out] Bağlam arabelleği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Geçerli çerçeve bağlamının başarıyla döndürüldü.|  
|E_FAIL|Bağlam döndürülemedi.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|Bağlam arabellek çok küçük.|  
|CORDBG_E_PAST_END_OF_STACK|Çerçeve işaretçisi yığının sonuna zaten; Bu nedenle, hiçbir ek çerçeve erişilebilir.|  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
 Geriye doğru izleme geçici olmayan Yazmaçları gibi kayıtları yalnızca bir kısmı getirir çünkü bağlam tam kayıt durumu çağrı aynı anda aynı olmayabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
