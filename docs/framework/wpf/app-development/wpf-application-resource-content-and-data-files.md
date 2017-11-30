---
title: "WPF Uygulama Kaynağı, İçerik ve Veri Dosyaları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF application [WPF], files
- loose resources [WPF]
- content files [WPF]
- Site of Origin files [WPF]
- resource files [WPF]
- remote files [WPF]
- embedded resources [WPF]
- files [WPF]
- referencing application files [WPF]
- application development [WPF], files
- application management [WPF]
ms.assetid: 7ad2943b-3961-41d3-8fc6-1582d43f5d99
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 19fd82daabd5ed12776b2deee6bc850529a6ef23
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="fbb9b-102">WPF Uygulama Kaynağı, İçerik ve Veri Dosyaları</span><span class="sxs-lookup"><span data-stu-id="fbb9b-102">WPF Application Resource, Content, and Data Files</span></span>
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]<span data-ttu-id="fbb9b-103">uygulamalar genellikle gibi yürütülebilir olmayan veri içeren dosyaları bağımlı [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], resim, video ve ses.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-103"> applications often depend on files that contain non-executable data, such as [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], images, video, and audio.</span></span> [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="fbb9b-104">yapılandırma, tanımlayan ve bu tür bir uygulama verileri dosyaları adı verilen veri dosyalarını kullanmak için özel destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-104"> offers special support for configuring, identifying, and using these types of data files, which are called application data files.</span></span> <span data-ttu-id="fbb9b-105">Bu destek, uygulama verilerini dosya türleri dahil olmak üzere, belirli bir dizi döner:</span><span class="sxs-lookup"><span data-stu-id="fbb9b-105">This support revolves around a specific set of application data file types, including:</span></span>  
  
-   <span data-ttu-id="fbb9b-106">**Kaynak dosyaları**: bir yürütülebilir dosya veya kitaplık derlenmiş veri dosyaları [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] derleme.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-106">**Resource Files**: Data files that are compiled into either an executable or library [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
-   <span data-ttu-id="fbb9b-107">**İçerik dosyaları**: yürütülebilir bir dosya ile açık bir ilişkisi olmayan bağımsız veri dosyaları [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] derleme.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-107">**Content Files**: Standalone data files that have an explicit association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
-   <span data-ttu-id="fbb9b-108">**Kaynak dosyaları sitesi**: yürütülebilir bir dosya ile ilişkisi olmayan bağımsız veri dosyaları [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] derleme.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-108">**Site of Origin Files**: Standalone data files that have no association with an executable [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] assembly.</span></span>  
  
 <span data-ttu-id="fbb9b-109">Bu dosyaları üç türleri arasında yapmak için bir önemli fark, kaynak dosyaları ve içerik dosyalarının derleme zamanında bilinen olur; bir derleme bunların açık bilgisine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-109">One important distinction to make between these three types of files is that resource files and content files are known at build time; an assembly has explicit knowledge of them.</span></span> <span data-ttu-id="fbb9b-110">Kaynak dosyaları sitesi için Bununla birlikte, bir derlemeyi bunları olanağıyla hiç olabilir veya bir paketi aracılığıyla örtülü bilgisi [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] başvuru; durumunda İkincisi, kaynak dosya başvurulan sitesinin gerçekten var garantisi yoktur.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-110">For site of origin files, however, an assembly may have no knowledge of them at all, or implicit knowledge through a pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference; the case of the latter, there is no guarantee that the referenced site of origin file actually exists.</span></span>  
  
 <span data-ttu-id="fbb9b-111">Uygulama verileri dosyaları, başvurmak için [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] paketi kullanan [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] içinde ayrıntılı olarak açıklanmıştır düzeni [Pack URI WPF'de](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-111">To reference application data files, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] uses the Pack [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] Scheme, which is described in detail in [Pack URIs in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)).</span></span>  
  
 <span data-ttu-id="fbb9b-112">Bu konuda, yapılandırma ve uygulama verileri dosyaları kullanma açıklar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-112">This topic describes how to configure and use application data files.</span></span>  
  
  
<a name="Resource_Files"></a>   
## <a name="resource-files"></a><span data-ttu-id="fbb9b-113">Kaynak Dosyalar</span><span class="sxs-lookup"><span data-stu-id="fbb9b-113">Resource Files</span></span>  
 <span data-ttu-id="fbb9b-114">Uygulama veri dosyası her zaman bir uygulama için kullanılabilir olması durumunda kullanılabilirliğini garanti etmek için tek bir uygulamanın ana çalıştırılabilir bütünleştirilmiş koduna veya başvurulan bütünleştirilmiş derlemek için yoludur.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-114">If an application data file must always be available to an application, the only way to guarantee availability is to compile it into an application's main executable assembly or one of its referenced assemblies.</span></span> <span data-ttu-id="fbb9b-115">Bu tür bir uygulama veri dosyası olarak bilinen bir *kaynak dosyası*.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-115">This type of application data file is known as a *resource file*.</span></span>  
  
 <span data-ttu-id="fbb9b-116">Kaynak kullanması gereken zaman dosyaları:</span><span class="sxs-lookup"><span data-stu-id="fbb9b-116">You should use resource files when:</span></span>  
  
-   <span data-ttu-id="fbb9b-117">Bütünleştirilmiş koda derlenmemiş sonra kaynak dosyanın içeriğini güncelleştirmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-117">You don't need to update the resource file's content after it is compiled into an assembly.</span></span>  
  
-   <span data-ttu-id="fbb9b-118">Dosya bağımlılıkları sayısını azaltarak uygulama dağıtım karmaşıklığını basitleştirmek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-118">You want to simplify application distribution complexity by reducing the number of file dependencies.</span></span>  
  
-   <span data-ttu-id="fbb9b-119">Uygulama veri dosyasının yerelleştirilebilir olması gerekir (bkz [WPF Genelleştirme ve yerelleştirme genel bakış](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-119">Your application data file needs to be localizable (see [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-120">Bu bölümde açıklanan kaynak dosyaları kaynak dosyaları açıklanan farklı [XAML kaynakları](../../../../docs/framework/wpf/advanced/xaml-resources.md) ve açıklanan katıştırılmış veya bağlantılı kaynakları farklı [yönetme uygulama kaynakları (.NET) ](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-120">The resource files described in this section are different than the resource files described in [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) and different than the embedded or linked resources described in [Managing Application Resources (.NET)](http://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).</span></span>  
  
### <a name="configuring-resource-files"></a><span data-ttu-id="fbb9b-121">Kaynak dosyalarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-121">Configuring Resource Files</span></span>  
 <span data-ttu-id="fbb9b-122">İçinde [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], bir kaynak dosyası yer aldığı bir dosyadır bir [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] proje olarak bir `Resource` öğesi.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a resource file is a file that is included in an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as a `Resource` item.</span></span>  
  
```xml  
<Project "xmlns=http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Resource Include="ResourceFile.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-123">İçinde [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], bir dosyayı bir proje ve ayarı ekleyerek kaynak dosyası oluşturma kendi `Build Action` için `Resource`.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-123">In [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you create a resource file by adding a file to a project and setting its `Build Action` to `Resource`.</span></span>  
  
 <span data-ttu-id="fbb9b-124">Proje yapılandırıldığında [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] kaynak bütünleştirilmiş koda derler.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-124">When the project is built, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] compiles the resource into the assembly.</span></span>  
  
### <a name="using-resource-files"></a><span data-ttu-id="fbb9b-125">Kaynak dosyalarını kullanma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-125">Using Resource Files</span></span>  
 <span data-ttu-id="fbb9b-126">Kaynak dosyayı yüklemek için çağırabilirsiniz <xref:System.Windows.Application.GetResourceStream%2A> yöntemi <xref:System.Windows.Application> sınıfı, bir paketi geçirme [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] istenen kaynak dosyayı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-126">To load a resource file, you can call the <xref:System.Windows.Application.GetResourceStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired resource file.</span></span> <span data-ttu-id="fbb9b-127"><xref:System.Windows.Application.GetResourceStream%2A>döndüren bir <xref:System.Windows.Resources.StreamResourceInfo> olarak kaynak dosyayı sunan nesnesi bir <xref:System.IO.Stream> ve içerik türünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-127"><xref:System.Windows.Application.GetResourceStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the resource file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="fbb9b-128">Örnek olarak, aşağıdaki kodu nasıl kullanılacağını gösterir. <xref:System.Windows.Application.GetResourceStream%2A> yüklemek için bir <xref:System.Windows.Controls.Page> kaynak dosyasını ve içeriği olarak ayarlanmış bir <xref:System.Windows.Controls.Frame> (`pageFrame`):</span><span class="sxs-lookup"><span data-stu-id="fbb9b-128">As an example, the following code shows how to use <xref:System.Windows.Application.GetResourceStream%2A> to load a <xref:System.Windows.Controls.Page> resource file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`):</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadapageresourcefilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageResourceFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadapageresourcefilemanuallycode)]  
  
 <span data-ttu-id="fbb9b-129">Arama sırasında <xref:System.Windows.Application.GetResourceStream%2A> e erişmenizi <xref:System.IO.Stream>, ek iş, kendisiyle ayarlayacağınız özellik türüne dönüştürme gerçekleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-129">While calling <xref:System.Windows.Application.GetResourceStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="fbb9b-130">Bunun yerine, sağlayabilirsiniz [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] açma ve dönüştürme ilgilenebilmek <xref:System.IO.Stream> tarafından doğrudan kodu kullanarak tür özelliğine bir kaynak dosyası yükleniyor.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-130">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="fbb9b-131">Aşağıdaki örnekte nasıl yükleneceğini gösterir bir <xref:System.Windows.Controls.Page> doğrudan bir <xref:System.Windows.Controls.Frame> (`pageFrame`) kullanılarak kod.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-131">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.cs#loadpageresourcefilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml.vb#loadpageresourcefilefromcode)]  
  
 <span data-ttu-id="fbb9b-132">Aşağıdaki örnek biçimlendirmesi olan önceki örnekte eşdeğer.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-132">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageResourceFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetResourceStreamSnippetWindow.xaml#loadpageresourcefilefromxaml)]  
  
### <a name="application-code-files-as-resource-files"></a><span data-ttu-id="fbb9b-133">Kaynak dosyaları olarak uygulama kod dosyaları</span><span class="sxs-lookup"><span data-stu-id="fbb9b-133">Application Code Files as Resource Files</span></span>  
 <span data-ttu-id="fbb9b-134">Özel kümesi [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uygulama kod dosyaları paketi kullanarak başvurulabilir [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]windows, sayfalar, akış belgeleri ve kaynak sözlükleri dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-134">A special set of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application code files can be referenced using pack [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)], including windows, pages, flow documents, and resource dictionaries.</span></span> <span data-ttu-id="fbb9b-135">Örneğin, ayarlayabileceğiniz <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> özellik paketi ile [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] penceresi veya bir uygulama başlatıldığında yüklemek istediğiniz sayfa başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-135">For example, you can set the <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType> property with a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that references the window or page that you would like to load when an application starts.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#SetApplicationStartupURI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/App.xaml#setapplicationstartupuri)]  
  
 <span data-ttu-id="fbb9b-136">Olduğunda bunu bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosya dahil bir [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] proje olarak bir `Page` öğesi.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-136">You can do this when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is included in an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as a `Page` item.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Page Include="MainWindow.xaml" />  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-137">İçinde [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], yeni eklediğiniz <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, veya <xref:System.Windows.ResourceDictionary> bir proje `Build Action` için biçimlendirme dosya için varsayılan `Page`.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-137">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you add a new <xref:System.Windows.Window>, <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.FlowDocument>, or <xref:System.Windows.ResourceDictionary> to a project, the `Build Action` for the markup file will default to `Page`.</span></span>  
  
 <span data-ttu-id="fbb9b-138">Bir proje ile zaman `Page` öğeleri derlenmiş, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] öğeleri ikili biçime dönüştürülür ve ilişkili bütünleştirilmiş koda derlenir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-138">When a project with `Page` items is compiled, the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] items are converted to binary format and compiled into the associated assembly.</span></span> <span data-ttu-id="fbb9b-139">Sonuç olarak, bu dosyalar normal kaynak dosyaları aynı şekilde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-139">Consequently, these files can be used in the same way as typical resource files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-140">Varsa bir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosya olarak yapılandırılmış bir `Resource` öğesi ve ham, arka plan kodu dosyanın yok [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ham ikili sürümü yerine bir derleme derlenmiş [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbb9b-140">If a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is configured as a `Resource` item, and does not have a code-behind file, the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is compiled into an assembly rather than a binary version of the raw [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
<a name="Content_Files"></a>   
## <a name="content-files"></a><span data-ttu-id="fbb9b-141">İçerik dosyaları</span><span class="sxs-lookup"><span data-stu-id="fbb9b-141">Content Files</span></span>  
 <span data-ttu-id="fbb9b-142">A *içerik dosyası* çalıştırılabilir bir bütünleştirilmiş kodun yanında gevşek bir dosya olarak dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-142">A *content file* is distributed as a loose file alongside an executable assembly.</span></span> <span data-ttu-id="fbb9b-143">Bir bütünleştirilmiş koda derlenmemiş rağmen derlemeler her içerik dosyasının ile bir ilişki kurar meta verilerle derlenir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-143">Although they are not compiled into an assembly, assemblies are compiled with metadata that establishes an association with each content file.</span></span>  
  
 <span data-ttu-id="fbb9b-144">Uygulamanız, bunları tüketir derleme derlemeden güncelleştirebilmek istediğiniz uygulama verileri dosyaları belirli bir dizi gerektirdiğinde, içerik dosyaları kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-144">You should use content files when your application requires a specific set of application data files that you want to be able to update without recompiling the assembly that consumes them.</span></span>  
  
### <a name="configuring-content-files"></a><span data-ttu-id="fbb9b-145">İçerik dosyalarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-145">Configuring Content Files</span></span>  
 <span data-ttu-id="fbb9b-146">Bir içerik dosyası için bir proje eklemek için uygulama veri dosyası olarak dahil edilmelidir bir `Content` öğesi.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-146">To add a content file to a project, an application data file must be included as a `Content` item.</span></span> <span data-ttu-id="fbb9b-147">Bir içerik dosyası doğrudan bütünleştirilmiş koda derlenmemiş olduğundan, ayrıca, ayarlamanız gerekir [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` içerik dosyasını yerleşik bütünleştirilmiş göreli bir konuma kopyalanır belirtmek için meta veri öğesi.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-147">Furthermore, because a content file is not compiled directly into the assembly, you need to set the [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`CopyToOutputDirectory` metadata element to specify that the content file is copied to a location that is relative to the built assembly.</span></span> <span data-ttu-id="fbb9b-148">Her zaman yapı çıktı klasörüne Kopyalanacak kaynak istiyorsanız bir proje oluşturulmuştur, ayarladığınız `CopyToOutputDirectory` olan meta veri öğesi `Always` değeri.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-148">If you want the resource to be copied to the build output folder every time a project is built, you set the `CopyToOutputDirectory` metadata element with the `Always` value.</span></span> <span data-ttu-id="fbb9b-149">Aksi halde, kaynak yalnızca en yeni sürümünü kullanarak yapı çıktı klasörüne kopyalanır sağlayabilirsiniz `PreserveNewest` değeri.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-149">Otherwise, you can ensure that only the newest version of the resource is copied to the build output folder by using the `PreserveNewest` value.</span></span>  
  
 <span data-ttu-id="fbb9b-150">Aşağıdaki klasörü kaynak yeni bir sürümü olduğunda projeye eklenir yapı kopyalanan bir içerik dosyası çıktı olarak yapılandırılmış bir dosya gösterir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-150">The following shows a file that is configured as a content file which is copied to the build output folder only when a new version of the resource is added to the project.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <ItemGroup>  
    <Content Include="ContentFile.xaml">  
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>  
    </Content>  
  </ItemGroup>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-151">İçinde [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], bir dosyayı bir proje ve ayarı ekleyerek bir içerik dosyası oluşturma kendi `Build Action` için `Content`ve kendi `Copy to Output Directory` için `Copy always` (aynı `Always`) ve `Copy if newer` (aynı `PreserveNewest`).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-151">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a content file by adding a file to a project and setting its `Build Action` to `Content`, and set its `Copy to Output Directory` to `Copy always` (same as `Always`) and `Copy if newer` (same as `PreserveNewest`).</span></span>  
  
 <span data-ttu-id="fbb9b-152">Proje yapılandırıldığında, bir <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> özniteliği her içerik dosyasının derlemenin meta verilerini derlenir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-152">When the project is built, an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is compiled into the metadata of the assembly for each content file.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("ContentFile.xaml")]`  
  
 <span data-ttu-id="fbb9b-153">Değeri <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> proje konumuna göre içerik dosyasının yolunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-153">The value of the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> implies the path to the content file relative to its position in the project.</span></span> <span data-ttu-id="fbb9b-154">Bir içerik dosyası projenin alt klasöründe bulunan, örneğin, ek yol bilgileri birleştirilir <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> değeri.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-154">For example, if a content file was located in a project subfolder, the additional path information would be incorporated into the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value.</span></span>  
  
 `[assembly: AssemblyAssociatedContentFile("Resources/ContentFile.xaml")]`  
  
 <span data-ttu-id="fbb9b-155"><xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> Değeri değeridir ayrıca yapı çıkış klasöründe içerik dosyasının yolu.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-155">The <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> value is also the value of the path to the content file in the build output folder.</span></span>  
  
### <a name="using-content-files"></a><span data-ttu-id="fbb9b-156">İçerik dosyalarını kullanma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-156">Using Content Files</span></span>  
 <span data-ttu-id="fbb9b-157">Bir içerik dosyası yüklemek için çağırabilirsiniz <xref:System.Windows.Application.GetContentStream%2A> yöntemi <xref:System.Windows.Application> sınıfı, bir paketi geçirme [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] istenen içerik dosyasını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-157">To load a content file, you can call the <xref:System.Windows.Application.GetContentStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired content file.</span></span> <span data-ttu-id="fbb9b-158"><xref:System.Windows.Application.GetContentStream%2A>döndüren bir <xref:System.Windows.Resources.StreamResourceInfo> olarak içerik dosyasını sunan nesnesi bir <xref:System.IO.Stream> ve içerik türünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-158"><xref:System.Windows.Application.GetContentStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the content file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="fbb9b-159">Örnek olarak, aşağıdaki kodu nasıl kullanılacağını gösterir. <xref:System.Windows.Application.GetContentStream%2A> yüklemek için bir <xref:System.Windows.Controls.Page> içerik dosyasını ve içeriği olarak ayarlanmış bir <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-159">As an example, the following code shows how to use <xref:System.Windows.Application.GetContentStream%2A> to load a <xref:System.Windows.Controls.Page> content file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadapagecontentfilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageContentFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadapagecontentfilemanuallycode)]  
  
 <span data-ttu-id="fbb9b-160">Arama sırasında <xref:System.Windows.Application.GetContentStream%2A> e erişmenizi <xref:System.IO.Stream>, ek iş, kendisiyle ayarlayacağınız özellik türüne dönüştürme gerçekleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-160">While calling <xref:System.Windows.Application.GetContentStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="fbb9b-161">Bunun yerine, sağlayabilirsiniz [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] açma ve dönüştürme ilgilenebilmek <xref:System.IO.Stream> tarafından doğrudan kodu kullanarak tür özelliğine bir kaynak dosyası yükleniyor.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-161">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="fbb9b-162">Aşağıdaki örnekte nasıl yükleneceğini gösterir bir <xref:System.Windows.Controls.Page> doğrudan bir <xref:System.Windows.Controls.Frame> (`pageFrame`) kullanılarak kod.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-162">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.cs#loadpagecontentfilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageContentFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml.vb#loadpagecontentfilefromcode)]  
  
 <span data-ttu-id="fbb9b-163">Aşağıdaki örnek biçimlendirmesi olan önceki örnekte eşdeğer.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-163">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageContentFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/ApplicationGetContentStreamSnippetWindow.xaml#loadpagecontentfilefromxaml)]  
  
<a name="Site_of_Origin_Files"></a>   
## <a name="site-of-origin-files"></a><span data-ttu-id="fbb9b-164">Kaynak dosyaları sitesi</span><span class="sxs-lookup"><span data-stu-id="fbb9b-164">Site of Origin Files</span></span>  
 <span data-ttu-id="fbb9b-165">Kaynak dosyalarınız yanı sıra, dağıtılmış derlemeler ile açık bir ilişkisi tarafından tanımlandığı şekilde <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-165">Resource files have an explicit relationship with the assemblies that they are distributed alongside, as defined by the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>.</span></span> <span data-ttu-id="fbb9b-166">Ancak, bir derlemeyi ve ne zaman dahil olmak üzere bir uygulama veri dosyası arasında örtük veya var olmayan bir ilişki kurmak istediğinizde zamanlar vardır:</span><span class="sxs-lookup"><span data-stu-id="fbb9b-166">But, there are times when you may want to establish either an implicit or non-existent relationship between an assembly and an application data file, including when:</span></span>  
  
-   <span data-ttu-id="fbb9b-167">Bir dosya derleme zamanında yok.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-167">A file doesn't exist when at compile time.</span></span>  
  
-   <span data-ttu-id="fbb9b-168">Derlemenizi çalışma zamanına kadar gerektirecektir hangi dosyaların bilinmiyor.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-168">You don't know what files your assembly will require until run time.</span></span>  
  
-   <span data-ttu-id="fbb9b-169">Güncelleştirme dosyaları ile ilişkili derleme derlemeden kullanabilmek ister.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-169">You want to be able to update files without recompiling the assembly that they are associated with.</span></span>  
  
-   <span data-ttu-id="fbb9b-170">Uygulamanız ses ve video gibi büyük veri dosyalarını kullanır ve yalnızca isterlerse bunları indirmek istediğiniz.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-170">Your application uses large data files, such as audio and video, and you only want users to download them if they choose to.</span></span>  
  
 <span data-ttu-id="fbb9b-171">Bu tür kullanarak geleneksel dosyaları yüklemek mümkündür [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] file:/// ve http:// düzenleri gibi düzenleri.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-171">It is possible to load these types of files by using traditional [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] schemes, such as the file:/// and http:// schemes.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#AbsolutePackUriFileHttpReferenceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/AbsolutePackUriPage.xaml#absolutepackurifilehttpreferencexaml)]  
  
 <span data-ttu-id="fbb9b-172">Ancak, file:/// ve http:// düzenleri uygulamanızın tam güven gerektirir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-172">However, the file:/// and http:// schemes require your application to have full trust.</span></span> <span data-ttu-id="fbb9b-173">Uygulamanız ise bir [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] Internet veya intranet tarafından başlatılmış ve yalnızca bu konumlardan başlatılan uygulamalara gevşek dosyalarını kaynağı (uygulamanın sitesinden yalnızca yüklenebilir izin verilen izinler kümesini istekleri Konum Başlat).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-173">If your application is a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that was launched from the Internet or intranet, and it requests only the set of permissions that are allowed for applications launched from those locations, loose files can only be loaded from the application's site of origin (launch location).</span></span> <span data-ttu-id="fbb9b-174">Bu tür dosyalar olarak bilinir *kaynak site* dosyaları.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-174">Such files are known as *site of origin* files.</span></span>  
  
 <span data-ttu-id="fbb9b-175">Kaynak dosyaları sitesi kısmi güven uygulamaları için tek seçenek olan ancak kısmi güven uygulamaları için sınırlı.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-175">Site of origin files are the only option for partial trust applications, although are not limited to partial trust applications.</span></span> <span data-ttu-id="fbb9b-176">Tam güven uygulamaları, bunlar derleme zamanında bilmiyor uygulama verileri dosyaları yüklemek hala gerekebilir; tam güven uygulamalarının file:/// kullanabilirken uygulama verileri dosyaları aynı klasörde veya bir alt klasörü, uygulama derleme yüklenecek olasıdır.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-176">Full trust applications may still need to load application data files that they do not know about at build time; while full trust applications could use file:///, it is likely that the application data files will be installed in the same folder as, or a subfolder of, the application assembly.</span></span> <span data-ttu-id="fbb9b-177">File:/// kullanarak dosyanın tam yolunu çalışmanız gerekir çünkü bu durumda, kaynak sitesi kullanarak file:/// kullanmaktan daha kolaydır.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-177">In this case, using site of origin referencing is easier than using file:///, because using file:/// requires you to work out the full path the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-178">Kaynak dosyaları ile önbelleğe alınmaz site bir [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] içerik dosyaları açıkken bir istemci makine üzerinde.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-178">Site of origin files are not cached with an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] on a client machine, while content files are.</span></span> <span data-ttu-id="fbb9b-179">Sonuç olarak, bunlar yalnızca özellikle istendiğinde indirilir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-179">Consequently, they are only downloaded when specifically requested.</span></span> <span data-ttu-id="fbb9b-180">Varsa bir [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] uygulama büyük medya dosyalarını, kaynak dosyaları sitesi anlamına gelir başlangıç uygulaması başlatma çok daha hızlıdır ve yalnızca isteğe bağlı olarak indirilen dosyaları gibi yapılandırmadan sahiptir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-180">If an [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] application has large media files, configuring them as site of origin files means the initial application launch is much faster, and the files are only downloaded on demand.</span></span>  
  
### <a name="configuring-site-of-origin-files"></a><span data-ttu-id="fbb9b-181">Kaynak dosyaları sitesi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-181">Configuring Site of Origin Files</span></span>  
 <span data-ttu-id="fbb9b-182">Geleneksel dağıtım kullanmanıza gerek olmayan veya bilinmeyen sitenizi kaynak dosyaları derleme zamanında, gerekli dosyaları sağlamaya yönelik mekanizmalarını kullanarak da dahil olmak üzere çalışma zamanında kullanılabilir `XCopy` komut satırı programı veya [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbb9b-182">If your site of origin files are non-existent or unknown at compile time, you need to use traditional deployment mechanisms for ensuring the required files are available at run time, including using either the `XCopy` command-line program or the [!INCLUDE[TLA#tla_wininstall](../../../../includes/tlasharptla-wininstall-md.md)].</span></span>  
  
 <span data-ttu-id="fbb9b-183">Kaynak sitede bulunması istiyor ancak yine de açık bağımlılığı önlemek istiyor dosyaları derleme zamanında biliyorsanız, bu dosyalara ekleyebileceğiniz bir [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] proje olarak `None` öğesi.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-183">If you do know at compile time the files that you would like to be located at the site of origin, but still want to avoid an explicit dependency, you can add those files to an [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] project as `None` item.</span></span> <span data-ttu-id="fbb9b-184">İçerik dosyaları ile ayarlamak gerek duyduğunuz [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `CopyToOutputDirectory` site kaynak dosya yerleşik derleme göreli ya da belirterek bir konuma kopyalanır belirtmek için özniteliği `Always` değeri veya `PreserveNewest` değeri.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-184">As with content files, you need to set the [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`CopyToOutputDirectory` attribute to specify that the site of origin file is copied to a location that is relative to the built assembly, by specifying either the `Always` value or the `PreserveNewest` value.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
  ...  
  <None Include="PageSiteOfOriginFile.xaml">  
    <CopyToOutputDirectory>Always</CopyToOutputDirectory>  
  </None>  
  ...  
</Project>  
```  
  
> [!NOTE]
>  <span data-ttu-id="fbb9b-185">İçinde [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], bir dosyayı bir proje ve ayarı ekleyerek kaynak dosya bir site oluşturun, `Build Action` için `None`.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-185">In [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], you create a site of origin file by adding a file to a project and setting its `Build Action` to `None`.</span></span>  
  
 <span data-ttu-id="fbb9b-186">Proje yapılandırıldığında [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] belirtilen dosyaları yapı çıktı klasörüne kopyalar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-186">When the project is built, [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] copies the specified files to the build output folder.</span></span>  
  
### <a name="using-site-of-origin-files"></a><span data-ttu-id="fbb9b-187">Kaynak dosyaları sitesi kullanma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-187">Using Site of Origin Files</span></span>  
 <span data-ttu-id="fbb9b-188">Kaynak dosya sitesini yüklemek için çağırabilirsiniz <xref:System.Windows.Application.GetRemoteStream%2A> yöntemi <xref:System.Windows.Application> sınıfı, bir paketi geçirme [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] kaynak dosya istenen site tanımlar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-188">To load a site of origin file, you can call the <xref:System.Windows.Application.GetRemoteStream%2A> method of the <xref:System.Windows.Application> class, passing a pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] that identifies the desired site of origin file.</span></span> <span data-ttu-id="fbb9b-189"><xref:System.Windows.Application.GetRemoteStream%2A>döndüren bir <xref:System.Windows.Resources.StreamResourceInfo> site kaynak dosya kullanıma sunar nesnesi bir <xref:System.IO.Stream> ve içerik türünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-189"><xref:System.Windows.Application.GetRemoteStream%2A> returns a <xref:System.Windows.Resources.StreamResourceInfo> object, which exposes the site of origin file as a <xref:System.IO.Stream> and describes its content type.</span></span>  
  
 <span data-ttu-id="fbb9b-190">Örnek olarak, aşağıdaki kodu nasıl kullanılacağını gösterir. <xref:System.Windows.Application.GetRemoteStream%2A> yüklemek için bir <xref:System.Windows.Controls.Page> kaynak site dosya ve içeriği olarak ayarlanmış bir <xref:System.Windows.Controls.Frame> (`pageFrame`).</span><span class="sxs-lookup"><span data-stu-id="fbb9b-190">As an example, the following code shows how to use <xref:System.Windows.Application.GetRemoteStream%2A> to load a <xref:System.Windows.Controls.Page> site of origin file and set it as the content of a <xref:System.Windows.Controls.Frame> (`pageFrame`).</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadapagesoofilemanuallycode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadAPageSOOFileManuallyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadapagesoofilemanuallycode)]  
  
 <span data-ttu-id="fbb9b-191">Arama sırasında <xref:System.Windows.Application.GetRemoteStream%2A> e erişmenizi <xref:System.IO.Stream>, ek iş, kendisiyle ayarlayacağınız özellik türüne dönüştürme gerçekleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-191">While calling <xref:System.Windows.Application.GetRemoteStream%2A> gives you access to the <xref:System.IO.Stream>, you need to perform the additional work of converting it to the type of the property that you'll be setting it with.</span></span> <span data-ttu-id="fbb9b-192">Bunun yerine, sağlayabilirsiniz [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] açma ve dönüştürme ilgilenebilmek <xref:System.IO.Stream> tarafından doğrudan kodu kullanarak tür özelliğine bir kaynak dosyası yükleniyor.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-192">Instead, you can let [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] take care of opening and converting the <xref:System.IO.Stream> by loading a resource file directly into the property of a type using code.</span></span>  
  
 <span data-ttu-id="fbb9b-193">Aşağıdaki örnekte nasıl yükleneceğini gösterir bir <xref:System.Windows.Controls.Page> doğrudan bir <xref:System.Windows.Controls.Frame> (`pageFrame`) kullanılarak kod.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-193">The following example shows how to load a <xref:System.Windows.Controls.Page> directly into a <xref:System.Windows.Controls.Frame> (`pageFrame`) using code.</span></span>  
  
 [!code-csharp[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml.cs#loadpagesoofilefromcode)]
 [!code-vb[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/VisualBasic/ResourcesSample/SOOPage.xaml.vb#loadpagesoofilefromcode)]  
  
 <span data-ttu-id="fbb9b-194">Aşağıdaki örnek biçimlendirmesi olan önceki örnekte eşdeğer.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-194">The following example is the markup equivalent of the preceding example.</span></span>  
  
 [!code-xaml[WPFAssemblyResourcesSnippets#LoadPageSOOFileFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAssemblyResourcesSnippets/CSharp/ResourcesSample/SOOPage.xaml#loadpagesoofilefromxaml)]  
  
<a name="Rebuilding_after_Changing_Build_Type"></a>   
## <a name="rebuilding-after-changing-build-type"></a><span data-ttu-id="fbb9b-195">Yapı türü değiştirdikten sonra yeniden oluşturma</span><span class="sxs-lookup"><span data-stu-id="fbb9b-195">Rebuilding After Changing Build Type</span></span>  
 <span data-ttu-id="fbb9b-196">Uygulama veri dosyası derleme türünü değiştirdikten sonra bu değişikliklerin uygulandığından emin olmak için tüm uygulamayı yeniden yapılandırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-196">After you change the build type of an application data file, you need to rebuild the entire application to ensure those changes are applied.</span></span> <span data-ttu-id="fbb9b-197">Yalnızca uygulamayı yapılandırdıysanız, değişiklikleri uygulanmaz.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-197">If you only build the application, the changes are not applied.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb9b-198">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fbb9b-198">See Also</span></span>  
 [<span data-ttu-id="fbb9b-199">WPF içinde URI'leri paketleme</span><span class="sxs-lookup"><span data-stu-id="fbb9b-199">Pack URIs in WPF</span></span>](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)