---
title: ICorDebugType::GetStaticFieldValue Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a6a7305017c83b539a3d5ec11fa61ccd2af90a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue Metodu
Arabirim işaretçisi belirtilen alanı tarafından başvurulan statik alanın değerini içeren bir Icordebugvalue nesne için belirtilen yığın çerçevesinde belirtecini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fieldDef`  
 [in] Bir `mdFieldDef` statik alan belirtir belirteci.  
  
 `pFrame`  
 [in] Yığın çerçevesi temsil eden bir Icordebugframe gösteren bir işaretçi.  
  
 `ppValue`  
 [out] Adresine bir işaretçi bir `ICorDebugValue` statik alanın değerini içerir.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetStaticFieldValue` Yöntemi yalnızca tür ELEMENT_TYPE_CLASS veya ELEMENT_TYPE_VALUETYPE, ise belirttiği olarak kullanılabilir [Icordebugtype::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) yöntemi.  
  
 Genel olmayan türlerinde işlemi tarafından gerçekleştirilen `GetStaticFieldValue` için arama aynıdır [Icordebugclass::getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) tarafından döndürülen Icordebugclass nesne üzerinde [Icordebugtype::getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Genel türler için bir statik alan değeri göre belirli bir örnek oluşturma olacaktır. Ayrıca, statik alanı, büyük olasılıkla bir iş parçacığı, bir içerik veya uygulama etki alanı göreli olabilir, yığın çerçevesi uygun değeri belirlemek hata ayıklayıcı yardımcı olur.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetStaticFieldValue`sadece bir çağrı sırasında kullanılan `ICorDebugType::GetType` ELEMENT_TYPE_CLASS veya ELEMENT_TYPE_VALUETYPE değerini döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
