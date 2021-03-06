---
title: "Derleme sonrası şema bilgi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b59b2b59852190bd19a3c1c9536fadb7b40603e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="post-schema-compilation-infoset"></a>Derleme sonrası şema bilgi
[World Wide Web Konsorsiyumu (W3C) XML Şeması öneri](http://go.microsoft.com/fwlink/?linkid=45242) öncesi şema doğrulaması ve sonrası şema derleme için sunulmalıdır bilgisi kümesi (bilgi) açıklanır. XML şema nesne modeli (SOM) önce ve sonra bu Etkilenme görünümleri <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> yöntemi <xref:System.Xml.Schema.XmlSchemaSet> olarak adlandırılır.  
  
 Ön şema doğrulaması bilgi ve şema düzenleme sırasında oluşturulmuştur. Derleme sonrası şema bilgi sonra oluşturulan <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> yöntemi <xref:System.Xml.Schema.XmlSchemaSet> şema derlemesi sırasında çağrılır ve özellikleri olarak sunulur.  
  
 SOM öncesi şema doğrulaması ve sonrası şema derleme infosets temsil eden nesne modelidir; sınıflarda oluşan <xref:System.Xml.Schema?displayProperty=nameWithType> ad alanı. Tüm okuma ve yazma sınıflarda özellikleri <xref:System.Xml.Schema> ad alanı ait sınıflarda salt okunur tüm özelliklerini sırasında ön şema doğrulaması bilgi <xref:System.Xml.Schema> ad ait sonrası şema derleme bilgi. Bu kural için özel ön şema doğrulaması bilgi ve sonrası şema derleme bilgi özellikleri aşağıdaki özellikleri durumdur.  
  
|örneği|Özellik|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 Örneğin, <xref:System.Xml.Schema.XmlSchemaElement> ve <xref:System.Xml.Schema.XmlSchemaComplexType> sınıflarının her ikisi de sahip `BlockResolved` ve `FinalResolved` özellikleri. Bu özelliklerin değerlerini tutmak için kullanılan `Block` ve `Final` şeması derlenmiş ve doğrulanmış sonra özellikleri. `BlockResolved`ve `FinalResolved` sonrası şema derleme bilgi parçası olan salt okunur özelliklerdir.  
  
 Aşağıdaki örnekte gösterildiği <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> özelliği <xref:System.Xml.Schema.XmlSchemaElement> sınıf kümesi şema doğrulama sonra. Doğrulama önce özelliği içeren bir `null` , başvuru ve <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> türünün adını söz konusu ayarlanır. Doğrulama sonrasında <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> geçerli bir tür olarak çözümlenir ve tür nesnesi aracılığıyla kullanılabilir <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> özelliği.  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Şema Nesne Modeli (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
