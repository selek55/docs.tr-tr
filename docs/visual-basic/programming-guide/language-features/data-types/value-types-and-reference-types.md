---
title: "Değer Türleri ve Başvuru Türleri"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b54945d27d186771e8b5353e753afd74c56d71b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="d4a54-102">Değer Türleri ve Başvuru Türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-102">Value Types and Reference Types</span></span>
<span data-ttu-id="d4a54-103">Visual Basic veri türleri sınıflandırmalarına göre uygulanır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="d4a54-104">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Veri türleri sınıflandırılmış belirli türde bir değişken kendi veri veya veri için bir işaretçi depolar göre.</span><span class="sxs-lookup"><span data-stu-id="d4a54-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="d4a54-105">Kendi verilerini depolayan ise bir *değer türü*; başka bir yerde bu bellek verileri için bir işaretçi barındırıyorsa bir *başvuru türüne*.</span><span class="sxs-lookup"><span data-stu-id="d4a54-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="d4a54-106">Değer Türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-106">Value Types</span></span>  
 <span data-ttu-id="d4a54-107">Bir veri türü olan bir *değer türü* kendi bellek ayırma içindeki verilere tutuyorsa.</span><span class="sxs-lookup"><span data-stu-id="d4a54-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="d4a54-108">Değer türleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="d4a54-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="d4a54-109">Tüm sayısal veri türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="d4a54-110">`Boolean`, `Char`, ve`Date`</span><span class="sxs-lookup"><span data-stu-id="d4a54-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="d4a54-111">Başvuru türleri üyeleri olan olsa bile tüm yapıları</span><span class="sxs-lookup"><span data-stu-id="d4a54-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="d4a54-112">Kendi temel alınan türü her zaman olduğundan numaralandırmalar `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, veya`ULong`</span><span class="sxs-lookup"><span data-stu-id="d4a54-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="d4a54-113">Başvuru türü üyeleri içerse bile, her bir değer türü yapısıdır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="d4a54-114">Bu nedenle, değer türleri gibi `Char` ve `Integer` .NET Framework yapıları tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="d4a54-115">Ayrılmış bir anahtar sözcük, örneğin, kullanarak bir değer türü bildirebilirsiniz `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="d4a54-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="d4a54-116">Aynı zamanda `New` anahtar sözcüğü bir değer türü başlatılamadı.</span><span class="sxs-lookup"><span data-stu-id="d4a54-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="d4a54-117">Bu tür parametreler isteyen bir kurucusunun özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="d4a54-118">Bunun bir örneği <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> yeni yapılar Oluşturucusu `Decimal` sağlanan bölümlerinden değeri.</span><span class="sxs-lookup"><span data-stu-id="d4a54-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="d4a54-119">Başvuru Türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-119">Reference Types</span></span>  
 <span data-ttu-id="d4a54-120">A *başvuru türüne* verilerini tutan başka bir bellek konumunu gösteren bir işaretçi içeriyor.</span><span class="sxs-lookup"><span data-stu-id="d4a54-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="d4a54-121">Başvuru türleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="d4a54-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="d4a54-122">Değer türleri kendi öğeleridir olsa bile tüm diziler</span><span class="sxs-lookup"><span data-stu-id="d4a54-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="d4a54-123">Sınıf türleri, gibi<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="d4a54-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="d4a54-124">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="d4a54-124">Delegates</span></span>  
  
 <span data-ttu-id="d4a54-125">Bir sınıf bir *başvuru türüne*.</span><span class="sxs-lookup"><span data-stu-id="d4a54-125">A class is a *reference type*.</span></span> <span data-ttu-id="d4a54-126">Bu nedenle, başvuru türleri gibi `Object` ve `String` tarafından desteklenen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] sınıfları.</span><span class="sxs-lookup"><span data-stu-id="d4a54-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="d4a54-127">Değer türleri üyeleri olsa bile, her dizi bir başvuru türü olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d4a54-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="d4a54-128">Her başvuru türündeki temel alınan bir .NET Framework sınıfı temsil ettiği kullanmalısınız [New işleci](../../../../visual-basic/language-reference/operators/new-operator.md) , Initialize when anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="d4a54-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="d4a54-129">Aşağıdaki deyim, bir dizi başlatır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="d4a54-130">Türleri olmayan öğeler</span><span class="sxs-lookup"><span data-stu-id="d4a54-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="d4a54-131">Bildirilen öğe için bir veri türü olarak hiçbirini belirtilemez çünkü aşağıdaki programlama öğeleri türleri olarak nitelemek değil:</span><span class="sxs-lookup"><span data-stu-id="d4a54-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="d4a54-132">Ad Alanları</span><span class="sxs-lookup"><span data-stu-id="d4a54-132">Namespaces</span></span>  
  
-   <span data-ttu-id="d4a54-133">Modüller</span><span class="sxs-lookup"><span data-stu-id="d4a54-133">Modules</span></span>  
  
-   <span data-ttu-id="d4a54-134">Olaylar</span><span class="sxs-lookup"><span data-stu-id="d4a54-134">Events</span></span>  
  
-   <span data-ttu-id="d4a54-135">Özellikler ve yordamları</span><span class="sxs-lookup"><span data-stu-id="d4a54-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="d4a54-136">Değişkenlerinin, sabitleri ve alanlar</span><span class="sxs-lookup"><span data-stu-id="d4a54-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="d4a54-137">Nesne veri türü ile çalışma</span><span class="sxs-lookup"><span data-stu-id="d4a54-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="d4a54-138">Bir değişken için bir başvuru türü veya bir değer türü atayabilirsiniz `Object` veri türü.</span><span class="sxs-lookup"><span data-stu-id="d4a54-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="d4a54-139">Bir `Object` değişkeni verileri verilerin kendisini hiçbir zaman, her zaman bir işaretçi tutar.</span><span class="sxs-lookup"><span data-stu-id="d4a54-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="d4a54-140">Ancak, bir değer türü atarsanız bir `Object` kendi verilerini varmış gibi değişken, davranır.</span><span class="sxs-lookup"><span data-stu-id="d4a54-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="d4a54-141">Daha fazla bilgi için bkz: [nesne veri türü](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d4a54-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="d4a54-142">Tanımlanmadığını bulabileceğiniz bir `Object` değişken işlevi gören bir başvuru türü veya bir değer türü olarak geçirerek <xref:Microsoft.VisualBasic.Information.IsReference%2A> yönteminde <xref:Microsoft.VisualBasic.Information> sınıfının <xref:Microsoft.VisualBasic?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="d4a54-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d4a54-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>döndürür `True` varsa içeriğini `Object` değişkeni bir başvuru türü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="d4a54-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a54-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d4a54-144">See Also</span></span>  
 [<span data-ttu-id="d4a54-145">Boş değer atanabilen değer türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="d4a54-146">Visual Basic'de tür dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="d4a54-147">Structure deyimi</span><span class="sxs-lookup"><span data-stu-id="d4a54-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="d4a54-148">Veri türlerinin etkili kullanımı</span><span class="sxs-lookup"><span data-stu-id="d4a54-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="d4a54-149">Nesne veri türü</span><span class="sxs-lookup"><span data-stu-id="d4a54-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="d4a54-150">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="d4a54-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)