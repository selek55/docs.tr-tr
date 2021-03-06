---
title: "Adlı Tür oluşturucu (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b572d09b812d43fa64e30a3058da9af01d29b747
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="named-type-constructor-entity-sql"></a>Adlı Tür oluşturucu (varlık SQL)
Kavramsal model nominal türleri gibi varlık veya karmaşık türler örneklerini oluşturmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>Arguments  
 `identifier`  
 Bir basit ya da alıntı tanımlayıcısı değeri. Daha fazla bilgi için [tanımlayıcıları](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 `expression`  
 Türü bildiriminde göründükleri gibi aynı sırada olduğu varsayılır türü öznitelikleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Adlandırılmış karmaşık türleri ve varlık türleri örnekleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki örnekler nasıl nominal ve karmaşık türleri oluşturulacağını gösterir:  
  
 İfade bir örneğini oluşturur bir `Person` türü:  
  
 `Person("abc", 12)`  
  
 İfade karmaşık türün bir örneğini oluşturur:  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 Aşağıdaki ifade, iç içe geçmiş bir karmaşık tür bir örneğini oluşturur:  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 İfade bir varlık örneği ile iç içe geçmiş bir karmaşık tür oluşturur:  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Aşağıdaki örnekte, bir özelliği null karmaşık türün başlatmak gösterilmektedir:`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki varlık SQL sorgusunu adlandırılmış Tür oluşturucu kavramsal model türünün bir örneği oluşturmak için kullanır. Sorgu AdventureWorks satış modelini temel alır. Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:  
  
1.  Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oluşturma Türleri](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [Entity SQL Başvurusu](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
