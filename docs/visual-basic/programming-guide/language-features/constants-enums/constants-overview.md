---
title: "Sabitlere Genel Bakış (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6526f7270602b3e1a4e8d953732c393ff252b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="9d9ba-102">Sabitlere Genel Bakış (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d9ba-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="9d9ba-103">Bir sabit bir sayı veya değişmez dize yerini alır anlamlı bir addır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="9d9ba-104">Adından da anlaşılacağı gibi bir uygulamanın yürütmesini boyunca aynı kalır değerleri sabitleri depolar.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="9d9ba-105">Büyük ölçüde kodunuzun okunabilirliğini artırmak ve sabitleri kullanarak bakımını kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="9d9ba-106">Yeniden değerleri içeren kodda kullanın veya hatırlamak veya belirgin bir anlama sahip zor olan belirli numaralarında bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="9d9ba-107">Oluşturma ve kullanma sabitleri</span><span class="sxs-lookup"><span data-stu-id="9d9ba-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9d9ba-108">Yazdırma ve görüntüleme için temel olarak kullanarak, önceden tanımlanmış sabitleri sayısını içerir.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="9d9ba-109">Kendi değerlerinizi ile de oluşturabilirsiniz `Const` deyimi, bir değişken adı oluşturmak için yaptığınız aynı yönergeleri kullanarak.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="9d9ba-110">Varsa `Option Strict` olan `On`, açıkça sabit türü belirtmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="9d9ba-111">Adını niteleme olmadan başvurduğu tüm kod kümesidir, sabit 's kapsamı, aynı konumda bildirilen bir değişken aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="9d9ba-112">Belirli bir yordamın kapsamında mevcut bir sabit oluşturmak için bu yordamı içinde bildirin.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="9d9ba-113">Bir uygulama genelinde kullanılabilir bir sabit oluşturmak için kullanarak bildirme `Public` sınıf bildirimleri bölümünde anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d9ba-114">Sabitler biraz değişkenleri benzer ancak bunları değiştiremez veya değişkenleri yapabildiğiniz gibi yeni değerler atayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="9d9ba-115">Kodunuzda kullandığınız sabitleri denetimleri veya ile çalışırsınız bileşenleri için nesne modeli tarafından tanımlanan veya kullanıcı tanımlı (diğer bir deyişle, bu sizin oluşturduğunuz).</span><span class="sxs-lookup"><span data-stu-id="9d9ba-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="9d9ba-116">Derleme zamanı ve çalışma zamanı sabitleri</span><span class="sxs-lookup"><span data-stu-id="9d9ba-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="9d9ba-117">Derleme zamanı sabiti uygulama çalışırken, yalnızca bir çalışma zamanı sabit hesaplanabilir sırada kodu derlenmiş aynı anda hesaplanır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="9d9ba-118">Derleme zamanı sabiti her zaman bir çalışma zamanı sabit değişebilir sırada bir uygulama, her çalıştığında aynı değere sahip.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="9d9ba-119">Derleme zamanı sabitleri dizi sınırları, case ifadeleri veya numaralandırıcı başlatıcıları gibi durumlarda gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d9ba-120">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="9d9ba-120">In This Section</span></span>  
  
|<span data-ttu-id="9d9ba-121">Tanım</span><span class="sxs-lookup"><span data-stu-id="9d9ba-121">Definition</span></span>|<span data-ttu-id="9d9ba-122">Terim</span><span class="sxs-lookup"><span data-stu-id="9d9ba-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="9d9ba-123">Nasıl yapılır: bir sabit bildirme</span><span class="sxs-lookup"><span data-stu-id="9d9ba-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="9d9ba-124">Nasıl kullanılacağı açıklanmaktadır `Const` deyimi bir sabit bildirme ve; değeri ayarlamak için bir sabit bildirerek, anlamlı bir ad değeri atayın.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="9d9ba-125">Kullanıcı tanımlı sabitler</span><span class="sxs-lookup"><span data-stu-id="9d9ba-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="9d9ba-126">Kapsam hakkında bilgiler dahil olmak üzere kendi sabitler oluşturmak ve döngüsel başvurulara önlemek açıklar.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="9d9ba-127">Sabit ve değişmez değerli veri türleri</span><span class="sxs-lookup"><span data-stu-id="9d9ba-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="9d9ba-128">Bilgi üzerinde nasıl sağlar [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] derleyici başlatır sabitleri zaman `Option Explicit` kapalıdır.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-128">Provides information on how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="9d9ba-129">Nasıl yapılır: ilgili sabit değerleri birlikte grubu</span><span class="sxs-lookup"><span data-stu-id="9d9ba-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="9d9ba-130">İlgili sabit değerleri grubuna gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="9d9ba-131">Başvuru</span><span class="sxs-lookup"><span data-stu-id="9d9ba-131">Reference</span></span>  
  
|<span data-ttu-id="9d9ba-132">Tanım</span><span class="sxs-lookup"><span data-stu-id="9d9ba-132">Definition</span></span>|<span data-ttu-id="9d9ba-133">Terim</span><span class="sxs-lookup"><span data-stu-id="9d9ba-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="9d9ba-134">Sabitler ve numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="9d9ba-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="9d9ba-135">Tarafından önceden tanımlanmış sabitleri listeler [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d9ba-135">Lists the constants predefined by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>|  
|[<span data-ttu-id="9d9ba-136">Const deyimi</span><span class="sxs-lookup"><span data-stu-id="9d9ba-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="9d9ba-137">Açıklar `Const` deyimi ve kullanımı.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="9d9ba-138">Option Strict deyimi</span><span class="sxs-lookup"><span data-stu-id="9d9ba-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="9d9ba-139">Açıklar `Option Strict` deyimi ve kullanımı.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d9ba-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9d9ba-140">See Also</span></span>  
 [<span data-ttu-id="9d9ba-141">Numaralandırmalara genel bakış</span><span class="sxs-lookup"><span data-stu-id="9d9ba-141">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="9d9ba-142">Nasıl yapılır: Visual Basic'te dizi değişkeni başlatma</span><span class="sxs-lookup"><span data-stu-id="9d9ba-142">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)