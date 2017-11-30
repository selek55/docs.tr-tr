---
title: "İzlenecek yol: Tür Sağlayıcılarını Kullanarak OData Hizmetine Erişim (F#)"
description: "Bir OData hizmeti için istemci türleri oluşturmak için F # 3. 0'f # ODataService türü sağlayıcısı kullanmayı öğrenin ve hizmet, veri akışlarını sorgu sağlar."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0adae84c-b0fa-455f-994b-274ecdc6df30
ms.openlocfilehash: 28c2e9a405670f4e5f9512e99e0e6c3e3082856c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-an-odata-service-by-using-type-providers"></a><span data-ttu-id="c48bf-104">İzlenecek yol: Tür Sağlayıcılarını Kullanarak OData Hizmetine Erişim</span><span class="sxs-lookup"><span data-stu-id="c48bf-104">Walkthrough: Accessing an OData Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="c48bf-105">Bu kılavuz, F # 3.0 için yazılmıştır ve güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="c48bf-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="c48bf-106">Bkz: [FSharp.Data](http://fsharp.github.io/FSharp.Data/) güncel, platformlar arası tür sağlayıcıları için.</span><span class="sxs-lookup"><span data-stu-id="c48bf-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="c48bf-107">API başvuru bağlantılar için MSDN götürür.</span><span class="sxs-lookup"><span data-stu-id="c48bf-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="c48bf-108">Docs.microsoft.com API Başvurusu tamamlanmadı.</span><span class="sxs-lookup"><span data-stu-id="c48bf-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="c48bf-109">Açık Veri Protokolü, yani OData Internet üzerinden veri aktarımı için bir protokoldür.</span><span class="sxs-lookup"><span data-stu-id="c48bf-109">OData, meaning Open Data Protocol, is a protocol for transferring data over the Internet.</span></span> <span data-ttu-id="c48bf-110">Birçok veri sağlayıcısı, bir OData web hizmetini yayımlayarak verilerine erişimi kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="c48bf-110">Many data providers expose access to their data by publishing an OData web service.</span></span> <span data-ttu-id="c48bf-111">F # veri türleri kullanılarak otomatik olarak oluşturulan 3.0 içinde herhangi bir OData kaynaktan veri erişim `ODataService` türü sağlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="c48bf-111">You can access data from any OData source in F# 3.0 using data types that are automatically generated by the `ODataService` type provider.</span></span> <span data-ttu-id="c48bf-112">Https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62 OData hakkında daha fazla bilgi için bkz.</span><span class="sxs-lookup"><span data-stu-id="c48bf-112">For more information about OData, see https://msdn.microsoft.com/library/da3380cc-f6da-4c6c-bdb2-bb86afa59d62.</span></span>

<span data-ttu-id="c48bf-113">Bu kılavuzda F # ODataService türü sağlayıcısı bir OData hizmeti için istemci türleri oluşturmak için nasıl kullanılacağını gösterir ve hizmet, veri akışlarını sorgu sağlar.</span><span class="sxs-lookup"><span data-stu-id="c48bf-113">This walkthrough shows you how to use the F# ODataService type provider to generate client types for an OData service and query data feeds that the service provides.</span></span>

<span data-ttu-id="c48bf-114">Bu izlenecek yol, başarılı olması için bu sırayla gerçekleştirmeniz gereken aşağıdaki görevleri gösterir:</span><span class="sxs-lookup"><span data-stu-id="c48bf-114">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="c48bf-115">İstemci projesi bir OData hizmeti için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="c48bf-115">Configuring a client project for an OData service</span></span>
<br />

- <span data-ttu-id="c48bf-116">OData türlerini erişme</span><span class="sxs-lookup"><span data-stu-id="c48bf-116">Accessing OData types</span></span>
<br />

- <span data-ttu-id="c48bf-117">Bir OData hizmet sorgulama</span><span class="sxs-lookup"><span data-stu-id="c48bf-117">Querying an OData service</span></span>
<br />

- <span data-ttu-id="c48bf-118">OData istekleri doğrulanıyor</span><span class="sxs-lookup"><span data-stu-id="c48bf-118">Verifying the OData requests</span></span>
<br />


## <a name="configuring-a-client-project-for-an-odata-service"></a><span data-ttu-id="c48bf-119">İstemci projesi bir OData hizmeti için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="c48bf-119">Configuring a client project for an OData service</span></span>
<span data-ttu-id="c48bf-120">Bu adımda, bir OData türü sağlayıcısı kullanmak için bir projesi ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c48bf-120">In this step, you set up a project to use an OData type provider.</span></span>


#### <a name="to-configure-a-client-project-for-an-odata-service"></a><span data-ttu-id="c48bf-121">Bir OData hizmeti için bir istemci projesi yapılandırmak için</span><span class="sxs-lookup"><span data-stu-id="c48bf-121">To configure a client project for an OData service</span></span>

- <span data-ttu-id="c48bf-122">F # konsol uygulaması projesini açın ve ardından bir başvuru ekleyin `System.Data.Services.Client` Framework derleme.</span><span class="sxs-lookup"><span data-stu-id="c48bf-122">Open an F# Console Application project, and then add a reference to the `System.Data.Services.Client` Framework assembly.</span></span>
<br />

- <span data-ttu-id="c48bf-123">Altında `Extensions`, bir başvuru ekleyin `FSharp.Data.TypeProviders` derleme.</span><span class="sxs-lookup"><span data-stu-id="c48bf-123">Under `Extensions`, add a reference to the `FSharp.Data.TypeProviders` assembly.</span></span>
<br />

## <a name="accessing-odata-types"></a><span data-ttu-id="c48bf-124">OData türlerini erişme</span><span class="sxs-lookup"><span data-stu-id="c48bf-124">Accessing OData types</span></span>
<span data-ttu-id="c48bf-125">Bu adımda, erişim sağlayan türleri ve verileri bir OData hizmeti için tür sağlayıcısı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="c48bf-125">In this step, you create a type provider that provides access to the types and data for an OData service.</span></span>


#### <a name="to-access-odata-types"></a><span data-ttu-id="c48bf-126">OData türlerini erişmek için</span><span class="sxs-lookup"><span data-stu-id="c48bf-126">To access OData types</span></span>

- <span data-ttu-id="c48bf-127">Kod Düzenleyicisi'nde, bir F # kaynak dosyasını açın ve aşağıdaki kodu girin.</span><span class="sxs-lookup"><span data-stu-id="c48bf-127">In the Code Editor, open an F# source file, and enter the following code.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type Northwind = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">

let db = Northwind.GetDataContext()
let fullContext = Northwind.ServiceTypes.NorthwindEntities()
```

<span data-ttu-id="c48bf-128">Bu örnekte, F # tür sağlayıcısı çağrılır ve belirttiğiniz OData URI'SİNİN temel türleri kümesi oluşturmak üzere talimat.</span><span class="sxs-lookup"><span data-stu-id="c48bf-128">In this example, you have invoked the F# type provider and instructed it to create a set of types that are based on the OData URI that you specified.</span></span> <span data-ttu-id="c48bf-129">İki nesne kullanılabilir; verileri hakkında bilgiler içerir Basitleştirilmiş veri bağlamı biridir `db` örnekte.</span><span class="sxs-lookup"><span data-stu-id="c48bf-129">Two objects are available that contain information about the data; one is a simplified data context, `db` in the example.</span></span> <span data-ttu-id="c48bf-130">Bu nesne türleri tablolar veya akışları için içeren veritabanı ile ilişkili yalnızca veri türlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="c48bf-130">This object contains only the data types that are associated with the database, which include types for tables or feeds.</span></span> <span data-ttu-id="c48bf-131">Başka bir nesneyle `fullContext` Bu örnekte, bir örneğidir `System.Data.Linq.DataContext` ve birçok ek özellikler, yöntemleri ve olayları içerir.</span><span class="sxs-lookup"><span data-stu-id="c48bf-131">The other object, `fullContext` in this example, is an instance of `System.Data.Linq.DataContext` and contains many additional properties, methods, and events.</span></span>
<br />


## <a name="querying-an-odata-service"></a><span data-ttu-id="c48bf-132">Bir OData hizmet sorgulama</span><span class="sxs-lookup"><span data-stu-id="c48bf-132">Querying an OData service</span></span>
<span data-ttu-id="c48bf-133">Bu adımda, OData hizmeti sorgulamak için F # sorgu ifadeleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="c48bf-133">In this step, you use F# query expressions to query the OData service.</span></span>


#### <a name="to-query-an-odata-service"></a><span data-ttu-id="c48bf-134">Bir OData hizmeti sorgulamak için</span><span class="sxs-lookup"><span data-stu-id="c48bf-134">To query an OData service</span></span>

1. <span data-ttu-id="c48bf-135">Türü Sağlayıcısı'nı ayarladığımıza göre OData hizmetine sorgulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c48bf-135">Now that you've set up the type provider, you can query an OData service.</span></span>
<br />  <span data-ttu-id="c48bf-136">OData yalnızca bir alt kümesini kullanılabilir sorgu işlemleri destekler.</span><span class="sxs-lookup"><span data-stu-id="c48bf-136">OData supports only a subset of the available query operations.</span></span> <span data-ttu-id="c48bf-137">Aşağıdaki işlemleri ve bunların karşılık gelen anahtar sözcükleri desteklenir:</span><span class="sxs-lookup"><span data-stu-id="c48bf-137">The following operations and their corresponding keywords are supported:</span></span>
<br />
  - <span data-ttu-id="c48bf-138">projeksiyon (`select`)</span><span class="sxs-lookup"><span data-stu-id="c48bf-138">projection (`select`)</span></span>
<br />

  - <span data-ttu-id="c48bf-139">Filtreleme (`where`, göre dizesi kullanılarak tarih ve işlemler)</span><span class="sxs-lookup"><span data-stu-id="c48bf-139">filtering (`where`, by using string and date operations)</span></span>
<br />

  - <span data-ttu-id="c48bf-140">disk belleği (`skip`, `take`)</span><span class="sxs-lookup"><span data-stu-id="c48bf-140">paging (`skip`, `take`)</span></span>
<br />

  - <span data-ttu-id="c48bf-141">Sıralama (`orderBy`, `thenBy`)</span><span class="sxs-lookup"><span data-stu-id="c48bf-141">ordering (`orderBy`, `thenBy`)</span></span>
<br />

  - <span data-ttu-id="c48bf-142">`AddQueryOption`ve `Expand`, OData özel işlemler olduğu</span><span class="sxs-lookup"><span data-stu-id="c48bf-142">`AddQueryOption` and `Expand`, which are OData-specific operations</span></span>
<br />

  <span data-ttu-id="c48bf-143">Daha fazla bilgi için bkz: [LINQ konuları &#40; WCF Veri Hizmetleri &#41; ](https://msdn.microsoft.com/library/ee622463.aspx).</span><span class="sxs-lookup"><span data-stu-id="c48bf-143">For more information, see [LINQ Considerations &#40;WCF Data Services&#41;](https://msdn.microsoft.com/library/ee622463.aspx).</span></span>
<br />  <span data-ttu-id="c48bf-144">Tüm girişleri akış veya tablosunda istiyorsanız, aşağıdaki kod olduğu gibi sorgu ifadesi en basit biçimi kullanın:</span><span class="sxs-lookup"><span data-stu-id="c48bf-144">If you want all of the entries in a feed or table, use the simplest form of the query expression, as in the following code:</span></span>
<br />

```fsharp
query {
  for customer in db.Customers do
  select customer
} |> Seq.iter (fun customer ->
                  printfn "ID: %s\nCompany: %s" customer.CustomerID customer.CompanyName
                  printfn "Contact: %s\nAddress: %s" customer.ContactName customer.Address
                  printfn "         %s, %s %s" customer.City customer.Region customer.PostalCode
                  printfn "%s\n" customer.Phone)
```

2. <span data-ttu-id="c48bf-145">Alanları veya select anahtar sözcüğünden sonra bir tanımlama grubu kullanarak istediğiniz sütunları belirtin.</span><span class="sxs-lookup"><span data-stu-id="c48bf-145">Specify the fields or columns that you want by using a tuple after the select keyword.</span></span>
<br />

```fsharp
  query { 
    for cat in db.Categories do
    select (cat.CategoryID, cat.CategoryName, cat.Description)
  } |> Seq.iter (fun (id, name, description) ->
                    printfn "ID: %d\nCategory: %s\nDescription: %s\n" id name description)
```

3. <span data-ttu-id="c48bf-146">Koşullar kullanarak belirttiğiniz bir `where` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="c48bf-146">Specify conditions by using a `where` clause.</span></span>
<br />

```fsharp
query {
  for employee in db.Employees do
  where (employee.EmployeeID = 9)
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

4. <span data-ttu-id="c48bf-147">Sorgu için bir alt dize koşulu kullanarak belirtin `System.String.Contains(System.String)` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="c48bf-147">Specify a substring condition to the query by using the `System.String.Contains(System.String)` method.</span></span> <span data-ttu-id="c48bf-148">Aşağıdaki sorgu adlarında "Chef" olan tüm ürünleri verir.</span><span class="sxs-lookup"><span data-stu-id="c48bf-148">The following query returns all products that have "Chef" in their names.</span></span> <span data-ttu-id="c48bf-149">Ayrıca kullanımını fark `System.Nullable<'T>.GetValueOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="c48bf-149">Also notice the use of `System.Nullable<'T>.GetValueOrDefault()`.</span></span> <span data-ttu-id="c48bf-150">`UnitPrice` Kullanarak ya da değeri almalısınız bir boş değer atanabilir değer olduğundan `Value` özelliği veya çağırmalıdır `System.Nullable<'T>.GetValueOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="c48bf-150">The `UnitPrice` is a nullable value, so you must either get the value by using the `Value` property, or you must call `System.Nullable<'T>.GetValueOrDefault()`.</span></span>
<br />

```fsharp
query { 
  for product in db.Products do
  where (product.ProductName.Contains("Chef"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

5. <span data-ttu-id="c48bf-151">Kullanım `System.String.EndsWith(System.String)` bir dizeyi belirli bir dizeyle sona ereceğini belirtmek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="c48bf-151">Use the `System.String.EndsWith(System.String)` method to specify that a string ends with a certain substring.</span></span>
<br />

```fsharp
query {
  for product in db.Products do
  where (product.ProductName.EndsWith("u"))
  select product
} |> Seq.iter (fun product ->
                  printfn "ID: %d Product: %s" product.ProductID product.ProductName
                  printfn "Price: %M\n" (product.UnitPrice.GetValueOrDefault()))
```

6. <span data-ttu-id="c48bf-152">Koşulları birleştirmek bir where yan tümcesini kullanarak `&&` işleci.</span><span class="sxs-lookup"><span data-stu-id="c48bf-152">Combine conditions in a where clause by using the `&&` operator.</span></span>
<br />

```fsharp
// Open this module to use the nullable operators ?> and ?<.
open Microsoft.FSharp.Linq.NullableOperators

let salesIn1997 = query { 
  for sales in db.Category_Sales_for_1997 do
  where (sales.CategorySales ?> 50000.00M && sales.CategorySales ?< 60000.0M)
  select sales }

salesIn1997
|> Seq.iter (fun sales ->
                printfn "Category: %s Sales: %M" sales.CategoryName (sales.CategorySales.GetValueOrDefault()))
```

<span data-ttu-id="c48bf-153">İşleçler `?>` ve `?<` boş değer atanabilir işleçler.</span><span class="sxs-lookup"><span data-stu-id="c48bf-153">The operators `?>` and `?<` are nullable operators.</span></span> <span data-ttu-id="c48bf-154">Boş değer atanabilir eşitlik ve Karşılaştırma işleçleri tam kümesini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c48bf-154">You can use a full set of nullable equality and comparison operators.</span></span> <span data-ttu-id="c48bf-155">Daha fazla bilgi için bkz: [Linq.NullableOperators Modülü](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="c48bf-155">For more information, see [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span>
<br />

7. <span data-ttu-id="c48bf-156">Kullanmak `sortBy` sorgu işleci sıralamasını belirtmek ve kullanmak `thenBy` sıralama başka bir düzeyini belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="c48bf-156">Use the `sortBy` query operator to specify ordering, and use `thenBy` to specify another level of ordering.</span></span> <span data-ttu-id="c48bf-157">Ayrıca bir tanımlama grubu sorgu select bölümünde kullanımına dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="c48bf-157">Notice also the use of a tuple in the select part of the query.</span></span> <span data-ttu-id="c48bf-158">Bu nedenle, sorgu bir tanımlama grubu bir öğe türüne sahip.</span><span class="sxs-lookup"><span data-stu-id="c48bf-158">Therefore, the query has a tuple as an element type.</span></span>
<br />

```fsharp
printfn "Freight for some orders: "

query { 
  for order in db.Orders do
  sortBy (order.OrderDate.Value)
  thenBy (order.OrderID)
  select (order.OrderDate, order.OrderID, order.Customer.CompanyName)
} |> Seq.iter (fun (orderDate, orderID, company) ->
                  printfn "OrderDate: %s" (orderDate.GetValueOrDefault().ToString())
                  printfn "OrderID: %d Company: %s\n" orderID company)
```

8. <span data-ttu-id="c48bf-159">Atla işlecini kullanarak belirli bir kayıt sayısı yoksay ve döndürmek için kayıt sayısını belirtmek için Al işlecini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c48bf-159">Ignore a specified number of records by using the skip operator, and use the take operator to specify a number of records to return.</span></span> <span data-ttu-id="c48bf-160">Bu şekilde, disk belleği veri akışları uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c48bf-160">In this way, you can implement paging on data feeds.</span></span>
<br />

```fsharp
printfn "Get the first page of 2 employees."

query { 
  for employee in db.Employees do
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID)) 

printfn "Get the next 2 employees."

query { 
  for employee in db.Employees do
  skip 2
  take 2
  select employee
} |> Seq.iter (fun employee ->
                  printfn "Name: %s ID: %d" (employee.FirstName + " " + employee.LastName) (employee.EmployeeID))
```

## <a name="verifying-the-odata-request"></a><span data-ttu-id="c48bf-161">OData isteği doğrulama</span><span class="sxs-lookup"><span data-stu-id="c48bf-161">Verifying the OData request</span></span>
<span data-ttu-id="c48bf-162">Tüm OData sorgu belirli bir OData isteği URI çevrilir.</span><span class="sxs-lookup"><span data-stu-id="c48bf-162">Every OData query is translated into a specific OData request URI.</span></span> <span data-ttu-id="c48bf-163">URI, belki de hata ayıklama için bir olay işleyicisi ekleyerek amacıyla olduğunu doğrulayabilirsiniz `SendingRequest` tam veri context nesnesinde olay.</span><span class="sxs-lookup"><span data-stu-id="c48bf-163">You can verify that URI, perhaps for debugging purposes, by adding an event handler to the `SendingRequest` event on the full data context object.</span></span>


#### <a name="to-verify-the-odata-request"></a><span data-ttu-id="c48bf-164">OData isteği doğrulamak için</span><span class="sxs-lookup"><span data-stu-id="c48bf-164">To verify the OData request</span></span>

- <span data-ttu-id="c48bf-165">OData isteği URI doğrulamak için aşağıdaki kodu kullanın:</span><span class="sxs-lookup"><span data-stu-id="c48bf-165">To verify the OData request URI, use the following code:</span></span>
<br />

```fsharp
// The DataContext property returns the full data context.
db.DataContext.SendingRequest.Add (fun eventArgs -> printfn "Requesting %A" eventArgs.Request.RequestUri)
```

<span data-ttu-id="c48bf-166">Önceki kod çıktısı şöyledir:</span><span class="sxs-lookup"><span data-stu-id="c48bf-166">The output of the previous code is:</span></span>
<br />`requesting http://services.odata.org/Northwind/Northwind.svc/Orders()?$orderby=ShippedDate&amp;$select=OrderID,ShippedDate`


## <a name="see-also"></a><span data-ttu-id="c48bf-167">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c48bf-167">See Also</span></span>
[<span data-ttu-id="c48bf-168">Sorgu ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c48bf-168">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="c48bf-169">LINQ konuları (WCF Veri Hizmetleri)</span><span class="sxs-lookup"><span data-stu-id="c48bf-169">LINQ Considerations (WCF Data Services)</span></span>](https://msdn.microsoft.com/library/ee622463.aspx)

[<span data-ttu-id="c48bf-170">ODataService türü sağlayıcısı (F #)</span><span class="sxs-lookup"><span data-stu-id="c48bf-170">ODataService Type Provider (F#)</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/odataservice-type-provider-%5bfsharp%5d)