---
title: "Nasıl yapılır: iki koleksiyonları (LINQ-XML) birleştirme (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9fdbd442e0974dfcf5183a237eecd94c4c925ee4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a>Nasıl yapılır: iki koleksiyonları (LINQ-XML) birleştirme (C#)
Bazen bir öğe veya öznitelik bir XML belgesi başka bir öğe veya öznitelik başvurabilir. Örneğin, [örnek XML dosyası: müşteriler ve siparişler (LINQ-XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML belgesi, müşterilerin listesini ve siparişleri listesini içerir. Her `Customer` öğesi içeren bir `CustomerID` özniteliği. Her `Order` öğesi içeren bir `CustomerID` öğesi. `CustomerID` Her sipariş öğesinde başvurduğu `CustomerID` bir müşteri özniteliği.  
  
 Konu [örnek XSD dosyası: müşteriler ve siparişler](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) bu belgeyi doğrulamak için kullanılan bir XSD içerir. Kullandığı `xs:key` ve `xs:keyref` , kurmak için XSD özelliklerini `CustomerID` özniteliği `Customer` öğesidir bir anahtarı ve arasında bir ilişki oluşturmak için `CustomerID` her öğesinde `Order` öğesi ve `CustomerID` her özniteliği `Customer` öğesi.  
  
 İle [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], bu ilişkinin kullanarak yararlanabilirsiniz `join` yan tümcesi.  
  
 Kullanılabilir herhangi bir dizin olduğundan zayıf çalışma zamanı performans böyle birleştirme'nin elde edersiniz unutmayın.  
  
 Hakkında ayrıntılı bilgi için `join`, bkz: [birleştirme işlemleri (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek birleştirmeler `Customer` öğelerine `Order` öğeleri ve içeren yeni bir XML belgesi oluşturur `CompanyName` siparişleri öğesinde.  
  
 Sorguyu çalıştırmadan önce örnek belge şeması ile uyumlu doğrular [örnek XSD dosyası: müşteriler ve siparişler](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md). Bu birleştirme yan tümcesi her zaman çalışmasını sağlar.  
  
 Bu sorgu önce tüm alır `Customer` öğeleri ve bunları birleştirir `Order` öğeleri. Yalnızca siparişleri sahip müşteriler için seçtiği bir `CustomerID` "K" büyüktür. Ardından yeni bir proje `Order` her sipariş içinde müşteri bilgilerini içeren öğe.  
  
 Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: müşteriler ve siparişler (LINQ-XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
 Bu örnekte aşağıdaki XSD şema kullanır: [örnek XSD dosyası: müşteriler ve siparişler](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).  
  
 Bu şekilde birleştirme çok iyi gerçekleştirmediğini unutmayın. Birleştirmeler doğrusal arama gerçekleştirilir. Karma tabloları veya performansla yardımcı olması için dizin yok.  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.Write("Attempting to validate, ");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
if (!errors)  
{  
    // Join customers and orders, and create a new XML document with  
    // a different shape.  
  
    // The new document contains orders only for customers with a  
    // CustomerID > 'K'  
    XElement custOrd = custOrdDoc.Element("Root");  
    XElement newCustOrd = new XElement("Root",  
        from c in custOrd.Element("Customers").Elements("Customer")  
        join o in custOrd.Element("Orders").Elements("Order")  
                   on (string)c.Attribute("CustomerID") equals  
                      (string)o.Element("CustomerID")  
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0  
        select new XElement("Order",  
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),  
            new XElement("CompanyName", (string)c.Element("CompanyName")),  
            new XElement("ContactName", (string)c.Element("ContactName")),  
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),  
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))  
        )  
    );  
    Console.WriteLine(newCustOrd);  
}  
```  
  
 Bu kod aşağıdaki çıktıyı üretir:  
  
```  
Attempting to validate, custOrdDoc validated  
<Root>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-03-21T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-05-22T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-06-25T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-10-27T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>6</EmployeeID>  
    <OrderDate>1997-11-10T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>4</EmployeeID>  
    <OrderDate>1998-02-12T00:00:00</OrderDate>  
  </Order>  
</Root>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş sorgu teknikler (LINQ-XML) (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
