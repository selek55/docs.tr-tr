---
title: "ICorPublishProcess::IsManaged Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.IsManaged
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21fdb09820acb6357fe1457d2f96c3319b3152a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged Yöntemi
İşlemin bu tarafından başvurulan olup olmadığını belirten bir değer alır [Icorpublishprocess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) yönetilen kodu bilinmektedir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbManaged`  
 [out] İşlem yönetilen kodu olup olmadığını gösteren bir Boole değeri için bir işaretçi. Değer `true` işlem kodu; yönetiliyorsa Aksi halde, `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli sürümü bu yana `ICorPublishProcess` yalnızca yönetilen kodu, işlemleri erişime `IsManaged` her zaman döndürür `true`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorPub.idl, CorPub.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorPublishProcess Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
