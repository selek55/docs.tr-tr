---
title: "select tümcesi (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f40bc26d1812e76ac618c5a0ddf23c4cef2700d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-c-reference"></a>select tümcesi (C# Başvurusu)
Bir sorgu ifadesinde `select` yan tümcesi sorgu yürütüldüğünde, üretilecek değerleri türünü belirtir. Sonuç önceki tüm yan tümceleri değerlendirmesi ve tüm ifadelerinde dayalı `select` yan tümcesi kendisi. Bir sorgu ifadesi ile bitmesi bir `select` yan tümcesinin veya bir [grup](../../../csharp/language-reference/keywords/group-clause.md) yan tümcesi.  
  
 Aşağıdaki örnekte basit bir `select` yan tümcesinde bir sorgu ifadesi.  
  
 [!code-csharp[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]  
  
 Sıra türü üretilen tarafından `select` yan tümcesi belirler sorgu değişkeninin türü `queryHighScores`. En basit durumda, `select` yan tümcesi yalnızca aralık değişkenini belirtir. Bu veri kaynağı olarak aynı türdeki öğeleri içerecek şekilde döndürülen dizi neden olur. Daha fazla bilgi için bkz: [LINQ Sorgu işlemlerinde tür ilişkileri](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md). Ancak, `select` yan tümcesi de dönüştürme için güçlü bir mekanizma sağlar (veya *planlanması*) yeni türlerine veri kaynağı. Daha fazla bilgi için bkz: [LINQ (C#) ile veri dönüştürmeler](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).  
  
## <a name="example"></a>Örnek  
 Tüm farklı formları aşağıdaki örnekte gösterilir bir `select` yan tümcesi alabilir. Her sorguda arasındaki ilişkiyi Not `select` yan tümcesi ve türünü *sorgu değişkeni* (`studentQuery1`, `studentQuery2`, vb.).  
  
 [!code-csharp[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]  
  
 Gösterildiği gibi `studentQuery8` önceki örnekte, bazı durumlarda, yalnızca bir alt kümesini kaynak öğelerin özellikleri içerecek şekilde döndürülen sıradaki isteyebilirsiniz. Döndürülen dizi olabildiğince küçük tutarak bellek gereksinimlerini azaltın ve sorgu yürütme hızını artırır. Anonim bir tür oluşturarak bunu gerçekleştirebilirsiniz `select` yan tümcesi ve source öğesi uygun özelliklerinden başlatılamadı nesne Başlatıcı kullanarak. Bunun nasıl yapılacağı örneği için bkz: [nesne ve koleksiyon başlatıcıları](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme zamanında `select` yan tümcesi bir yöntem çağrısı için çevrilir <xref:System.Linq.Enumerable.Select%2A> standart sorgu işleci.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [Sorgu anahtar sözcükleri (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [from yan tümcesi](../../../csharp/language-reference/keywords/from-clause.md)  
 [partial (yöntem) (C# Başvurusu)](../../../csharp/language-reference/keywords/partial-method.md)  
 [Anonim türler](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [LINQ Sorgu ifadeleri](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [C# üzerinde LINQ ile çalışmaya başlama](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
