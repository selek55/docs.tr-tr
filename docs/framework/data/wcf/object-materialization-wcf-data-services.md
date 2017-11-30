---
title: Nesne Materialization (WCF Veri Hizmetleri)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, querying
ms.assetid: f0dbf7b0-0292-4e31-9ae4-b98288336dc1
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f671d3b41e0812916d1db342c211f2db6456ede3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="object-materialization-wcf-data-services"></a><span data-ttu-id="c4fb1-102">Nesne Materialization (WCF Veri Hizmetleri)</span><span class="sxs-lookup"><span data-stu-id="c4fb1-102">Object Materialization (WCF Data Services)</span></span>
<span data-ttu-id="c4fb1-103">Kullandığınızda **hizmet Başvurusu Ekle** iletişim kullanmak için bir [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] bir .NET Framework tabanlı istemci uygulamasında akış, eşdeğer veri sınıfları için akış tarafından kullanıma sunulan veri modelindeki her bir varlık türü oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-103">When you use the **Add Service Reference** dialog to consume an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in a .NET Framework-based client application, equivalent data classes are generated for each entity type in the data model exposed by the feed.</span></span> <span data-ttu-id="c4fb1-104">Daha fazla bilgi için bkz: [veri hizmeti istemci kitaplığı oluşturma](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4fb1-104">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span> <span data-ttu-id="c4fb1-105">Bir sorgu tarafından döndürülen varlık verilerini bu oluşturulan istemci veri hizmeti sınıfları birinin bir örneğine gerçekleştirildiği.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-105">Entity data that is returned by a query is materialized into an instance of one of these generated client data service classes.</span></span> <span data-ttu-id="c4fb1-106">Birleştirme seçeneklerini ve izlenen nesneler için kimlik çözümleme hakkında daha fazla bilgi için bkz: [veri Hizmet bağlamı yönetme](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4fb1-106">For information about merge options and identity resolution for tracked objects, see [Managing the Data Service Context](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="c4fb1-107">Ayrıca, aracı tarafından oluşturulan veri sınıflarını kullanmak yerine, kendi istemci veri hizmeti sınıfları tanımlamanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-107"> also enables you to define your own client data service classes rather than using the tool-generated data classes.</span></span> <span data-ttu-id="c4fb1-108">Bu, kendi veri sınıfları olarak da bilinen "düz eski CLR nesnesi" kullanmanızı sağlar (POCO) veri sınıfları.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-108">This enables you to use your own data classes, also known as "plain-old CLR object" (POCO) data classes.</span></span> <span data-ttu-id="c4fb1-109">Bu tür özel veri sınıflarını kullanırken ya da veri sınıfı özniteliği <xref:System.Data.Services.Common.DataServiceKeyAttribute> veya <xref:System.Data.Services.Common.DataServiceEntityAttribute> ve türü veri hizmetinin veri modelindeki istemci eşleşme türü adları adları emin olun.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-109">When using these types of custom data classes, you should attribute the data class with either <xref:System.Data.Services.Common.DataServiceKeyAttribute> or <xref:System.Data.Services.Common.DataServiceEntityAttribute> and ensure that type names on the client match type names in the data model of the data service.</span></span>  
  
 <span data-ttu-id="c4fb1-110">Kitaplık sorgu yanıt iletisini aldıktan sonra döndürülen veriler gerçeğe [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] istemci verilerini örneğine sorgu türlerinin hizmet sınıfları akış.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-110">After the library receives the query response message, it materializes the returned data from the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed into instances of client data service classes that are of the type of the query.</span></span> <span data-ttu-id="c4fb1-111">Bu nesneler gerçekleştirilmesini için genel işlem aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="c4fb1-111">The general process for materializing these objects is as follows:</span></span>  
  
1.  <span data-ttu-id="c4fb1-112">İstemci Kitaplığı serileştirilmiş türünden okur `entry` akış yanıt iletisi ve doğru türde yeni bir örneğini aşağıdaki yollardan biriyle oluşturma denemesi öğesinde:</span><span class="sxs-lookup"><span data-stu-id="c4fb1-112">The client library reads the serialized type from the `entry` element in the response message feed and attempts to create a new instance of the correct type, in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="c4fb1-113">Ne zaman akışın türü bildirilmedi türü aynı ada sahip <xref:System.Data.Services.Client.DataServiceQuery%601>, bu tür yeni bir örneğini boş Oluşturucusu kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-113">When the type declared in the feed has the same name as the type of the <xref:System.Data.Services.Client.DataServiceQuery%601>, a new instance of this type is created by using the empty constructor.</span></span>  
  
    -   <span data-ttu-id="c4fb1-114">Ne zaman akışın türü bildirilmedi türünden türetilmiş bir tür aynı ada sahip <xref:System.Data.Services.Client.DataServiceQuery%601>, bu türetilmiş türü yeni bir örneğini boş Oluşturucusu kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-114">When the type declared in the feed has the same name as a type that is derived from the type of the <xref:System.Data.Services.Client.DataServiceQuery%601>, a new instance of this derived type is created by using the empty constructor.</span></span>  
  
    -   <span data-ttu-id="c4fb1-115">Ne zaman akışın türü bildirilmedi türüne eşleştirilemiyor <xref:System.Data.Services.Client.DataServiceQuery%601> veya herhangi bir türetilmiş türler, sorgulanan türü yeni bir örneğini boş Oluşturucusu kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-115">When the type declared in the feed cannot be matched to the type of the <xref:System.Data.Services.Client.DataServiceQuery%601> or any derived types, a new instance of the queried type is created by using the empty constructor.</span></span>  
  
    -   <span data-ttu-id="c4fb1-116">Zaman <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A> özelliği ayarlanmışsa, varsayılan ad tabanlı tür eşlemesi ve tarafından döndürülen türü yeni bir örneğini geçersiz kılmak için sağlanan temsilci çağrılır <xref:System.Func%602> bunun yerine oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-116">When the <xref:System.Data.Services.Client.DataServiceContext.ResolveType%2A> property is set, the supplied delegate is called to override the default name-based type mapping and a new instance of the type returned by the <xref:System.Func%602> is created instead.</span></span> <span data-ttu-id="c4fb1-117">Bu temsilci boş bir değer döndürürse, sorgulanan türü yeni bir örneğini yerine oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-117">If this delegate returns a null value, a new instance of the queried type is created instead.</span></span> <span data-ttu-id="c4fb1-118">Devralma senaryoları desteklemek için varsayılan ad tabanlı türü adı eşlemesi geçersiz kılmak için gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-118">It may be required to override the default name-based type name mapping to support inheritance scenarios.</span></span>  
  
2.  <span data-ttu-id="c4fb1-119">URI değerinin istemci kitaplığı okur `id` öğesinin `entry`, varlık kimlik değeri olduğu.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-119">The client library reads the URI value from the `id` element of the `entry`, which is the identity value of the entity.</span></span> <span data-ttu-id="c4fb1-120">Sürece bir <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> değerini <xref:System.Data.Services.Client.MergeOption.NoTracking> olan kullanıldığında, kimlik değeri nesnesinde izlemek için kullanılan <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-120">Unless a <xref:System.Data.Services.Client.DataServiceContext.MergeOption%2A> value of <xref:System.Data.Services.Client.MergeOption.NoTracking> is used, the identity value is used to track the object in the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c4fb1-121">Kimlik değerini de bile bir varlık birden çok kez sorgu yanıtta döndürülen yalnızca tek bir varlık örneği, oluşturulduğunda olduğunu güvence altına almak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-121">The identity value is also used to guarantee that only a single entity instance is created, even when an entity is returned multiple times in the query response.</span></span>  
  
3.  <span data-ttu-id="c4fb1-122">İstemci Kitaplığı akış girdisinden Özellikleri'ni okur ve yeni oluşturulan bir nesne üzerinde karşılık gelen özelliklerini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-122">The client library reads properties from the feed entry and set the corresponding properties on the newly created object.</span></span> <span data-ttu-id="c4fb1-123">Zaten aynı kimlik değeri olan bir nesneyi oluştuğunda <xref:System.Data.Services.Client.DataServiceContext>, özellikleri temel alınarak ayarlanır <xref:System.Data.Services.Client.MergeOption> ayarıyla <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-123">When an object that has the same identity value already occurs in the <xref:System.Data.Services.Client.DataServiceContext>, the properties are set based on the <xref:System.Data.Services.Client.MergeOption> setting of the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c4fb1-124">Yanıt karşılık gelen özelliği istemci türünde oluşmaz özellik değerleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-124">The response might contain property values for which a corresponding property does not occur in the client type.</span></span> <span data-ttu-id="c4fb1-125">Bu durumda, eylem değerine bağlıdır <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> özelliği <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-125">When this occurs, the action depends on the value of the <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> property of the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c4fb1-126">Bu özellik ayarlandığında `true`, eksik özellik yok sayılır.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-126">When this property is set to `true`, the missing property is ignored.</span></span> <span data-ttu-id="c4fb1-127">Aksi takdirde bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-127">Otherwise, an error is raised.</span></span> <span data-ttu-id="c4fb1-128">Özellikler aşağıdaki gibi ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="c4fb1-128">Properties are set as follows:</span></span>  
  
    -   <span data-ttu-id="c4fb1-129">Skaler özellikler yanıt iletisi girdisinde karşılık gelen değere ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-129">Scalar properties are set to the corresponding value in the entry in the response message.</span></span>  
  
    -   <span data-ttu-id="c4fb1-130">Karmaşık özellikleri karmaşık tür özellikleri ile yanıttan ayarlanan yeni bir karmaşık tür örneğine ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-130">Complex properties are set to a new complex type instance, which are set with the properties of the complex type from the response.</span></span>  
  
    -   <span data-ttu-id="c4fb1-131">İlgili varlık koleksiyonu döndüren bir gezinti özellikleri bir yeni veya var olan örneğine ayarlanmış <xref:System.Collections.Generic.ICollection%601>, burada `T` ilgili varlık türü değil.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-131">Navigation properties that return a collection of related entities are set to a new or existing instance of <xref:System.Collections.Generic.ICollection%601>, where `T` is the type of the related entity.</span></span> <span data-ttu-id="c4fb1-132">İlişkili nesneleri içine yüklemiş olduğunuz sürece bu koleksiyonu boş olan <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-132">This collection is empty unless the related objects have been loaded into the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c4fb1-133">Daha fazla bilgi için bkz: [ertelenmiş içerik yüklenirken](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4fb1-133">For more information, see [Loading Deferred Content](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c4fb1-134">Oluşturulan istemci veri sınıfları veri bağlamayı destekleyen, gezinti özellikleri örneklerini döndürür <xref:System.Data.Services.Client.DataServiceCollection%601> yerine sınıfı.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-134">When the generated client data classes support data binding, navigation properties return instances of the <xref:System.Data.Services.Client.DataServiceCollection%601> class instead.</span></span> <span data-ttu-id="c4fb1-135">Daha fazla bilgi için bkz: [denetimlere veri bağlama](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4fb1-135">For more information, see [Binding Data to Controls](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).</span></span>  
  
4.  <span data-ttu-id="c4fb1-136"><xref:System.Data.Services.Client.DataServiceContext.ReadingEntity> Olayı oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-136">The <xref:System.Data.Services.Client.DataServiceContext.ReadingEntity> event is raised.</span></span>  
  
5.  <span data-ttu-id="c4fb1-137">İstemci Kitaplığı nesneye ekler <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-137">The client library attaches the object to the <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="c4fb1-138">Nesne değil ne zaman bağlı <xref:System.Data.Services.Client.MergeOption> olan <xref:System.Data.Services.Client.MergeOption.NoTracking>.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-138">The object is not attached when the <xref:System.Data.Services.Client.MergeOption> is <xref:System.Data.Services.Client.MergeOption.NoTracking>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fb1-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c4fb1-139">See Also</span></span>  
 [<span data-ttu-id="c4fb1-140">Veri Hizmeti sorgulama</span><span class="sxs-lookup"><span data-stu-id="c4fb1-140">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [<span data-ttu-id="c4fb1-141">Sorgu projeksiyonu</span><span class="sxs-lookup"><span data-stu-id="c4fb1-141">Query Projections</span></span>](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md)