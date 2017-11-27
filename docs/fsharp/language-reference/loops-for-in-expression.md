---
title: "Döngüler: for...in İfadesi (F#)"
description: "Bkz. nasıl F # for... ifadesinde yapı döngü numaralandırılabilir bir koleksiyon içindeki bir desenle eşleşen üzerinden yinelemek için kullanılır."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f54e3228-4aec-4d0a-ae37-bc3376508284
ms.openlocfilehash: d86aeb3bdd975261e59004d636354a740bd95c47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="loops-forin-expression"></a><span data-ttu-id="6bf27-104">Döngüler: for...in İfadesi</span><span class="sxs-lookup"><span data-stu-id="6bf27-104">Loops: for...in Expression</span></span>

<span data-ttu-id="6bf27-105">Bu döngü yapısı aralık ifade, sırası, liste, dizi veya numaralandırma destekleyen diğer yapı gibi numaralandırılabilir bir koleksiyon içindeki bir desenle eşleşen üzerinden yinelemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6bf27-105">This looping construct is used to iterate over the matches of a pattern in an enumerable collection such as a range expression, sequence, list, array, or other construct that supports enumeration.</span></span>


## <a name="syntax"></a><span data-ttu-id="6bf27-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6bf27-106">Syntax</span></span>

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="6bf27-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6bf27-107">Remarks</span></span>
<span data-ttu-id="6bf27-108">`for...in` İfade için karşılaştırılabilir `for each` diğer .NET dilleri deyiminde numaralandırılabilir koleksiyonundaki değerleri üzerinde döngü için kullanıldığından.</span><span class="sxs-lookup"><span data-stu-id="6bf27-108">The `for...in` expression can be compared to the `for each` statement in other .NET languages because it is used to loop over the values in an enumerable collection.</span></span> <span data-ttu-id="6bf27-109">Ancak, `for...in` desen eşleştirme içinde tüm koleksiyon yerine yalnızca yineleme koleksiyon üzerinden de destekler.</span><span class="sxs-lookup"><span data-stu-id="6bf27-109">However, `for...in` also supports pattern matching over the collection instead of just iteration over the whole collection.</span></span>

<span data-ttu-id="6bf27-110">Numaralandırılabilir ifade numaralandırılabilir bir koleksiyon olarak veya kullanarak belirtilen `..` olarak bir tamsayı türünde bir aralık işleci.</span><span class="sxs-lookup"><span data-stu-id="6bf27-110">The enumerable expression can be specified as an enumerable collection or, by using the `..` operator, as a range on an integral type.</span></span> <span data-ttu-id="6bf27-111">Numaralandırılabilir koleksiyonları listeler, dizileri, dizileri, kümeleri, eşlemeleri vb. içerir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-111">Enumerable collections include lists, sequences, arrays, sets, maps, and so on.</span></span> <span data-ttu-id="6bf27-112">Uygulayan herhangi bir türü `System.Collections.IEnumerable` kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-112">Any type that implements `System.Collections.IEnumerable` can be used.</span></span>

<span data-ttu-id="6bf27-113">Ne zaman, hızlı bir aralık kullanarak `..` işleci, aşağıdaki söz dizimini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6bf27-113">When you express a range by using the `..` operator, you can use the following syntax.</span></span>

<span data-ttu-id="6bf27-114">*Başlat* ...</span><span class="sxs-lookup"><span data-stu-id="6bf27-114">*start* ..</span></span> <span data-ttu-id="6bf27-115">*Son*</span><span class="sxs-lookup"><span data-stu-id="6bf27-115">*finish*</span></span>

<span data-ttu-id="6bf27-116">Adlı bir artış içeren bir sürümünü de kullanabilirsiniz *atla*, aşağıdaki kod gibi.</span><span class="sxs-lookup"><span data-stu-id="6bf27-116">You can also use a version that includes an increment called the *skip*, as in the following code.</span></span>

<span data-ttu-id="6bf27-117">*Başlat* ...</span><span class="sxs-lookup"><span data-stu-id="6bf27-117">*start* ..</span></span> <span data-ttu-id="6bf27-118">*atla* ...</span><span class="sxs-lookup"><span data-stu-id="6bf27-118">*skip* ..</span></span> <span data-ttu-id="6bf27-119">*Son*</span><span class="sxs-lookup"><span data-stu-id="6bf27-119">*finish*</span></span>

<span data-ttu-id="6bf27-120">Tam sayı aralıkları ve basit bir sayaç değişken kalıp olarak kullandığınızda, tipik davranışı her bir yineleme 1 sayaç değişkeni artırılacak olmakla birlikte, aralık bir atlama değeri içeriyorsa, bu sayaç tarafından atlama değeri yerine artırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf27-120">When you use integral ranges and a simple counter variable as a pattern, the typical behavior is to increment the counter variable by 1 on each iteration, but if the range includes a skip value, the counter is incremented by the skip value instead.</span></span>

<span data-ttu-id="6bf27-121">Düzende eşleşen değerleri de gövde ifadesinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-121">Values matched in the pattern can also be used in the body expression.</span></span>

<span data-ttu-id="6bf27-122">Aşağıdaki kod örnekleri kullanımını göstermek `for...in` ifade.</span><span class="sxs-lookup"><span data-stu-id="6bf27-122">The following code examples illustrate the use of the `for...in` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

<span data-ttu-id="6bf27-123">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="6bf27-123">The output is as follows.</span></span>

```
1
5
100
450
788
```

<span data-ttu-id="6bf27-124">Aşağıdaki örnekte nasıl sırası döngü ve yerine basit bir değişkene bir demet deseni kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-124">The following example shows how to loop over a sequence, and how to use a tuple pattern instead of a simple variable.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

<span data-ttu-id="6bf27-125">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="6bf27-125">The output is as follows.</span></span>

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

<span data-ttu-id="6bf27-126">Aşağıdaki örnek, bir basit tamsayı aralığında döngü gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-126">The following example shows how to loop over a simple integer range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

<span data-ttu-id="6bf27-127">Function1 çıktı aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-127">The output of function1 is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
```

<span data-ttu-id="6bf27-128">Aşağıdaki örnek, bir aralığı her bir öğe içeren bir Atla 2 ' olan bir aralığı üzerinden döngü gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-128">The following example shows how to loop over a range with a skip of 2, which includes every other element of the range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

<span data-ttu-id="6bf27-129">Çıktısını `function2` aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-129">The output of `function2` is as follows.</span></span>

```
1 3 5 7 9
```

<span data-ttu-id="6bf27-130">Aşağıdaki örnek, bir karakter aralığı kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-130">The following example shows how to use a character range.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

<span data-ttu-id="6bf27-131">Çıktısını `function3` aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-131">The output of `function3` is as follows.</span></span>

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

<span data-ttu-id="6bf27-132">Aşağıdaki örnek, geriye doğru yineleme için negatif atlama değeri kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-132">The following example shows how to use a negative skip value for a reverse iteration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

<span data-ttu-id="6bf27-133">Çıktısını `function4` aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-133">The output of `function4` is as follows.</span></span>

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

<span data-ttu-id="6bf27-134">Başlangıç ve bitiş aralığının İşlevler, aşağıdaki kod olduğu gibi ifadeler de olabilir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-134">The beginning and ending of the range can also be expressions, such as functions, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

<span data-ttu-id="6bf27-135">Çıktısını `function5` bu girişle aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-135">The output of `function5` with this input is as follows.</span></span>

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

<span data-ttu-id="6bf27-136">Öğe bir döngüde gerekli olmadığında sonraki örnek bir joker karakteri (_) kullanımını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="6bf27-136">The next example shows the use of a wildcard character (_) when the element is not needed in the loop.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

<span data-ttu-id="6bf27-137">Çıktı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="6bf27-137">The output is as follows.</span></span>

```
Number of elements in list1: 5
```

<span data-ttu-id="6bf27-138">`Note`Kullanabileceğiniz `for...in` sequence ifadeleri ve diğer hesaplama ifadeleri özelleştirilmiş bir sürümünü durumda içinde `for...in` ifade kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6bf27-138">`Note` You can use `for...in` in sequence expressions and other computation expressions, in which case a customized version of the `for...in` expression is used.</span></span> <span data-ttu-id="6bf27-139">Daha fazla bilgi için bkz: [sıraları](sequences.md), [zaman uyumsuz iş akışları](asynchronous-workflows.md), ve [hesaplama ifadeleri](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6bf27-139">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="6bf27-140">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6bf27-140">See Also</span></span>
[<span data-ttu-id="6bf27-141">F # dili başvurusu</span><span class="sxs-lookup"><span data-stu-id="6bf27-141">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="6bf27-142">Döngüler: `for...to` ifade</span><span class="sxs-lookup"><span data-stu-id="6bf27-142">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)

[<span data-ttu-id="6bf27-143">Döngüler: `while...do` ifade</span><span class="sxs-lookup"><span data-stu-id="6bf27-143">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)