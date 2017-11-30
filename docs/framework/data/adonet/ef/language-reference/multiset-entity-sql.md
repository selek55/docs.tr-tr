---
title: "MULTISET (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e72605225d214ccd2283aaae3f0c2071ceb92d91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="multiset-entity-sql"></a><span data-ttu-id="ef931-102">MULTISET (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="ef931-102">MULTISET (Entity SQL)</span></span>
<span data-ttu-id="ef931-103">Değerler listesinden bir çoklu küme örneği oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ef931-103">Creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="ef931-104">Çok KÜMELİ Oluşturucusu tüm değerleri uyumlu bir türü olmalıdır `T`.</span><span class="sxs-lookup"><span data-stu-id="ef931-104">All the values in the MULTISET constructor must be of a compatible type `T`.</span></span> <span data-ttu-id="ef931-105">Boş multiset oluşturucular izin verilmiyor.</span><span class="sxs-lookup"><span data-stu-id="ef931-105">Empty multiset constructors are not allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef931-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="ef931-106">Syntax</span></span>  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a><span data-ttu-id="ef931-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="ef931-107">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ef931-108">Geçerli tüm değerlerin listesi.</span><span class="sxs-lookup"><span data-stu-id="ef931-108">Any valid list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef931-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="ef931-109">Return Value</span></span>  
 <span data-ttu-id="ef931-110">MULTISET türünden bir koleksiyona\<T >.</span><span class="sxs-lookup"><span data-stu-id="ef931-110">A collection of type MULTISET\<T>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef931-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ef931-111">Remarks</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="ef931-112">üç tür oluşturucular sağlar: satır Oluşturucular, nesne oluşturucuları ve multiset (veya koleksiyon) oluşturucular.</span><span class="sxs-lookup"><span data-stu-id="ef931-112"> provides three kinds of constructors: row constructors, object constructors, and multiset (or collection) constructors.</span></span> <span data-ttu-id="ef931-113">Daha fazla bilgi için bkz: [oluşturma türleri](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ef931-113">For more information, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
 <span data-ttu-id="ef931-114">Çok kümeli Oluşturucusu değerler listesinden bir çoklu küme örneği oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ef931-114">The multiset constructor creates an instance of a multiset from a list of values.</span></span> <span data-ttu-id="ef931-115">Oluşturucu tüm değerleri uyumlu bir türü olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ef931-115">All the values in the constructor must be of a compatible type.</span></span>  
  
 <span data-ttu-id="ef931-116">Örneğin, aşağıdaki ifade tamsayıların çoklu küme oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ef931-116">For example, the following expression creates a multiset of integers.</span></span>  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
>  <span data-ttu-id="ef931-117">İç içe geçmiş çok kümeli değişmez değerler, yalnızca tek bir çok kümeli öğe kaydırma mutiset sahip olduğunda desteklenir; Örneğin, `{{1, 2, 3}}`.</span><span class="sxs-lookup"><span data-stu-id="ef931-117">Nested multiset literals are only supported when a wrapping mutiset has a single multiset element; for example, `{{1, 2, 3}}`.</span></span> <span data-ttu-id="ef931-118">Birden çok çok kümeli öğe kaydırma multiset sahip olduğunda (örneğin, `{{1, 2}, {3, 4}}`), iç içe geçmiş çok kümeli değişmez değerler desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="ef931-118">When the wrapping multiset has multiple multiset elements (for example, `{{1, 2}, {3, 4}}`), nested multiset literals are not supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef931-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="ef931-119">Example</span></span>  
 <span data-ttu-id="ef931-120">Aşağıdaki varlık SQL sorgusu MULTISET işleci değerler listesinden bir çoklu küme örneği oluşturmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="ef931-120">The following Entity SQL query uses the MULTISET operator to create an instance of a multiset from a list of values.</span></span> <span data-ttu-id="ef931-121">Sorgu AdventureWorks satış modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="ef931-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ef931-122">Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="ef931-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ef931-123">Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ef931-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ef931-124">Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="ef931-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a><span data-ttu-id="ef931-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ef931-125">See Also</span></span>  
 [<span data-ttu-id="ef931-126">Türleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="ef931-126">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [<span data-ttu-id="ef931-127">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="ef931-127">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)