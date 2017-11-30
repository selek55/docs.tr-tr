---
title: "Varlık SQL dili"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 08e366e8bbd9df31f367496ca5e106b876921896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-language"></a><span data-ttu-id="2f6cf-102">Varlık SQL dili</span><span class="sxs-lookup"><span data-stu-id="2f6cf-102">Entity SQL Language</span></span>
<span data-ttu-id="2f6cf-103">Varlık SQL SQL benzer bir depolama bağımsız sorgu dildir.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="2f6cf-104">Varlık SQL sorgu bir varlığın verilerinin nesneler olarak veya bir tablo formunda sağlar.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="2f6cf-105">Varlık SQL aşağıdaki durumlarda kullanmayı düşünmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="2f6cf-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="2f6cf-106">Ne zaman bir sorgu çalışma zamanında dinamik olarak oluşturulması gerekir.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="2f6cf-107">Bu durumda, aynı zamanda sorgu oluşturucu yöntemleri kullanmayı düşünmelisiniz <xref:System.Data.Objects.ObjectQuery%601> Sorgu dizesinden çalışma zamanında bir varlık SQL oluşturmak yerine.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="2f6cf-108">Bir sorgu modelini tanımının bir parçası tanımlamak istediğinizde.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="2f6cf-109">Yalnızca varlık SQL veri modelinde desteklenir.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="2f6cf-110">Daha fazla bilgi için bkz: [QueryView öğesi (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span><span class="sxs-lookup"><span data-stu-id="2f6cf-110">For more information, see [QueryView Element (MSL)](http://msdn.microsoft.com/en-us/f0426b34-45cb-4fd7-9777-e0570c5e0e80)</span></span>  
  
-   <span data-ttu-id="2f6cf-111">EntityClient satır kümeleri kullanarak olarak salt okunur varlık verileri döndürmek için kullanılırken bir <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="2f6cf-112">Daha fazla bilgi için bkz: [EntityClient sağlayıcısı için Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="2f6cf-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="2f6cf-113">SQL tabanlı sorgu dillerde uzmanı zaten varsa, size en doğal varlık SQL gibi görünebilir.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="2f6cf-114">Varlık SQL EntityClient sağlayıcısı ile kullanma</span><span class="sxs-lookup"><span data-stu-id="2f6cf-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="2f6cf-115">Varlık SQL EntityClient sağlayıcısı ile kullanmak istiyorsanız, daha fazla bilgi için aşağıdaki konulara bakın:</span><span class="sxs-lookup"><span data-stu-id="2f6cf-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="2f6cf-116">Entity Framework için EntityClient sağlayıcısı</span><span class="sxs-lookup"><span data-stu-id="2f6cf-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="2f6cf-117">Nasıl yapılır: bir EntityConnection bağlantı dizesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="2f6cf-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="2f6cf-118">Nasıl yapılır: PrimitiveType sonuçları döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="2f6cf-119">Nasıl yapılır: StructuralType sonuçları döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="2f6cf-120">Nasıl yapılır: RefType sonuçları döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="2f6cf-121">Nasıl yapılır: karmaşık türleri döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="2f6cf-122">Nasıl yapılır: iç içe geçmiş koleksiyonları döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="2f6cf-123">Nasıl yapılır: EntityCommand kullanarak parametreli varlık SQL sorgusu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="2f6cf-124">Nasıl yapılır: EntityCommand kullanarak parametreli bir saklı yordamı yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="2f6cf-125">Nasıl yapılır: çok biçimli bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="2f6cf-126">Nasıl yapılır: ilişkileriyle gidin işleci gidin</span><span class="sxs-lookup"><span data-stu-id="2f6cf-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="2f6cf-127">Varlık SQL nesne sorgularıyla kullanma</span><span class="sxs-lookup"><span data-stu-id="2f6cf-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="2f6cf-128">Varlık SQL nesne sorgularıyla kullanmak istiyorsanız, daha fazla bilgi için aşağıdaki konulara bakın:</span><span class="sxs-lookup"><span data-stu-id="2f6cf-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="2f6cf-129">Nasıl yapılır: varlık türü nesnesi döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](http://msdn.microsoft.com/en-us/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="2f6cf-130">Nasıl yapılır: parametreleştirilmiş sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-130">How to: Execute a Parameterized Query</span></span>](http://msdn.microsoft.com/en-us/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="2f6cf-131">Nasıl yapılır: Gezinti özellikleri kullanarak ilişkiler gidin</span><span class="sxs-lookup"><span data-stu-id="2f6cf-131">How to: Navigate Relationships Using Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="2f6cf-132">Nasıl yapılır: bir kullanıcı tanımlı işlev çağrısı</span><span class="sxs-lookup"><span data-stu-id="2f6cf-132">How to: Call a User-Defined Function</span></span>](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="2f6cf-133">Nasıl yapılır: verileri filtreleme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-133">How to: Filter Data</span></span>](http://msdn.microsoft.com/en-us/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="2f6cf-134">Nasıl yapılır: verileri sıralama</span><span class="sxs-lookup"><span data-stu-id="2f6cf-134">How to: Sort Data</span></span>](http://msdn.microsoft.com/en-us/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="2f6cf-135">Nasıl yapılır: veri grubu</span><span class="sxs-lookup"><span data-stu-id="2f6cf-135">How to: Group Data</span></span>](http://msdn.microsoft.com/en-us/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="2f6cf-136">Nasıl yapılır: veri toplama</span><span class="sxs-lookup"><span data-stu-id="2f6cf-136">How to: Aggregate Data</span></span>](http://msdn.microsoft.com/en-us/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="2f6cf-137">Nasıl yapılır: Anonim türde nesne döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](http://msdn.microsoft.com/en-us/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="2f6cf-138">Nasıl yapılır: basit türler koleksiyonu döndüren bir sorgu yürütme</span><span class="sxs-lookup"><span data-stu-id="2f6cf-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](http://msdn.microsoft.com/en-us/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="2f6cf-139">Nasıl yapılır: bir Entitycollection'a ilgili nesneleri sorgulama</span><span class="sxs-lookup"><span data-stu-id="2f6cf-139">How to: Query Related Objects in an EntityCollection</span></span>](http://msdn.microsoft.com/en-us/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="2f6cf-140">Nasıl yapılır: iki sorguları birleşimi sipariş</span><span class="sxs-lookup"><span data-stu-id="2f6cf-140">How to: Order the Union of Two Queries</span></span>](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="2f6cf-141">Nasıl yapılır: sonuçları sorgu aracılığıyla sayfası</span><span class="sxs-lookup"><span data-stu-id="2f6cf-141">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="2f6cf-142">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="2f6cf-142">In This Section</span></span>  
 [<span data-ttu-id="2f6cf-143">Varlık SQL genel bakış</span><span class="sxs-lookup"><span data-stu-id="2f6cf-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="2f6cf-144">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="2f6cf-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f6cf-145">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2f6cf-145">See Also</span></span>  
 [<span data-ttu-id="2f6cf-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2f6cf-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="2f6cf-147">Dil Başvurusu</span><span class="sxs-lookup"><span data-stu-id="2f6cf-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)