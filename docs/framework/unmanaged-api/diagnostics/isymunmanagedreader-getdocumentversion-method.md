---
title: ISymUnmanagedReader::GetDocumentVersion Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2cb0abf887abaac4d7433b52a795beca509ec61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a>ISymUnmanagedReader::GetDocumentVersion Metodu
Belirtilen belge belirtilen sürümünü alır. Belge sürüm 1'den başlar ve belgenin kullanarak güncelleştirilir her zaman artırılır [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) yöntemi. Varsa `pbCurrent` parametresi `true`, bu belgenin en son sürümüdür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pDoc`  
 [in] Belirtilen belge.  
  
 `version`  
 [out] Bir işaretçi bir değişkene belirtilen belge sürümünü alır.  
  
 `pbCurrent`  
 [out] Alan bir değişken için bir işaretçi `true` bu belgenin en son sürüm ise veya `false` en son sürümü değilse.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ISymUnmanagedReader Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
