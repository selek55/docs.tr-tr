---
title: ISymUnmanagedWriter Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter
helpviewer_keywords: ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4996f0196df4c2bcf890df6ad972f313403e435
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter Arabirimi
Sembol yazıcıyı temsil eder ve belgeleri, sıralama noktaları, sözcük kapsamlar ve değişkenleri tanımlamak için yöntemler sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Abort Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Sembol yazan sembol deposu simgeleri kaydetmeden kapatır.|  
|[Close Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Sembol yazan simgeleri sembol deposu uyguladıktan sonra kapatır.|  
|[CloseMethod Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Geçerli yöntemi kapatır. Bir yöntem kapatıldıktan sonra daha fazla simge içinde tanımlanabilir.|  
|[CloseNamespace Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Kapanır ad alanı en son açıldı.|  
|[CloseScope Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Geçerli sözcük kapsamı kapatır.|  
|[DefineConstant Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Sabit bir değer için bir ad tanımlar.|  
|[DefineDocument Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Kaynak belge tanımlar.|  
|[DefineField Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Yöntemi içinde değil tek bir değişken tanımlar.|  
|[DefineGlobalVariable Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Tek bir genel değişkeni tanımlar.|  
|[DefineLocalVariable Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Tek bir değişken geçerli sözcük kapsamda tanımlar.|  
|[DefineParameter Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Tek bir parametre geçerli yöntemi tanımlar.|  
|[DefineSequencePoints Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Geçerli yöntemi içinde sıralama noktaları grubunu tanımlar.|  
|[GetDebugInfo Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Taşınabilir yürütülebilir (PE) dosya üstbilgisinde hata ayıklama dizin girişi yazmak bir derleyici için gerekli bilgileri döndürür.|  
|[Initialize Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|İle bu yazıcısı ilişkili olacağı meta verileri verici arabirimi ayarlar ve hata ayıklama simgeleri yazılacak çıktı dosyası adını ayarlar.|  
|[Initialize2 Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|İle bu yazıcısı ilişkili olacağı meta verileri verici arabirimi ayarlar, hangi hata ayıklama simgeleri yazılır ve program veritabanı (PDB) dosyasının son konumunu ayarlar çıktı dosyası adını ayarlar.|  
|[OpenMethod Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Hangi sembolün bilgi yayılan bir yöntem açar.|  
|[OpenNamespace Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Yeni bir ad alanı açılır.|  
|[OpenScope Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Yeni bir sözcük kapsamı geçerli yönteminde açar.|  
|[RemapToken Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Sembol yazıcı meta verileri yayılan gibi meta veri simgesi eşleştirilmiş bildirir.|  
|[SetMethodSourceRange Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Gerçek başlangıç ve bitiş kaynak dosyası içinde yönteminin belirtir.|  
|[SetScopeRange Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Belirtilen sözcük kapsamı için uzaklık aralığını tanımlar.|  
|[SetSymAttribute Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Adını dayalı özel bir öznitelik tanımlar.|  
|[SetUserEntryPoint Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Bu modül için giriş noktası kullanıcı tanımlı yöntemini belirtir.|  
|[UsingNamespace Yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Verilen tam ad alanı adı şu anda açık sözcük kapsamında kullanılmakta olduğunu belirtir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tanılama Simge Deposu Arabirimleri](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedWriter2 Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [ISymUnmanagedWriter3 Arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
