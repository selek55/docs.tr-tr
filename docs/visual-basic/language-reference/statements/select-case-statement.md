---
title: Select...Case Deyimi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7527763a05ec32af88c6ba66ef717d839c33154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="bd1de-102">Select...Case Deyimi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd1de-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="bd1de-103">İfadenin değerine bağlı olarak deyimlerinin birkaç gruplarından birini çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="bd1de-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1de-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="bd1de-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="bd1de-105">Bölümler</span><span class="sxs-lookup"><span data-stu-id="bd1de-105">Parts</span></span>  
  
|<span data-ttu-id="bd1de-106">Terim</span><span class="sxs-lookup"><span data-stu-id="bd1de-106">Term</span></span>|<span data-ttu-id="bd1de-107">Tanım</span><span class="sxs-lookup"><span data-stu-id="bd1de-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="bd1de-108">Gerekli.</span><span class="sxs-lookup"><span data-stu-id="bd1de-108">Required.</span></span> <span data-ttu-id="bd1de-109">İfade.</span><span class="sxs-lookup"><span data-stu-id="bd1de-109">Expression.</span></span> <span data-ttu-id="bd1de-110">Başlangıç veri türleri biri olarak değerlendirmeniz gerekir (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, ve `UShort`).</span><span class="sxs-lookup"><span data-stu-id="bd1de-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="bd1de-111">Gerekli bir `Case` deyimi.</span><span class="sxs-lookup"><span data-stu-id="bd1de-111">Required in a `Case` statement.</span></span> <span data-ttu-id="bd1de-112">Eşleşme değerlerini temsil eden ifade yan tümceleri listesi `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="bd1de-113">Birden çok ifade yan tümceleri virgülle ayrılır.</span><span class="sxs-lookup"><span data-stu-id="bd1de-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="bd1de-114">Her yan tümcesi aşağıdaki biçimlerden birini gerçekleştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="bd1de-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="bd1de-115">-   *İfade1* `To` *İfade2*</span><span class="sxs-lookup"><span data-stu-id="bd1de-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="bd1de-116">-[ `Is` ] *Karşılaştırmaİşleci* *ifadesi*</span><span class="sxs-lookup"><span data-stu-id="bd1de-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="bd1de-117">-   *ifade*</span><span class="sxs-lookup"><span data-stu-id="bd1de-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="bd1de-118">Kullanım `To` için eşleşen bir dizi sınırları belirtmek için anahtar sözcüğü değerler `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="bd1de-119">Değeri `expression1` değerine eşit veya daha az olmalıdır `expression2`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="bd1de-120">Kullanım `Is` anahtar sözcüğüyle bir karşılaştırma işleci (`=`, `<>`, `<`, `<=`, `>`, veya `>=`) eşleşme değerlerinde bir kısıtlama belirtmek için `testexpression`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="bd1de-121">Varsa `Is` anahtar sözcüğü sağlanmadı, önce otomatik olarak eklenen *Karşılaştırmaİşleci*.</span><span class="sxs-lookup"><span data-stu-id="bd1de-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="bd1de-122">Yalnızca belirtme form `expression` özel bir durum olarak kabul edilir `Is` form nerede *Karşılaştırmaİşleci* eşittir işaretidir (`=`).</span><span class="sxs-lookup"><span data-stu-id="bd1de-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="bd1de-123">Bu form olarak değerlendirilir `testexpression`  =  `expression`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="bd1de-124">İfadelerde `expressionlist` türüne örtük olarak dönüştürülebilir sağlanan tüm veri türünde olabilir `testexpression` ve uygun `comparisonoperator` ile kullanıldığı iki tür için geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="bd1de-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="bd1de-125">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bd1de-125">Optional.</span></span> <span data-ttu-id="bd1de-126">Bir veya daha fazla deyimleri aşağıdaki `Case` çalışma olması durumunda `testexpression` herhangi yan tümcesinde eşleşen `expressionlist`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="bd1de-127">İsteğe bağlı.</span><span class="sxs-lookup"><span data-stu-id="bd1de-127">Optional.</span></span> <span data-ttu-id="bd1de-128">Bir veya daha fazla deyimleri aşağıdaki `Case Else` çalışma olması durumunda `testexpression` herhangi yan tümcesinde eşleşmiyor `expressionlist` herhangi birinin `Case` deyimleri.</span><span class="sxs-lookup"><span data-stu-id="bd1de-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="bd1de-129">Tanımını sonlandırır `Select`... `Case` oluşturma.</span><span class="sxs-lookup"><span data-stu-id="bd1de-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd1de-130">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bd1de-130">Remarks</span></span>  
 <span data-ttu-id="bd1de-131">Varsa `testexpression` eşleşir `Case` `expressionlist` yan tümcesi, aşağıdaki deyimleri `Case` deyimi sonraki gerçekleştirdiğinizden `Case`, `Case Else`, veya `End Select` deyimi.</span><span class="sxs-lookup"><span data-stu-id="bd1de-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="bd1de-132">Denetim sonra deyimi aşağıdaki geçer `End Select`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="bd1de-133">Varsa `testexpression` eşleşen bir `expressionlist` yan tümcesinde birden fazla `Case` yan tümcesi, yalnızca ilk eşleşmeye aşağıdaki deyimleri çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="bd1de-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="bd1de-134">`Case Else` Deyimi tanıtmak için kullanılan `elsestatements` arasında eşleşme bulunamazsa, çalıştırmak için `testexpression` ve bir `expressionlist` yan tümcesinde herhangi diğer `Case` deyimleri.</span><span class="sxs-lookup"><span data-stu-id="bd1de-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="bd1de-135">Gerekli değildir, ancak bunu sağlamak için iyi bir fikirdir bir `Case Else` deyiminde, `Select Case` işlemek için yapım öngörülemeyen `testexpression` değerleri.</span><span class="sxs-lookup"><span data-stu-id="bd1de-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="bd1de-136">Öyle değilse `Case` `expressionlist` yan tümcesi ile eşleşen `testexpression` ve hiçbir `Case Else` deyimi, deyimi aşağıdaki denetim geçer `End Select`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="bd1de-137">Birden çok ifadeyi veya aralıklar her kullanabilirsiniz `Case` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="bd1de-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="bd1de-138">Örneğin, aşağıdaki satırı geçerli değil.</span><span class="sxs-lookup"><span data-stu-id="bd1de-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="bd1de-139">`Is` Kullanılan anahtar sözcüğü `Case` ve `Case Else` deyimleri ile aynı değil [Is işlecini](../../../visual-basic/language-reference/operators/is-operator.md), nesne başvurusu karşılaştırma için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bd1de-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="bd1de-140">Aralıkları ve karakter dizeleri için birden çok ifadeyi belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd1de-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="bd1de-141">Aşağıdaki örnekte, `Case` "uygulama" tam olarak eşittir, alfabetik sırada "nuts" ve "Çorbası" arasında bir değer içeriyor veya geçerli değeri tam aynı değeri içeren herhangi bir dizeyle eşleşir `testItem`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="bd1de-142">Ayarını `Option Compare` dize karşılaştırmaları etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="bd1de-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="bd1de-143">Altında `Option Compare Text`, "Elmalar" ve "elmalar" dizeleri eşit olarak ancak altında karşılaştırmak `Option Compare Binary`, bunlar yapın.</span><span class="sxs-lookup"><span data-stu-id="bd1de-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd1de-144">A `Case` birden çok yan tümceleri deyimiyle olarak bilinen davranış sergileyen *kısa devre*.</span><span class="sxs-lookup"><span data-stu-id="bd1de-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="bd1de-145">Visual Basic yan tümcelerini soldan sağa değerlendirir ve varsa bir eşleşme ile üreten `testexpression`, kalan yan tümceleri değerlendirilmez.</span><span class="sxs-lookup"><span data-stu-id="bd1de-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="bd1de-146">Kısa devre performansı artırabilir, ancak her ifadesinde Bekleniyor durumunda beklenmeyen sonuçlara yol açabilir `expressionlist` değerlendirilecek.</span><span class="sxs-lookup"><span data-stu-id="bd1de-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="bd1de-147">Kısa devre daha fazla bilgi için bkz: [Boole ifadeleri](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bd1de-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="bd1de-148">Varsa içindeki kod bir `Case` veya `Case Else` deyimi blok bloğunda bilgilerinin başka çalışması gerekmez, blok kullanarak çıkabilirsiniz `Exit Select` deyimi.</span><span class="sxs-lookup"><span data-stu-id="bd1de-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="bd1de-149">Bu denetim deyimi aşağıdaki hemen aktarır `End Select`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="bd1de-150">`Select Case`kurulumlarını iç içe.</span><span class="sxs-lookup"><span data-stu-id="bd1de-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="bd1de-151">Her iç içe geçmiş `Select Case` yapım eşleşen olması gerekir `End Select` deyimi ve tek tamamen bulunmalıdır `Case` veya `Case Else` dış deyimi bloğunu `Select Case` yapı içinde bu iç içe geçmiş.</span><span class="sxs-lookup"><span data-stu-id="bd1de-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd1de-152">Örnek</span><span class="sxs-lookup"><span data-stu-id="bd1de-152">Example</span></span>  
 <span data-ttu-id="bd1de-153">Aşağıdaki örnek kullanan bir `Select Case` değişkenin değerine karşılık gelen bir satır yazmak için yapım `number`.</span><span class="sxs-lookup"><span data-stu-id="bd1de-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="bd1de-154">İkinci `Case` deyimi geçerli değeri ile eşleşen değerini içerdiği `number`, "6 ve 8 (bunlar dahil) arasında" Yazar deyim şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="bd1de-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd1de-155">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bd1de-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [<span data-ttu-id="bd1de-156">End deyimi</span><span class="sxs-lookup"><span data-stu-id="bd1de-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="bd1de-157">If... Then... Else deyimi</span><span class="sxs-lookup"><span data-stu-id="bd1de-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="bd1de-158">Option Compare deyimi</span><span class="sxs-lookup"><span data-stu-id="bd1de-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="bd1de-159">Exit deyimi</span><span class="sxs-lookup"><span data-stu-id="bd1de-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)