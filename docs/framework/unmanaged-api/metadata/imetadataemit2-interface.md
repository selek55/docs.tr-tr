---
title: IMetaDataEmit2 Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94180a1f844ac43d8a42be59ac4fca807a70ec70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 Arabirimi
Genişletir [Imetadataemit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) öncelikle genel türleri ile çalışma olanağı sağlamak için arabirim.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[DefineGenericParam Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Genel tür parametresi için bir tanım oluşturur ve o genel tür parametresi için bir belirteç alır.|  
|[DefineMethodSpec Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Bir yöntem genel bir örneğini oluşturur ve tanımı için bir belirteç alır.|  
|[GetDeltaSaveSize Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Düzenle ve devam et geçerli oturum için değişiklikleri ifade etmek için gerekli verilerin boyutunu fark belirten bir değer alır.|  
|[ResetENCLog Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Düzenle ve devam et günlük sıfırlar ve yeni bir oturum başlatır.|  
|[SaveDelta Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Değişiklikleri geçerli Düzenle ve devam et oturumundan belirtilen dosyaya kaydeder.|  
|[SaveDeltaToMemory Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Değişiklikleri geçerli Düzenle ve devam et oturumundan belleğe kaydeder.|  
|[SaveDeltaToStream Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Değişiklikleri geçerli Düzenle ve devam et oturumundan belirtilen akışa kaydeder.|  
|[SetGenericParamProps Yöntemi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Belirtilen belirteç tarafından başvurulan genel parametresini tanımı için özellik değerlerini ayarlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** Cor.h  
  
 **Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Meta Veri Arabirimleri](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
