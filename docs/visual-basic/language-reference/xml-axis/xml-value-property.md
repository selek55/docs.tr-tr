---
title: "XML Değeri Özelliği (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c52ac09e209d6e3f0cfd877a071cbbe3ab96f18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="25a41-102">XML Değeri Özelliği (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25a41-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="25a41-103">Bir ilk öğesinin değeri erişim sağlayan <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25a41-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="25a41-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="25a41-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="25a41-105">Parts</span></span>  
  
|<span data-ttu-id="25a41-106">Terim</span><span class="sxs-lookup"><span data-stu-id="25a41-106">Term</span></span>|<span data-ttu-id="25a41-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="25a41-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="25a41-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="25a41-108">Required.</span></span> <span data-ttu-id="25a41-109">Koleksiyonu <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="25a41-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="25a41-110">Return Value</span></span>  
 <span data-ttu-id="25a41-111">A `String` koleksiyonun ilk öğesinin değeri içeren veya `Nothing` koleksiyonu boş ise.</span><span class="sxs-lookup"><span data-stu-id="25a41-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25a41-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="25a41-112">Remarks</span></span>  
 <span data-ttu-id="25a41-113"><xref:System.Xml.Linq.XElement.Value%2A> Özellik koleksiyonu ilk öğe değerini erişmek kolaylaştırır <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="25a41-114">Bu özellik ilk koleksiyon en az bir nesne içerip içermediğini denetler.</span><span class="sxs-lookup"><span data-stu-id="25a41-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="25a41-115">Koleksiyon boş ise, bu özellik döndürür `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="25a41-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="25a41-116">Aksi takdirde, bu özellik değerini döndürür <xref:System.Xml.Linq.XElement.Value%2A> koleksiyondaki ilk öğesi özelliği.</span><span class="sxs-lookup"><span data-stu-id="25a41-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25a41-117">Bir XML özniteliği kullanılarak değerini eriştiğinizde ' @' tanımlayıcısı, öznitelik değeri olarak döndürülür bir `String` ve açıkça belirtmek gerekmez <xref:System.Xml.Linq.XAttribute.Value%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="25a41-117">When you access the value of an XML attribute using the '@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="25a41-118">Bir koleksiyondaki diğer öğeler erişmek için XML uzantı dizin oluşturucu özelliği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="25a41-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="25a41-119">Daha fazla bilgi için bkz: [Extension Indexer özelliği](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="25a41-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="25a41-120">Devralma</span><span class="sxs-lookup"><span data-stu-id="25a41-120">Inheritance</span></span>  
 <span data-ttu-id="25a41-121">Kullanıcıların çoğunun uygulamak zorunda kalmazsınız <xref:System.Collections.Generic.IEnumerable%601>ve bu nedenle bu bölüm göz ardı edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="25a41-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="25a41-122"><xref:System.Xml.Linq.XElement.Value%2A> Özelliktir uygulama türleri için bir uzantı özelliği `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="25a41-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="25a41-123">Bu uzantı özelliği bağlama genişletme yöntemleri bağlama gibi olduğu: Bu özellik türü arabirimlerinden biri, uygular ve "Value" adına sahip bir özelliğini tanımlar, uzantı özelliği önceliğe sahip.</span><span class="sxs-lookup"><span data-stu-id="25a41-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="25a41-124">Diğer bir deyişle, bu <xref:System.Xml.Linq.XElement.Value%2A> özelliğinin yeni özellik uygulayan bir sınıf tanımlama tarafından geçersiz kılınmış `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="25a41-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25a41-125">Örnek</span><span class="sxs-lookup"><span data-stu-id="25a41-125">Example</span></span>  
 <span data-ttu-id="25a41-126">Aşağıdaki örnekte nasıl kullanılacağını gösterir <xref:System.Xml.Linq.XElement.Value%2A> koleksiyonu ilk düğüm erişmek için özelliğini <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="25a41-127">Örnek, tüm alt düğümleri adlı koleksiyonunu alma için child axis özelliği kullanır. `phone` olan `contact` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="25a41-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="25a41-128">Bu kod, aşağıdaki metni görüntüler:</span><span class="sxs-lookup"><span data-stu-id="25a41-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="25a41-129">Örnek</span><span class="sxs-lookup"><span data-stu-id="25a41-129">Example</span></span>  
 <span data-ttu-id="25a41-130">Aşağıdaki örnek, bir XML özniteliğinin değeri bir koleksiyonundan almak gösterilmiştir <xref:System.Xml.Linq.XAttribute> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="25a41-131">Örnek attribute axis özelliği değerini görüntülemek için kullanır. `type` özniteliği için tüm `phone` öğeleri.</span><span class="sxs-lookup"><span data-stu-id="25a41-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="25a41-132">Bu kod, aşağıdaki metni görüntüler:</span><span class="sxs-lookup"><span data-stu-id="25a41-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="25a41-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="25a41-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="25a41-134">XML eksen özellikleri</span><span class="sxs-lookup"><span data-stu-id="25a41-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="25a41-135">XML değişmez değerleri</span><span class="sxs-lookup"><span data-stu-id="25a41-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="25a41-136">Visual Basic'de XML oluşturma</span><span class="sxs-lookup"><span data-stu-id="25a41-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="25a41-137">Genişletme yöntemleri</span><span class="sxs-lookup"><span data-stu-id="25a41-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="25a41-138">Extension Indexer özelliği</span><span class="sxs-lookup"><span data-stu-id="25a41-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="25a41-139">XML alt Axis özelliği</span><span class="sxs-lookup"><span data-stu-id="25a41-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="25a41-140">XML özniteliği Axis özelliği</span><span class="sxs-lookup"><span data-stu-id="25a41-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)