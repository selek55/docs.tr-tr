---
title: "IMetaDataAssemblyEmit::DefineFile Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineFile
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48584822d7a2f31c466401db3a24156a71ad7011
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a>IMetaDataAssemblyEmit::DefineFile Yöntemi
Oluşturur bir `File` derleme bu derlemesi tarafından başvurulan ve ilişkili meta veri simgesi döndürür için meta verileri içeren meta veri yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szName`  
 [in] Kullanılacak dosya adı.  
  
 `pbHashValue`  
 [in] Derleme ile ilişkili karma verileri bir işaretçi.  
  
 `cbHashValue`  
 [in] Bayt cinsinden boyutu `pbHashValue`.  
  
 `dwFileFlags`  
 [in] Bit düzeyinde bileşimini `FileFlags` özellik ayarlarını belirten değerleri.  
  
 `pmdf`  
 [out] Bir işaretçi döndürülen `File` belirteci.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir `File` meta veri yapısı, bu derleme meta verilerini içeren dosyanın hariç olmak üzere bu derlemesi oluşturuldu zaman parçası olan her bir dosya için tanımlanmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platform:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** Cor.h  
  
 **Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IMetaDataAssemblyEmit Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
