---
title: "Nasıl yapılır: Bir Yordama Bağımsız Değişkenler Geçirme (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Nasıl yapılır: Bir Yordama Bağımsız Değişkenler Geçirme (Visual Basic)
Bir yordam çağrısı için bağımsız değişken listesi parantez içinde yordam adıyla izleyin. Yordam tanımlar her gerekli parametre için karşılık gelen bir bağımsız değişken sağlayın ve isteğe bağlı olarak bağımsız değişkenleri sağlayın `Optional` parametreleri. Sağladığınız değil, bir `Optional` çağrısında parametre, sonraki tüm bağımsız değişkenleri sağlamış olursunuz, onun yerine bağımsız değişken listesinde işaretlemek için virgül içermelidir.  
  
 Bir veri türünde bir bağımsız değişken gibi kendi karşılık gelen bir parametre farklı geçirmek istiyorsanız, `Byte` için `String`, tür denetlemesi anahtarı ayarlayabilirsiniz ([Option Strict deyimi](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) için `Off`. Varsa `Option Strict` olan `On`, ya da kullanmalıdır dönüşümleri veya açık dönüşüm anahtar sözcükleri genişletme. Daha fazla bilgi için bkz: [Widening ve daraltma dönüşümleri](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) ve [tür dönüştürme işlevleri](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Daha fazla bilgi için bkz: [parametreler ve bağımsız değişkenler](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Bir yordama bağımsız değişkenlerden biri veya daha fazla geçirmek için  
  
1.  Arama deyiminde parantez yordamı adıyla izleyin.  
  
2.  Parantez içinde bir bağımsız değişken listesi yerleştirin. Bağımsız değişkenler virgülle ayırın ve yordam tanımlar her gerekli parametre için bir bağımsız değişken içerir.  
  
3.  Her değişken için karşılık gelen bir parametre türü yordamı bir veri türüne dönüştürülebilir değerlendiren geçerli bir ifade tanımlar olduğundan emin olun.  
  
4.  Bir parametre olarak tanımlanmışsa [isteğe bağlı](../../../../visual-basic/language-reference/modifiers/optional.md), bağımsız değişken listesinde içerebilir veya onu atlayın. Yordam atlarsanız, bu parametre için tanımlanan varsayılan değeri kullanır.  
  
5.  Bir bağımsız değişken atlarsanız bir `Optional` parametre ve başka bir parametre sonra parametre listesinde, bağımsız değişken listesinde fazladan bir virgül tarafından belirtilmemiş bağımsız değişkeni yerine işaretleyebilirsiniz.  
  
     Aşağıdaki örnek çağrıları [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> işlevi.  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     Önceki örnekte görüntülenecek ileti dizesi gerekli ilk bağımsız sağlar. İleti kutusu görüntülenecek düğmeleri belirten isteğe bağlı ikinci parametre için bir bağımsız değişken atlar. Çağrısı bir değer sağlamaz çünkü `MsgBox` varsayılan değeri kullanır `MsgBoxStyle.OKOnly`, yalnızca görüntüleyen bir **Tamam** düğmesi.  
  
     Bağımsız değişken listesinde ikinci virgülle belirtilmemişse ikinci bağımsız değişkeni yerine işaretler ve son dize için isteğe bağlı üçüncü parametresi, geçirilen `MsgBox`, başlık çubuğunda görüntülenecek metni olduğu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alt yordamlar](./sub-procedures.md)  
 [İşlev yordamları](./function-procedures.md)  
 [Özellik yordamları](./property-procedures.md)  
 [İşleç yordamları](./operator-procedures.md)  
 [Nasıl yapılır: bir yordamın parametresini tanımlama](./how-to-define-a-parameter-for-a-procedure.md)  
 [Bağımsız değişkenleri değere ve başvuruya göre geçirme](./passing-arguments-by-value-and-by-reference.md)  
 [Özyinelemeli yordamlar](./recursive-procedures.md)  
 [Yordam aşırı yüklemesi](./procedure-overloading.md)  
 [Nesneler ve sınıflar](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Nesne odaklı programlama](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
