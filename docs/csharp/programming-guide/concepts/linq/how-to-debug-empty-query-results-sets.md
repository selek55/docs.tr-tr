---
title: "Nasıl yapılır: hata ayıklama boş sorgu sonuç kümeleri (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f8fb77a65c2c5023685251435d3028ffa9b3c2b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-debug-empty-query-results-sets-c"></a>Nasıl yapılır: hata ayıklama boş sorgu sonuç kümeleri (C#)
XML ağaçları sorgulanırken en yaygın sorunları XML ağacında bir varsayılan ad alanı varsa, XML değil gibi davranarak bir ad alanındaki Geliştirici bazen sorgu yazdığını biridir.  
  
 Bu konudaki örnekler ilk kümesi, bir varsayılan ad alanı XML yüklenir ve yanlış sorgulanan tipik bir yolunu gösterir.  
  
 XML ad alanında sorgulayabilmesi ikinci örneklerde gerekli düzeltmeleri ayarlayın.  
  
 Daha fazla bilgi için bkz: [XML ad alanları (C#) çalışma](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir ad alanındaki XML oluşturulmasını gösterir ve boş bir sonuç döndüren bir sorgu ayarlayın.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Bu örnekte aşağıdaki sonucu üretir:  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir ad alanı ve düzgün şekilde kodlanmış bir sorgu XML oluşturulmasını gösterir.  
  
 Çözümdür bildirme ve başlatmak için bir <xref:System.Xml.Linq.XNamespace> nesnesi ve belirtirken kullanılacak <xref:System.Xml.Linq.XName> nesneleri. Bu durumda, bağımsız değişkeni <xref:System.Xml.Linq.XElement.Elements%2A> yöntemi bir <xref:System.Xml.Linq.XName> nesnesi.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Bu örnekte aşağıdaki sonucu üretir:  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel sorgu (LINQ-XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
