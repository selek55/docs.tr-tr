---
title: "And İşleci (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83e1f9df11152f88ef0db24a794026d6f5888a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="and-operator-visual-basic"></a>And İşleci (Visual Basic)
Mantıksal ve işlecini iki gerçekleştirir `Boolean` ifadeler veya iki sayısal ifadeye bit tabanlı birlikte.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Bölümler  
 `result`  
 Gerekli. Tüm `Boolean` veya sayısal ifade. Boole karşılaştırma için `result` mantıksal ve işlecini iki olduğu `Boolean` değerleri. Bit düzeyinde işlemler için `result` iki sayısal bit desenleri Bitsel birlikte temsil eden bir sayısal değer.  
  
 `expression1`  
 Gerekli. Tüm `Boolean` veya sayısal ifade.  
  
 `expression2`  
 Gerekli. Tüm `Boolean` veya sayısal ifade.  
  
## <a name="remarks"></a>Açıklamalar  
 Boole karşılaştırma için `result` olan `True` varsa ve yalnızca her iki `expression1` ve `expression2` için değerlendirin `True`. Aşağıdaki tabloda gösterilmektedir nasıl `result` belirlenir.  
  
|Varsa `expression1` olduğu|Ve `expression2` olduğu|Değeri `result` olduğu|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  Boole karşılaştırmaya `And` işleci her zaman yordam çağrıları yapma dahil olabilir hem ifadeleri değerlendirir. [AndAlso işleci](../../../visual-basic/language-reference/operators/andalso-operator.md) gerçekleştirir *kısa devre*, başka bir deyişle, olması durumunda `expression1` olan `False`, ardından `expression2` değerlendirilmez.  
  
 Sayısal değerler için uygulandığında `And` işleci içinde iki sayısal ifadeye bit tabanlı karşılaştırma aynı konumlandırılmış bit gerçekleştirir ve buna karşılık gelen içinde bit ayarlar `result` aşağıdaki tabloya göre.  
  
|Varsa, bit `expression1` olduğu|Ve içinde bit `expression2` olduğu|Bit `result` olduğu|  
|--------------------------------|---------------------------------|----------------------------|  
|1.|1.|1.|  
|1.|0|0|  
|0|1.|0|  
|0|0|0|  
  
> [!NOTE]
>  Mantıksal ve bit düzeyinde işleçler diğer aritmetik ve ilişkisel işleçleri düşük önceliğe sahip olduğundan, tüm bit düzeyinde işlemler doğru sonuçlar sağlamak için parantez içine alınmış.  
  
## <a name="data-types"></a>Veri Türleri  
 İşlenen birini oluşması durumunda `Boolean` ifadesi ve tek bir sayısal ifade, Visual Basic dönüştürür `Boolean` ifade sayısal bir değere (– 1 için `True` ve 0 `False`) ve bit tabanlı işlemi gerçekleştirir.  
  
 Boolean karşılaştırması için sonuç veri türünde `Boolean`. Bit tabanlı karşılaştırma için sonuç veri türü veri türleri için uygun sayısal bir tür değil. `expression1` ve `expression2`. "İlişkisel ve Bitsel karşılaştırmaları" tablosunda görmek [işleci sonuçlarını veri türleri](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  `And` İşleci olabilir *aşırı*, işleneni, sınıf veya yapı türüne sahip olduğunda bir sınıf veya yapı davranışını tanımlayabilirsiniz, anlamına gelir. Bu tür bir sınıf veya yapı üzerinde kodunuzu bu işleç kullanıyorsa, yeniden tanımlanan davranışını anladığınızdan emin olun. Daha fazla bilgi için bkz: [işleç yordamları](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `And` iki ifadeleri mantıksal ve işlecini gerçekleştirmek için işleci. Sonuç bir `Boolean` ifadeleri her ikisi de olup olmadığını gösteren bir değer `True`.  
  
 [!code-vb[VbVbalrOperators#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_1.vb)]  
  
 Önceki örnekte sonuçlarını üreten `True` ve `False`sırasıyla.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `And` iki sayısal ifadeye tek tek bitleri mantıksal ve işlecini gerçekleştirmek için işleci. İşlenen karşılık gelen bitleri hem kümesine 1 olduğunda sonuç düzeninde bit ayarlanır.  
  
 [!code-vb[VbVbalrOperators#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-operator_2.vb)]  
  
 Önceki örnekte, 8, 2 ve 0, sonuçları sırasıyla üretir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mantıksal ve bit düzeyinde işleçler (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic'de İşleç önceliği](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [İşlevselliğe göre listelenmiş işleçler](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [AndAlso işleci](../../../visual-basic/language-reference/operators/andalso-operator.md)  
 [Visual Basic'de mantıksal ve bit düzeyinde işleçler](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
