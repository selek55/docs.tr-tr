---
title: "Bir Dize Adı Kullanarak Bir Özelliği veya Yöntemi Çağırma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5974257fb82fe83c66a480225da200c14338898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="45a0d-102">Bir Dize Adı Kullanarak Bir Özelliği veya Yöntemi Çağırma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45a0d-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="45a0d-103">Çoğu durumda, özellikleri ve yöntemleri bir nesnenin tasarım zamanında bulun ve bunları işlemek için kod yazın.</span><span class="sxs-lookup"><span data-stu-id="45a0d-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="45a0d-104">Ancak, bazı durumlarda, nesnenin özellikleri ve yöntemleri hakkında önceden bilemeyebilirsiniz veya yalnızca bir son kullanıcının özelliklerini belirtin veya çalışma zamanında bir yöntem yürütülemez etkinleştirme esnekliğini isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="45a0d-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="45a0d-105">CallByName işlevi</span><span class="sxs-lookup"><span data-stu-id="45a0d-105">CallByName Function</span></span>  
 <span data-ttu-id="45a0d-106">, Örneğin, bir COM bileşeni için bir işleç geçirerek kullanıcı tarafından girilen ifadeleri değerlendiren bir istemci uygulaması göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="45a0d-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="45a0d-107">Yeni işlevleri yeni işleçleri gerektiren bileşenine sürekli ekleme varsayalım.</span><span class="sxs-lookup"><span data-stu-id="45a0d-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="45a0d-108">Standart nesne erişim tekniklerini kullandığınızda, yeniden derleyin ve yeni işleçleri kullanabilirsiniz önce istemci uygulaması yeniden dağıtın.</span><span class="sxs-lookup"><span data-stu-id="45a0d-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="45a0d-109">Bu durumu önlemek için kullanabileceğiniz `CallByName` uygulamayı değiştirmeden yeni işleçler dize olarak geçirmek için işlevi.</span><span class="sxs-lookup"><span data-stu-id="45a0d-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="45a0d-110">`CallByName` İşlevi çalışma zamanında bir özelliği veya yöntemi belirtmek için bir dize kullanmanıza imkan tanır.</span><span class="sxs-lookup"><span data-stu-id="45a0d-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="45a0d-111">İmza için `CallByName` işlevi şu şekilde görünür:</span><span class="sxs-lookup"><span data-stu-id="45a0d-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="45a0d-112">*Sonuç* = `CallByName`(*nesne*, *ProcedureName*, *CallType*, *bağımsız değişkenleri*())</span><span class="sxs-lookup"><span data-stu-id="45a0d-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="45a0d-113">İlk bağımsız değişken *nesne*, görev istediğiniz nesne adını alır.</span><span class="sxs-lookup"><span data-stu-id="45a0d-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="45a0d-114">*ProcedureName* bağımsız değişkeni çağrılacak yöntemi veya özelliği yordamın adını içeren bir dize alır.</span><span class="sxs-lookup"><span data-stu-id="45a0d-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="45a0d-115">*CallType* çağırmak için yordamı türünü temsil eden sabit bağımsız değişkeni alır: bir yöntem (`Microsoft.VisualBasic.CallType.Method`), bir özelliğin okuma (`Microsoft.VisualBasic.CallType.Get`), veya bir özellik kümesi (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="45a0d-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="45a0d-116">*Bağımsız değişkenleri* isteğe bağlıdır, bağımsız değişkeni alır türünde bir dizi `Object` yordamı için herhangi bir bağımsız değişken içeriyor.</span><span class="sxs-lookup"><span data-stu-id="45a0d-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="45a0d-117">Kullanabileceğiniz `CallByName` sınıflarıyla geçerli çözümünüzün, ancak çoğunlukla COM nesneleri erişmek için kullanılan veya nesnelerin [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] derlemeler.</span><span class="sxs-lookup"><span data-stu-id="45a0d-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="45a0d-118">Adlı bir sınıf içeren bir derleme başvurusu Ekle varsayalım `MathClass`, adında yeni bir işlevi olan `SquareRoot`aşağıdaki kodda gösterildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="45a0d-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 <span data-ttu-id="45a0d-119">Uygulamanızın hangi yöntemi adlı Denetim ve bağımsız değişkenleri için metin kutusu denetimleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="45a0d-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="45a0d-120">Örneğin, varsa `TextBox1` değerlendirilecek ifade içerir ve `TextBox2` olan işlevin adını girmek için kullanılan, çağırmak için aşağıdaki kodu kullanabilirsiniz `SquareRoot` ifade işlevini `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="45a0d-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 <span data-ttu-id="45a0d-121">İçindeki "64" girerseniz `TextBox1`, "SquareRoot" `TextBox2`ve ardından arama `CallMath` yordamı, sayısının kare kökünü `TextBox1` değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="45a0d-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="45a0d-122">Örnek kodda çağırır `SquareRoot` (gerekli bir bağımsız değişken olarak değerlendirilecek ifade içeren bir dize aldığı) işlev ve "8" döndürür `TextBox1` (64 kare kökünü).</span><span class="sxs-lookup"><span data-stu-id="45a0d-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="45a0d-123">Kuşkusuz kullanıcı geçersiz bir dize girerse `TextBox2`, bir yöntem yerine bir özellik adı dize içeriyor ya da yöntemi ek gerekli bağımsız değişken varsa, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="45a0d-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="45a0d-124">Kullandığınızda sağlam hata işleme kodu eklemek zorunda `CallByName` bu veya başka bir hatalar tahmin için.</span><span class="sxs-lookup"><span data-stu-id="45a0d-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45a0d-125">Sırada `CallByName` işlevi bazı durumlarda yararlı olabilir, kendi yararlılığını performans etkileri karşı tartmanız gerekir — kullanarak `CallByName` bir yordam çağırma için geç bağlama çağrı kısmen daha yavaştır.</span><span class="sxs-lookup"><span data-stu-id="45a0d-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="45a0d-126">Gibi bir döngü olduğu gibi içinde tekrar tekrar çağrılan işlev çağırma varsa `CallByName` performans üzerinde ciddi bir etkisi olabilir.</span><span class="sxs-lookup"><span data-stu-id="45a0d-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a0d-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="45a0d-127">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [<span data-ttu-id="45a0d-128">Nesne türünü belirleme</span><span class="sxs-lookup"><span data-stu-id="45a0d-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)