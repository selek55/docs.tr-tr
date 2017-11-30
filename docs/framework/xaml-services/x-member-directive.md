---
title: "x:Member Yönergesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: eafb222dd5d3afcc751bae7799f0d17279aed14f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="xmember-directive"></a><span data-ttu-id="ef53d-102">x:Member Yönergesi</span><span class="sxs-lookup"><span data-stu-id="ef53d-102">x:Member Directive</span></span>
<span data-ttu-id="ef53d-103">XAML üyesi biçimlendirmede bildirir.</span><span class="sxs-lookup"><span data-stu-id="ef53d-103">Declares a XAML member in markup.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="ef53d-104">XAML Nesne Öğesi Kullanımı</span><span class="sxs-lookup"><span data-stu-id="ef53d-104">XAML Object Element Usage</span></span>  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Member Name="propertyName"/>  
    additionalMembers  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ef53d-105">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="ef53d-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`className`|<span data-ttu-id="ef53d-106">XAML üretim için yedekleme sınıfı ya da parçalı sınıf adıdır.</span><span class="sxs-lookup"><span data-stu-id="ef53d-106">Name of the backing class or partial class for the XAML production.</span></span>|  
|`memberName`|<span data-ttu-id="ef53d-107">Tanımlanan özelliğinin üye adı.</span><span class="sxs-lookup"><span data-stu-id="ef53d-107">Member name of the property being defined.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef53d-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ef53d-108">Remarks</span></span>  
 <span data-ttu-id="ef53d-109">.NET Framework XAML hizmetlerinde uygulamasında.</span><span class="sxs-lookup"><span data-stu-id="ef53d-109">In the .NET Framework XAML Services implementation, .</span></span> <span data-ttu-id="ef53d-110">`x:Member`Yedekleme doğrudan türüne sahip değil, ancak tarafından desteklenen <xref:System.Windows.Markup.MemberDefinition> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="ef53d-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="ef53d-111">XAML düğümü akışı içinde bir `x:Member` öğesi adlı bir üye temsil edilir `Member`, XAML dili XAML ad.</span><span class="sxs-lookup"><span data-stu-id="ef53d-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="ef53d-112">Üye `Member` biçimlendirme tarafından bildirilen şekilde öznitelikleri tutar.</span><span class="sxs-lookup"><span data-stu-id="ef53d-112">The member `Member` holds attributes as declared by markup.</span></span>  
  
 <span data-ttu-id="ef53d-113">Anlamını `Name` ve `Type` .NET Framework XAML hizmetlerinde düzeyinde atanmaz.</span><span class="sxs-lookup"><span data-stu-id="ef53d-113">The meaning of `Name` and `Type` are not assigned at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="ef53d-114">Bunlar daha sonra belirli çerçeveleri tarafından uygulanan kuralları altında yorumlanan dize değerleri, ilk XAML düğüm akış içinde depolanır.</span><span class="sxs-lookup"><span data-stu-id="ef53d-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="ef53d-115">Anlamı bir XAML ad ve XAML türü anlamı Hizala veya yalnızca uygulama bağlı olarak bir yedekleme türü sistemindeki geçerli olabilir.</span><span class="sxs-lookup"><span data-stu-id="ef53d-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>  
  
 <span data-ttu-id="ef53d-116">Pratik kullanımını desteklemek için `x:Members` üye tanımları biçimlendirmede belirtmek için bir yol üyeleri değiştirilebilir bir sınıf ile ilişkili olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="ef53d-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="ef53d-117">Hedeflenen modeli olan `x:Members` belirten bir türü bir üyesi olarak mevcut bir `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="ef53d-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="ef53d-118">Ancak, türleri ve üyeleri ilişkilendirme veya dinamik üyenin tanımları oluşturan mekanizması .NET Framework XAML hizmetlerinde düzeyinde desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ef53d-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at the .NET Framework XAML Services level.</span></span> <span data-ttu-id="ef53d-119">Bu üye tanımları XAML destek uygulama modelleri sahip tek tek çerçeveler bırakılır.</span><span class="sxs-lookup"><span data-stu-id="ef53d-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="ef53d-120">Genellikle, isteğe bağlı olarak işaretleme-XAML ve ya da derleme MSBUILD yapı eylemleri arka plan kodu ile tümleştirmek veya üretim XAML gelen saf derlemeler bu özelliği desteklemek için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="ef53d-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>  
  
## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="ef53d-121">x: özellik Windows Workflow Foundation için</span><span class="sxs-lookup"><span data-stu-id="ef53d-121">x:Property for Windows Workflow Foundation</span></span>  
 <span data-ttu-id="ef53d-122">Windows Workflow Foundation için `x:Property` tamamen XAML veya XAML oluşan özel bir aktivite üyelerini tanımlayan – dinamik üyeler arka plan kodu ile bir etkinlik Tasarımcısı için tanımlanmış.</span><span class="sxs-lookup"><span data-stu-id="ef53d-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="ef53d-123">`x:Class`XAML üretim kök öğesinin de belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="ef53d-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="ef53d-124">Bu, .NET Framework XAML hizmetlerinde düzeyinde zorunlu değildir, ancak XAML üretim özel etkinlikler ve Windows Workflow Foundation XAML genel destek MSBUILD yapı eylemleri tarafından yüklenen bir gereksinim haline gelir.</span><span class="sxs-lookup"><span data-stu-id="ef53d-124">This is not a requirement at the .NET Framework XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="ef53d-125">Windows Workflow Foundation kullanmaz saf XAML tür adı için hedeflenen değeri olarak `x:Property` `Type` özniteliği ve bunun yerine belgelenmemiştir bir kuralı burada kullanır.</span><span class="sxs-lookup"><span data-stu-id="ef53d-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="ef53d-126">Daha fazla bilgi için bkz: [dinamik etkinlik oluşturma](http://msdn.microsoft.com/library/dd807392.aspx).</span><span class="sxs-lookup"><span data-stu-id="ef53d-126">For more information, see [Dynamic Activity Creation](http://msdn.microsoft.com/library/dd807392.aspx).</span></span>