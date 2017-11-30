---
title: "&gt;(Büyük) (Varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 05673a8d24bccf798f654a73220411d41dba17d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="gt-greater-than-entity-sql"></a><span data-ttu-id="00461-102">&gt;(Büyük) (Varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="00461-102">&gt; (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="00461-103">Sol ifade sağ ifade büyük bir değere sahip olup olmadığını belirlemek için iki ifadeye karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="00461-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00461-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="00461-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="00461-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="00461-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="00461-106">Herhangi bir geçerli ifade.</span><span class="sxs-lookup"><span data-stu-id="00461-106">Any valid expression.</span></span> <span data-ttu-id="00461-107">Her iki ifadeleri örtük olarak dönüştürülebilir veri türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="00461-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="00461-108">Sonuç türleri</span><span class="sxs-lookup"><span data-stu-id="00461-108">Result Types</span></span>  
 <span data-ttu-id="00461-109">`true`Sol ifade sağ ifade büyük bir değer varsa; Aksi takdirde `false`.</span><span class="sxs-lookup"><span data-stu-id="00461-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00461-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="00461-110">Example</span></span>  
 <span data-ttu-id="00461-111">Aşağıdaki varlık SQL sorgusu kullanır > karşılaştırma işlecinin sol ifade sağ ifade büyük bir değere sahip olup olmadığını belirlemek için iki ifadeye karşılaştırın.</span><span class="sxs-lookup"><span data-stu-id="00461-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="00461-112">Sorgu AdventureWorks satış modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="00461-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="00461-113">Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="00461-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="00461-114">Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="00461-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="00461-115">Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="00461-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="00461-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="00461-116">See Also</span></span>  
 [<span data-ttu-id="00461-117">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="00461-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)