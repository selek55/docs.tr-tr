---
title: "PLINQ ve TPL'deki Lambda İfadeleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79ab0f4427e0f37259f88cd3ec0762d1582481f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a><span data-ttu-id="e68bb-102">PLINQ ve TPL'deki Lambda İfadeleri</span><span class="sxs-lookup"><span data-stu-id="e68bb-102">Lambda Expressions in PLINQ and TPL</span></span>
<span data-ttu-id="e68bb-103">Görev paralel kitaplığı (TPL) birini birçok yöntem içerir <xref:System.Func%601?displayProperty=nameWithType> veya <xref:System.Action?displayProperty=nameWithType> giriş parametresi olarak temsilciler ailesi.</span><span class="sxs-lookup"><span data-stu-id="e68bb-103">The Task Parallel Library (TPL) contains many methods that take one of the <xref:System.Func%601?displayProperty=nameWithType> or <xref:System.Action?displayProperty=nameWithType> family of delegates as input parameters.</span></span> <span data-ttu-id="e68bb-104">Bu temsilci paralel döngü, görev veya sorgu için özel bir program mantığınızı geçirmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e68bb-104">You use these delegates to pass in your custom program logic to the parallel loop, task or query.</span></span> <span data-ttu-id="e68bb-105">Kod örnekleri PLINQ yanı sıra TPL için lambda ifadeleri Bu temsilci satır içi kod blokları olarak örneklerini oluşturmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e68bb-105">The code examples for TPL as well as PLINQ use lambda expressions to create instances of those delegates as inline code blocks.</span></span> <span data-ttu-id="e68bb-106">Bu konu, işlev ve eylem kısa bir giriş sağlar ve görev paralel kitaplığı ve PLINQ'da lambda ifadeleri kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="e68bb-106">This topic provides a brief introduction to Func and Action and shows you how to use lambda expressions in the Task Parallel Library and PLINQ.</span></span>  
  
 <span data-ttu-id="e68bb-107">**Not** genel olarak, temsilciler hakkında daha fazla bilgi için bkz [Temsilciler](../../csharp/programming-guide/delegates/index.md) ve [Temsilciler](../../visual-basic/programming-guide/language-features/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="e68bb-107">**Note** For more information about delegates in general, see [Delegates](../../csharp/programming-guide/delegates/index.md) and [Delegates](../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span> <span data-ttu-id="e68bb-108">C# ' deki lambda ifadeleri hakkında daha fazla bilgi ve [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], bkz: [Lambda ifadeleri](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) ve [Lambda ifadeleri](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e68bb-108">For more information about lambda expressions in C# and [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], see [Lambda Expressions](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) and [Lambda Expressions](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="func-delegate"></a><span data-ttu-id="e68bb-109">İşlev temsilcisi</span><span class="sxs-lookup"><span data-stu-id="e68bb-109">Func Delegate</span></span>  
 <span data-ttu-id="e68bb-110">A `Func` temsilci bir değer döndüren bir yöntem yalıtır.</span><span class="sxs-lookup"><span data-stu-id="e68bb-110">A `Func` delegate encapsulates a method that returns a value.</span></span> <span data-ttu-id="e68bb-111">Bir işlev imzası son veya en sağdaki tür parametresi her zaman dönüş türünü belirtir.</span><span class="sxs-lookup"><span data-stu-id="e68bb-111">In a Func signature, the last or rightmost type parameter always specifies the return type.</span></span> <span data-ttu-id="e68bb-112">Bir genel derleyici hataları nedenidir iki giriş parametreleri geçirin girişimi için bir <xref:System.Func%602?displayProperty=nameWithType>; aslında bu tür, yalnızca bir giriş parametresi alır.</span><span class="sxs-lookup"><span data-stu-id="e68bb-112">One common cause of compiler errors is to attempt to pass in two input parameters to a <xref:System.Func%602?displayProperty=nameWithType>; in fact this type takes only one input parameter.</span></span> <span data-ttu-id="e68bb-113">17 sürümleri Framework sınıf kitaplığı tanımlar `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, vb. Yukarı aracılığıyla <xref:System.Func%6017?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e68bb-113">The Framework Class Library defines 17 versions of `Func`: <xref:System.Func%601?displayProperty=nameWithType>, <xref:System.Func%602?displayProperty=nameWithType>, <xref:System.Func%603?displayProperty=nameWithType>, and so on up through <xref:System.Func%6017?displayProperty=nameWithType>.</span></span>  
  
## <a name="action-delegate"></a><span data-ttu-id="e68bb-114">Eylem temsilcisi</span><span class="sxs-lookup"><span data-stu-id="e68bb-114">Action Delegate</span></span>  
 <span data-ttu-id="e68bb-115">A <xref:System.Action?displayProperty=nameWithType> temsilci yalıtan bir yöntem (içinde Sub [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), bir değer döndürmez veya verir [void](~/docs/csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="e68bb-115">A <xref:System.Action?displayProperty=nameWithType> delegate encapsulates a method (Sub in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) that does not return a value, or returns [void](~/docs/csharp/language-reference/keywords/void.md).</span></span> <span data-ttu-id="e68bb-116">Bir eylem türü imzası tür parametreleri yalnızca giriş parametreleri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e68bb-116">In an Action type signature, the type parameters represent only input parameters.</span></span> <span data-ttu-id="e68bb-117">FUNC gibi eylem, 17 sürümleri olan hiçbir tür parametreleri 16 türü parametrelerine sahip bir sürüm sürümünden Framework sınıf kitaplığı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e68bb-117">Like Func, the Framework Class Library defines 17 versions of Action, from a version that has no type parameters up through a version that has 16 type parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68bb-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="e68bb-118">Example</span></span>  
 <span data-ttu-id="e68bb-119">Aşağıdaki örnek için <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> yöntemi lambda ifadeleri kullanarak işlev ve eylem temsilciler express nasıl gösterir.</span><span class="sxs-lookup"><span data-stu-id="e68bb-119">The following example for the <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> method shows how to express both Func and Action delegates by using lambda expressions.</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a><span data-ttu-id="e68bb-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e68bb-120">See Also</span></span>  
 [<span data-ttu-id="e68bb-121">Paralel Programlama</span><span class="sxs-lookup"><span data-stu-id="e68bb-121">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)