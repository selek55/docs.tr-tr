---
title: "Ertelenmiş yürütme örneği (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b902c58f801a6e157a971335895670e8a8bf2181
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="deferred-execution-example-c"></a>Ertelenmiş yürütme örneği (C#)
Geç değerlendirme, LINQ to XML sorgularını yürütme etkiler ve bu konuda nasıl ertelenmiş yürütme gösterir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, ertelenmiş yürütme kullanan bir genişletme yöntemi kullanırken yürütme sırasını gösterir. Örnek üç bir dizeler dizisi bildirir. Ardından tarafından döndürülen koleksiyon üzerinden yineleme `ConvertCollectionToUpperCase`.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 Bu örnek şu çıkışı üretir:  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 Tarafından döndürülen koleksiyon üzerinden yineleme zaman fark `ConvertCollectionToUpperCase`, her öğe kaynak dize diziden alınır ve sonraki önce büyük harfe dönüştürülmüş öğesi, kaynak dize diziden alınır.  
  
 Döndürülen koleksiyondaki her öğe içinde işlenmeden önce tüm dizisini büyük harfe dönüştürülmez olduğunu görebilirsiniz `foreach` içinde döngü `Main`.  
  
 Bu öğreticide sonraki konu zincirleme sorguları birlikte gösterilmektedir:  
  
-   [Zincirleme sorguları örnek (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Öğretici: Sorguları birlikte (C#) zincirleme](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
