---
title: Icordebugcode Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode
helpviewer_keywords: ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86659b624ef01922b6c5d1db9b3ae3697d0128b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode-interface1"></a>Icordebugcode Interface1
Microsoft ara dili (MSIL) kodunun veya yerel kodun bir kesimini temsil eder.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[CreateBreakpoint Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|Belirtilen uzaklıkta bir kesme noktası oluşturur.|  
|[GetAddress Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|Kod kesimi göreli sanal adres (RAV) alır bu `ICorDebugCode` temsil eder.|  
|[GetCode Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|Belirtilen işlev için ayrıştırılmış biçimlendirilmiş tüm kodu alır. Bu yöntem kullanım dışı bırakıldı; kullanmak [Icordebugcode2::getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) yerine.|  
|[GetEnCRemapSequencePoints Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|Henüz uygulanmadı.|  
|[GetFunction Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|"Bu ile ilişkili ICorDebugFunction" alır `ICorDebugCode`.|  
|[GetILToNativeMapping Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|Eşlemeleri MSIL uzaklıkları yerel uzaklıkları temsil "Cor_debug_ıl_to_natıve_map" örnekleri dizisi alır.|  
|[GetSize Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|Bu tarafından temsil edilen ikili kod bayt cinsinden boyutu alır `ICorDebugCode`.|  
|[GetVersionNumber Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|Kod sürümünü belirleyen tabanlı numarasını alır bu `ICorDebugCode` temsil eder.|  
|[IsIL Yöntemi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|Gösteren bir değer alır olup olmadığını bu `ICorDebugCode` MSIL içinde derlenir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `ICorDebugCode`MSIL veya yerel koda temsil edebilir. MSIL kodunu temsil eden bir "ICorDebugFunction" nesne sıfır veya bir olabilir `ICorDebugCode` ilişkili nesneleri. Yerel kod temsil eden bir "ICorDebugFunction" nesne herhangi bir sayıda olabilir `ICorDebugCode` ilişkili nesneleri.  
  
> [!NOTE]
>  Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
    
 [ICorDebugCode3 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
