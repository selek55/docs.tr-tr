---
title: "Nasıl yapılır: bir nesneyi serileştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1ce7baf12c1826ddd14edad5e7dec328278c40e3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-serialize-an-object"></a>Nasıl yapılır: bir nesneyi serileştirme
Bir nesneyi serileştirmek için önce sıralanabilir ve ortak özelliklerini ve alanları ayarlamak için olan nesne oluşturun. Bunu yapmak için XML akışı bir akış veya bir dosya olarak depolanmasını aktarım biçimi belirlemeniz gerekir. Örneğin, XML Akışı kalıcı bir biçimde kaydedilmelidir varsa, oluşturun bir <xref:System.IO.FileStream> nesnesi.  
  
> [!NOTE]
>  Daha fazla XML serileştirme örnekleri için bkz: [XML serileştirme örnekler](../../../docs/standard/serialization/examples-of-xml-serialization.md).  
  
### <a name="to-serialize-an-object"></a>Bir nesneyi serileştirmek için  
  
1.  Nesne oluşturun ve kendi ortak alanları ve özelliklerini ayarlayın.  
  
2.  Oluşturmak bir <xref:System.Xml.Serialization.XmlSerializer> nesne türünü kullanarak. Daha fazla bilgi için bkz: <xref:System.Xml.Serialization.XmlSerializer> sınıf oluşturucu.  
  
3.  Çağrı <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> bir XML akışı veya bir dosya gösterimini nesnenin genel özellikleri ve alanları oluşturmak için yöntem. Aşağıdaki örnek, bir dosya oluşturur.  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Serileştirmeye Giriş](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [Nasıl yapılır: Nesneyi Seri Durumdan Çıkarma](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
