---
title: "ÇAKIŞMALAR (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 22593af3f79e78621764ba293e65505a72b194f8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="overlaps-entity-sql"></a>ÇAKIŞMALAR (varlık SQL)
İki koleksiyon ortak öğeler sahip olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Başka bir sorgu ifadesinden döndürülen koleksiyonu ile karşılaştırmak için bir koleksiyon döndürür herhangi bir geçerli sorgu ifade. Tüm ifadeler aynı türde veya ortak bir temel veya türetilmiş türünde olması gerekir `expression`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`iki koleksiyon ortak öğeler varsa; Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 İşlevsel olarak eşdeğerdir aşağıdaki ÇAKIŞMALAR sağlar:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 ÇAKIŞMALAR biridir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri ayarlayın. Tüm [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kümesi işleçleri soldan sağa değerlendirilir. Öncelik bilgilerini [!INCLUDE[esql](../../../../../../includes/esql-md.md)] işleçleri, bakın [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki varlık SQL sorgusunu ÇAKIŞMALAR işleci belirler için iki koleksiyon ortak bir değere sahip olup olmadığını kullanır. Sorgu AdventureWorks satış modelini temel alır. Derlemek ve bunu çalıştırmak için aşağıdaki adımları izleyin:  
  
1.  Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Entity SQL Başvurusu](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
