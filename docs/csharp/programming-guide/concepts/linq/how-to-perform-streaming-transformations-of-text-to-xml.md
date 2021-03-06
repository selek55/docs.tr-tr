---
title: "Nasıl yapılır: XML (C#) için metin akış dönüştürmeleri gerçekleştirebilirsiniz"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03c5ed5ef66db311ade751b5aad21de70b78f063
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Nasıl yapılır: XML (C#) için metin akış dönüştürmeleri gerçekleştirebilirsiniz
Bir metin dosyası işleme için bir yaklaşım ise metin dosyası akışları bir genişletme yöntemi kullanarak bir defada bir satır yazmak için `yield return` oluşturun. Ardından, yavaş bir ertelenmiş şekilde metin dosyasında işler bir LINQ sorgu yazabilirsiniz. Ardından kullanırsanız <xref:System.Xml.Linq.XStreamingElement> akış çıkışı için daha sonra bir dönüşüm metin dosyasından en az bir kaynak metin dosyasının boyutunu bağımsız olarak bellek miktarını kullanır XML oluşturabilirsiniz.  
  
 Akış dönüşümleri ilgili bazı uyarılar var. Bir akış dönüştürmesi en iyi yeri sonra ve kaynak belgesinde oluşma sırada satırları işlem, dosyanın tamamı işleyebilir durumlarda uygulanır. Dosyanın birden çok kez işlemek varsa veya bunları işlemeden önce satırları sıralamak varsa, bir akış teknik kullanmanın avantajları çoğunu kaybedersiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki metin dosyası People.txt, bu örnek kaynağıdır.  
  
```  
#This is a comment  
1,Tai,Yee,Writer  
2,Nikolay,Grachev,Programmer  
3,David,Wright,Inventor  
```  
  
 Aşağıdaki kod satırları ertelenmiş biçimde metin dosyasının akışları bir genişletme yöntemi içerir.  
  
```csharp  
public static class StreamReaderSequence  
{  
    public static IEnumerable<string> Lines(this StreamReader source)  
    {  
        String line;  
  
        if (source == null)  
            throw new ArgumentNullException("source");  
        while ((line = source.ReadLine()) != null)  
        {  
            yield return line;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        StreamReader sr = new StreamReader("People.txt");  
        XStreamingElement xmlTree = new XStreamingElement("Root",  
            from line in sr.Lines()  
            let items = line.Split(',')  
            where !line.StartsWith("#")  
            select new XElement("Person",  
                       new XAttribute("ID", items[0]),  
                       new XElement("First", items[1]),  
                       new XElement("Last", items[2]),  
                       new XElement("Occupation", items[3])  
                   )  
        );  
        Console.WriteLine(xmlTree);  
        sr.Close();  
    }  
}  
```  
  
 Bu örnek şu çıkışı üretir:  
  
```xml  
<Root>  
  <Person ID="1">  
    <First>Tai</First>  
    <Last>Yee</Last>  
    <Occupation>Writer</Occupation>  
  </Person>  
  <Person ID="2">  
    <First>Nikolay</First>  
    <Last>Grachev</Last>  
    <Occupation>Programmer</Occupation>  
  </Person>  
  <Person ID="3">  
    <First>David</First>  
    <Last>Wright</Last>  
    <Occupation>Inventor</Occupation>  
  </Person>  
</Root>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XStreamingElement>  
 [Gelişmiş sorgu teknikler (LINQ-XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
