---
title: "Nasıl yapılır: Bir Dönüşüm İşleci Tanımlama (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0f9e63ba039a48226186fa4ce118d3e47b5673e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="71f21-102">Nasıl yapılır: Bir Dönüşüm İşleci Tanımlama (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71f21-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="71f21-103">Bir sınıf veya yapı tanımladıysanız, sınıf veya yapı türüne ve başka bir veri türü arasında tür dönüştürme işleci tanımlayabilirsiniz (gibi `Integer`, `Double`, veya `String`).</span><span class="sxs-lookup"><span data-stu-id="71f21-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="71f21-104">Tür dönüştürme olarak tanımlayan bir [CType işlevi](../../../../visual-basic/language-reference/functions/ctype-function.md) yordam sınıf veya yapı içinde.</span><span class="sxs-lookup"><span data-stu-id="71f21-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="71f21-105">Tüm dönüştürme yordamları olmalıdır `Public Shared`, ve her biri ya da belirtmeniz gerekir [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) veya [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="71f21-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="71f21-106">Bir sınıf veya yapı bir işleci tanımlama olarak da adlandırılır *aşırı* işleci.</span><span class="sxs-lookup"><span data-stu-id="71f21-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71f21-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="71f21-107">Example</span></span>  
 <span data-ttu-id="71f21-108">Aşağıdaki örnek olarak adlandırılan bir yapıyı arasında dönüştürme işleçleri tanımlayan `digit` ve `Byte`.</span><span class="sxs-lookup"><span data-stu-id="71f21-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="71f21-109">Yapıyı test `digit` aşağıdaki kod ile.</span><span class="sxs-lookup"><span data-stu-id="71f21-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="71f21-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="71f21-110">See Also</span></span>  
 [<span data-ttu-id="71f21-111">İşleç yordamları</span><span class="sxs-lookup"><span data-stu-id="71f21-111">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="71f21-112">Nasıl yapılır: bir işleci tanımlama</span><span class="sxs-lookup"><span data-stu-id="71f21-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="71f21-113">Nasıl yapılır: bir işleç yordamı çağırma</span><span class="sxs-lookup"><span data-stu-id="71f21-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="71f21-114">Nasıl yapılır: işleçleri tanımlayan bir sınıf kullanma</span><span class="sxs-lookup"><span data-stu-id="71f21-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="71f21-115">Operator deyimi</span><span class="sxs-lookup"><span data-stu-id="71f21-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="71f21-116">Structure deyimi</span><span class="sxs-lookup"><span data-stu-id="71f21-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="71f21-117">Nasıl yapılır: bir yapıyı bildirme</span><span class="sxs-lookup"><span data-stu-id="71f21-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="71f21-118">Örtük ve açık dönüştürmeler</span><span class="sxs-lookup"><span data-stu-id="71f21-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="71f21-119">Genişletme ve daraltma dönüşümleri</span><span class="sxs-lookup"><span data-stu-id="71f21-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)