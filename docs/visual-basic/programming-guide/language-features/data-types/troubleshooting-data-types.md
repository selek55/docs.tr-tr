---
title: "Veri Türleri Sorunlarını Giderme (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d2fb1cd1be9c88ad0dd413eedb8a226fe59f41e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-data-types-visual-basic"></a><span data-ttu-id="8378a-102">Veri Türleri Sorunlarını Giderme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8378a-102">Troubleshooting Data Types (Visual Basic)</span></span>
<span data-ttu-id="8378a-103">Bu sayfada, iç veri türleri üzerinde işlemler gerçekleştirdiğinizde oluşabilecek bazı yaygın sorunlar listelenir.</span><span class="sxs-lookup"><span data-stu-id="8378a-103">This page lists some common problems that can occur when you perform operations on intrinsic data types.</span></span>  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a><span data-ttu-id="8378a-104">Kayan nokta ifadeleri eşit olarak karşılaştırmak değil</span><span class="sxs-lookup"><span data-stu-id="8378a-104">Floating-Point Expressions Do Not Compare as Equal</span></span>  
 <span data-ttu-id="8378a-105">Kayan nokta sayıları ile çalışırken ([tek bir veri türü](../../../../visual-basic/language-reference/data-types/single-data-type.md) ve [Double veri türü](../../../../visual-basic/language-reference/data-types/double-data-type.md)), ikili kesir olarak depolandığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="8378a-105">When you work with floating-point numbers ([Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) and [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md)), remember that they are stored as binary fractions.</span></span> <span data-ttu-id="8378a-106">Bu olamaz tuttukları ikili kesir değil miktar tam bir gösterimi anlamına gelir (k formunun / (2 ^ n) k ve n nerede tamsayılar).</span><span class="sxs-lookup"><span data-stu-id="8378a-106">This means they cannot hold an exact representation of any quantity that is not a binary fraction (of the form k / (2 ^ n) where k and n are integers).</span></span> <span data-ttu-id="8378a-107">Yalnızca yaklaşık değerler 0.2 (1/5 =) ve (3/10 =) 0.3 olabilirken örneğin 0,5 (1/2 =) ve (= 5/16) 0.3125 kesin değerler tutulabilir.</span><span class="sxs-lookup"><span data-stu-id="8378a-107">For example, 0.5 (= 1/2) and 0.3125 (= 5/16) can be held as precise values, whereas 0.2 (= 1/5) and 0.3 (= 3/10) can be only approximations.</span></span>  
  
 <span data-ttu-id="8378a-108">Kayan nokta değerlerine çalışmayabilir, bu nedenle imprecision, tam sonuçlarına bağlı olamaz.</span><span class="sxs-lookup"><span data-stu-id="8378a-108">Because of this imprecision, you cannot rely on exact results when you operate on floating-point values.</span></span> <span data-ttu-id="8378a-109">Özellikle, teorik olarak eşit iki değer biraz farklı sunumu olabilir.</span><span class="sxs-lookup"><span data-stu-id="8378a-109">In particular, two values that are theoretically equal might have slightly different representations.</span></span>  
  
| <span data-ttu-id="8378a-110">Kayan nokta sayıları karşılaştırmak için</span><span class="sxs-lookup"><span data-stu-id="8378a-110">To compare floating-point quantities</span></span> | 
|---| 
|<span data-ttu-id="8378a-111">1.  Kullanarak kendi fark mutlak değeri hesaplama <xref:System.Math.Abs%2A> yöntemi <xref:System.Math> sınıfını <xref:System> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="8378a-111">1.  Calculate the absolute value of their difference by using the <xref:System.Math.Abs%2A> method of the <xref:System.Math> class in the <xref:System> namespace.</span></span><br /><span data-ttu-id="8378a-112">2.  Kendi fark büyük ise pratik amaçlar için eşit olacak şekilde iki miktarları düşünebilirsiniz şekilde bir kabul edilebilir maksimum fark belirler.</span><span class="sxs-lookup"><span data-stu-id="8378a-112">2.  Determine an acceptable maximum difference, such that you can consider the two quantities to be equal for practical purposes if their difference is no larger.</span></span><br /><span data-ttu-id="8378a-113">3.  Mutlak değeri kabul edilebilir farktan farkının karşılaştırın.</span><span class="sxs-lookup"><span data-stu-id="8378a-113">3.  Compare the absolute value of the difference to the acceptable difference.</span></span>|  
  
 <span data-ttu-id="8378a-114">Aşağıdaki örnek, iki hatalı ve doğru karşılaştırma gösterir `Double` değerleri.</span><span class="sxs-lookup"><span data-stu-id="8378a-114">The following example demonstrates both incorrect and correct comparison of two `Double` values.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 <span data-ttu-id="8378a-115">Önceki örnekte kullanılmaktadır <xref:System.Double.ToString%2A> yöntemi <xref:System.Double> böylece daha iyi duyarlılık belirleyebilirsiniz yapısı `CStr` anahtar sözcüğü kullanır.</span><span class="sxs-lookup"><span data-stu-id="8378a-115">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better  precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="8378a-116">Varsayılan, 15 basamağa olmakla birlikte isteğe bağlı olarak "G17" biçimi için 17 basamaklı genişletir.</span><span class="sxs-lookup"><span data-stu-id="8378a-116">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>  
  
## <a name="mod-operator-does-not-return-accurate-result"></a><span data-ttu-id="8378a-117">Mod işleci doğru sonuç döndürmüyor</span><span class="sxs-lookup"><span data-stu-id="8378a-117">Mod Operator Does Not Return Accurate Result</span></span>  
 <span data-ttu-id="8378a-118">Kayan nokta depolama imprecision nedeniyle [Mod işleci](../../../../visual-basic/language-reference/operators/mod-operator.md) işlenen en az biri kayan nokta olduğunda beklenmeyen bir sonuç geri dönebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8378a-118">Because of the imprecision of floating-point storage, the [Mod Operator](../../../../visual-basic/language-reference/operators/mod-operator.md) can return an unexpected result when at least one of the operands is floating-point.</span></span>  
  
 <span data-ttu-id="8378a-119">[Ondalık veri türü](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) kayan Noktası temsili kullanmaz.</span><span class="sxs-lookup"><span data-stu-id="8378a-119">The [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) does not use floating-point representation.</span></span> <span data-ttu-id="8378a-120">İçinde filtresinin birçok numaraları `Single` ve `Double` tam olarak olan `Decimal` (örneğin 0.2 ve 0.3).</span><span class="sxs-lookup"><span data-stu-id="8378a-120">Many numbers that are inexact in `Single` and `Double` are exact in `Decimal` (for example 0.2 and 0.3).</span></span> <span data-ttu-id="8378a-121">Aritmetik rağmen yavaş `Decimal` daha kayan nokta, bu daha iyi duyarlık elde etmek için performans düşüşünü olabilir.</span><span class="sxs-lookup"><span data-stu-id="8378a-121">Although arithmetic is slower in `Decimal` than in floating-point, it might be worth the performance decrease to achieve better precision.</span></span>  
  
|<span data-ttu-id="8378a-122">Kayan nokta sayıları tamsayı kalanını bulmak için</span><span class="sxs-lookup"><span data-stu-id="8378a-122">To find the integer remainder of floating-point quantities</span></span>|  
|---|  
|<span data-ttu-id="8378a-123">1.  Bildirme değişkenleri olarak `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8378a-123">1.  Declare variables as `Decimal`.</span></span><br /><span data-ttu-id="8378a-124">2.  Değişmez değer türü karakteri kullanmak `D` değişmez değerleri için zorlamak için `Decimal`, bunların değerleri için çok büyük olduğu durumlarda `Long` veri türü.</span><span class="sxs-lookup"><span data-stu-id="8378a-124">2.  Use the literal type character `D` to force literals to `Decimal`, in case their values are too large for the `Long` data type.</span></span>|  
  
 <span data-ttu-id="8378a-125">Aşağıdaki örnek, kayan nokta işlenenleri imprecision olası gösterir.</span><span class="sxs-lookup"><span data-stu-id="8378a-125">The following example demonstrates the potential imprecision of floating-point operands.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 <span data-ttu-id="8378a-126">Önceki örnekte kullanılmaktadır <xref:System.Double.ToString%2A> yöntemi <xref:System.Double> böylece daha iyi duyarlılık belirleyebilirsiniz yapısı `CStr` anahtar sözcüğü kullanır.</span><span class="sxs-lookup"><span data-stu-id="8378a-126">The previous example uses the <xref:System.Double.ToString%2A> method of the <xref:System.Double> structure so that it can specify better precision than the `CStr` keyword uses.</span></span> <span data-ttu-id="8378a-127">Varsayılan, 15 basamağa olmakla birlikte isteğe bağlı olarak "G17" biçimi için 17 basamaklı genişletir.</span><span class="sxs-lookup"><span data-stu-id="8378a-127">The default is 15 digits, but the "G17" format extends it to 17 digits.</span></span>  
  
 <span data-ttu-id="8378a-128">Çünkü `zeroPointTwo` olan `Double`, değeri 0.2 için bir sonsuz yinelenen ikili 0.20000000000000001 saklı değerine sahip bölümüdür.</span><span class="sxs-lookup"><span data-stu-id="8378a-128">Because `zeroPointTwo` is `Double`, its value for 0.2 is an infinitely repeating binary fraction with a stored value of 0.20000000000000001.</span></span> <span data-ttu-id="8378a-129">Bu miktar 2.0 bölerek 0.19999999999999991 kalanı ile 9.9999999999999995 verir.</span><span class="sxs-lookup"><span data-stu-id="8378a-129">Dividing 2.0 by this quantity yields 9.9999999999999995 with a remainder of 0.19999999999999991.</span></span>  
  
 <span data-ttu-id="8378a-130">İçin ifadede `decimalRemainder`, değişmez değer türü karakteri `D` her iki işlenen zorlar `Decimal`, ve 0.2 kesin bir gösterimi.</span><span class="sxs-lookup"><span data-stu-id="8378a-130">In the expression for `decimalRemainder`, the literal type character `D` forces both operands to `Decimal`, and 0.2 has a precise representation.</span></span> <span data-ttu-id="8378a-131">Bu nedenle `Mod` işleci 0,0 beklenen geri kalanı verir.</span><span class="sxs-lookup"><span data-stu-id="8378a-131">Therefore the `Mod` operator yields the expected remainder of 0.0.</span></span>  
  
 <span data-ttu-id="8378a-132">Bunu bildirmek yeterli değildir `decimalRemainder` olarak `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="8378a-132">Note that it is not sufficient to declare `decimalRemainder` as `Decimal`.</span></span> <span data-ttu-id="8378a-133">Değişmez değerler için zorlaması gerekir `Decimal`, veya kullandıkları `Double` varsayılan ve `decimalRemainder` aynı yanlış değerine alır `doubleRemainder`.</span><span class="sxs-lookup"><span data-stu-id="8378a-133">You must also force the literals to `Decimal`, or they use `Double` by default and `decimalRemainder` receives the same inaccurate value as `doubleRemainder`.</span></span>  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a><span data-ttu-id="8378a-134">Boolean türü sayısal türe doğru şekilde dönüştürmez</span><span class="sxs-lookup"><span data-stu-id="8378a-134">Boolean Type Does Not Convert to Numeric Type Accurately</span></span>  
 <span data-ttu-id="8378a-135">[Boole veri türü](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) değerlerini, sayı olarak depolanmaz ve depolanan değerlerin sayıya eşit olması amaçlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="8378a-135">[Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="8378a-136">Önceki sürümlerle uyumluluk için [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] dönüşüm anahtar sözcükleri sağlar ([CType işlevi](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, vb.) arasında dönüştürme yapma `Boolean` ve sayısal türler.</span><span class="sxs-lookup"><span data-stu-id="8378a-136">For compatibility with earlier versions, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides conversion keywords ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, and so on) to convert between `Boolean` and numeric types.</span></span> <span data-ttu-id="8378a-137">Bununla birlikte, diğer diller bazen dönüştürmeler gibi farklı şekilde gerçekleştirmeniz [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="8378a-137">However, other languages sometimes perform these conversions differently, as do the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] methods.</span></span>  
  
 <span data-ttu-id="8378a-138">Hiçbir zaman eşdeğer sayısal değerler için güvenen kod yazmanız gerekir `True` ve `False`.</span><span class="sxs-lookup"><span data-stu-id="8378a-138">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="8378a-139">Mümkün olduğunda, kullanımını kısıtlamalısınız `Boolean` , bunlar tasarlanan mantıksal değerleri değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="8378a-139">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span> <span data-ttu-id="8378a-140">Karışık gerekir, `Boolean` ve sayısal değerleri, seçtiğiniz dönüştürme yöntemi anladığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="8378a-140">If you must mix `Boolean` and numeric values, make sure that you understand the conversion method that you select.</span></span>  
  
### <a name="conversion-in-visual-basic"></a><span data-ttu-id="8378a-141">Visual Basic'te dönüştürme</span><span class="sxs-lookup"><span data-stu-id="8378a-141">Conversion in Visual Basic</span></span>  
 <span data-ttu-id="8378a-142">Kullandığınızda `CType` veya `CBool` sayısal veri türlerine dönüştürmek için dönüşüm anahtar sözcükleri `Boolean`, 0 olur `False` ve diğer tüm değerler duruma `True`.</span><span class="sxs-lookup"><span data-stu-id="8378a-142">When you use the `CType` or `CBool` conversion keywords to convert numeric data types to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="8378a-143">Dönüştürürken `Boolean` dönüşüm anahtar sözcükleri kullanarak sayısal türler değerlere `False` 0 olur ve `True` -1 olur.</span><span class="sxs-lookup"><span data-stu-id="8378a-143">When you convert `Boolean` values to numeric types by using the conversion keywords, `False` becomes 0 and `True` becomes -1.</span></span>  
  
### <a name="conversion-in-the-framework"></a><span data-ttu-id="8378a-144">Framework'te dönüştürme</span><span class="sxs-lookup"><span data-stu-id="8378a-144">Conversion in the Framework</span></span>  
 <span data-ttu-id="8378a-145"><xref:System.Convert.ToInt32%2A> Yöntemi <xref:System.Convert> sınıfını <xref:System> ad alanı dönüştürür `True` + 1 için.</span><span class="sxs-lookup"><span data-stu-id="8378a-145">The <xref:System.Convert.ToInt32%2A> method of the <xref:System.Convert> class in the <xref:System> namespace converts `True` to +1.</span></span>  
  
 <span data-ttu-id="8378a-146">Dönüştürürseniz gerekir, bir `Boolean` değer sayısal veri türü için dikkatli olun hakkında hangi dönüştürme yöntemini kullanın.</span><span class="sxs-lookup"><span data-stu-id="8378a-146">If you must convert a `Boolean` value to a numeric data type, be careful about which conversion method you use.</span></span>  
  
## <a name="character-literal-generates-compiler-error"></a><span data-ttu-id="8378a-147">Derleyici Hatası karakter sabit değeri oluşturur</span><span class="sxs-lookup"><span data-stu-id="8378a-147">Character Literal Generates Compiler Error</span></span>  
 <span data-ttu-id="8378a-148">Herhangi bir tür karakteri olmadığında [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] veri türleri değişmez değerleri için varsayılan varsayar.</span><span class="sxs-lookup"><span data-stu-id="8378a-148">In the absence of any type characters, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] assumes default data types for literals.</span></span> <span data-ttu-id="8378a-149">Değişmez değer bir karakteri için varsayılan türü — tırnak işaretleri içine (`" "`) — olduğu `String`.</span><span class="sxs-lookup"><span data-stu-id="8378a-149">The default type for a character literal — enclosed in quotation marks (`" "`) — is `String`.</span></span>  
  
 <span data-ttu-id="8378a-150">`String` Veri türü için genişletmek değil [Char veri türü](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8378a-150">The `String` data type does not widen to the [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span> <span data-ttu-id="8378a-151">Bunun anlamı bir hazır değer atamak istiyorsanız bir `Char` değişken, daraltma dönüştürme yapmak veya sabit zorla `Char` türü.</span><span class="sxs-lookup"><span data-stu-id="8378a-151">This means that if you want to assign a literal to a `Char` variable, you must either make a narrowing conversion or force the literal to the `Char` type.</span></span>  

|<span data-ttu-id="8378a-152">Bir Char değişkeni ya da sabit değer atamak için değişmez değer oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="8378a-152">To create a Char literal to assign to a variable or constant</span></span>|
|---|  
|<span data-ttu-id="8378a-153">1.  Değişken ya da sabit değer olarak bildirmek `Char`.</span><span class="sxs-lookup"><span data-stu-id="8378a-153">1.  Declare the variable or constant as `Char`.</span></span><br /><span data-ttu-id="8378a-154">2.  Karakter değeri tırnak işaretleri içine alın (`" "`).</span><span class="sxs-lookup"><span data-stu-id="8378a-154">2.  Enclose the character value in quotation marks (`" "`).</span></span><br /><span data-ttu-id="8378a-155">3.  Değişmez değer türü karakteri ile kapanış çift tırnak işareti izleyin `C` literal zorlamak için `Char`.</span><span class="sxs-lookup"><span data-stu-id="8378a-155">3.  Follow the closing double quotation mark with the literal type character `C` to force the literal to `Char`.</span></span> <span data-ttu-id="8378a-156">Bu tür denetlemesi geçiş yaparsanız gereklidir ([Option Strict deyimi](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) olan `On`, ve her durumda tercih edilir.</span><span class="sxs-lookup"><span data-stu-id="8378a-156">This is necessary if the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On`, and it is desirable in any case.</span></span>|  
  
 <span data-ttu-id="8378a-157">Aşağıdaki örnek, bir hazır değer başarılı ve başarısız atamalarını gösterir bir `Char` değişkeni.</span><span class="sxs-lookup"><span data-stu-id="8378a-157">The following example demonstrates both unsuccessful and successful assignments of a literal to a `Char` variable.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 <span data-ttu-id="8378a-158">Her zaman bir riski yoktur daraltma dönüşümleri kullanarak çünkü çalışma zamanında başarısız.</span><span class="sxs-lookup"><span data-stu-id="8378a-158">There is always a risk in using narrowing conversions, because they can fail at run time.</span></span> <span data-ttu-id="8378a-159">Örneğin, bir dönüştürme `String` için `Char` başarısız `String` değeri birden fazla karakter içeriyor.</span><span class="sxs-lookup"><span data-stu-id="8378a-159">For example, a conversion from `String` to `Char` can fail if the `String` value contains more than one character.</span></span> <span data-ttu-id="8378a-160">Bu nedenle, daha iyi kullanmak için programlama `C` karakteri yazın.</span><span class="sxs-lookup"><span data-stu-id="8378a-160">Therefore, it is better programming to use the `C` type character.</span></span>  
  
## <a name="string-conversion-fails-at-run-time"></a><span data-ttu-id="8378a-161">Dize dönüştürme çalışma zamanında başarısız olur</span><span class="sxs-lookup"><span data-stu-id="8378a-161">String Conversion Fails at Run Time</span></span>  
 <span data-ttu-id="8378a-162">[Dize veri türü](../../../../visual-basic/language-reference/data-types/string-data-type.md) çok az genişletme Dönüşümlerde katılır.</span><span class="sxs-lookup"><span data-stu-id="8378a-162">The [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) participates in very few widening conversions.</span></span> <span data-ttu-id="8378a-163">`String`yalnızca kendisine widens ve `Object`, yalnızca ve `Char` ve `Char()` (bir `Char` array) için genişletmek `String`.</span><span class="sxs-lookup"><span data-stu-id="8378a-163">`String` widens only to itself and `Object`, and only `Char` and `Char()` (a `Char` array) widen to `String`.</span></span> <span data-ttu-id="8378a-164">Bunun nedeni, `String` değişkenleri ve sabitleri diğer veri türleri bulunamaz değerler içerebilir.</span><span class="sxs-lookup"><span data-stu-id="8378a-164">This is because `String` variables and constants can contain values that other data types cannot contain.</span></span>  
  
 <span data-ttu-id="8378a-165">Tür denetleme zaman geçiş ([Option Strict deyimi](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) olan `On`, tüm örtük daraltma dönüşümleri derleyici izin vermez.</span><span class="sxs-lookup"><span data-stu-id="8378a-165">When the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `On`, the compiler disallows all implicit narrowing conversions.</span></span> <span data-ttu-id="8378a-166">Bu ilgili olanlar içerir `String`.</span><span class="sxs-lookup"><span data-stu-id="8378a-166">This includes those involving `String`.</span></span> <span data-ttu-id="8378a-167">Kodunuzu dönüşüm anahtar sözcükleri gibi kullanmaya devam edebilirsiniz `CStr` ve [CType işlevi](../../../../visual-basic/language-reference/functions/ctype-function.md), hangi doğrudan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] dönüştürme çalışır.</span><span class="sxs-lookup"><span data-stu-id="8378a-167">Your code can still use conversion keywords such as `CStr` and [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), which direct the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to attempt the conversion.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8378a-168">Daraltma dönüştürme hatası öğelerde bulunan dönüştürmeleri için gizlenen bir `For Each…Next` for döngüsü denetim değişkeni koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="8378a-168">The narrowing-conversion error is suppressed for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="8378a-169">Daha fazla bilgi ve örnekler için "Daraltma dönüşümleri" bölümüne bakın [For Each... Sonraki deyim](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8378a-169">For more information and examples, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
### <a name="narrowing-conversion-protection"></a><span data-ttu-id="8378a-170">Dönüştürme koruma daraltma</span><span class="sxs-lookup"><span data-stu-id="8378a-170">Narrowing Conversion Protection</span></span>  
 <span data-ttu-id="8378a-171">Daraltma dönüşümleri dezavantajı, çalışma zamanında yük devredebildiğini ' dir.</span><span class="sxs-lookup"><span data-stu-id="8378a-171">The disadvantage of narrowing conversions is that they can fail at run time.</span></span> <span data-ttu-id="8378a-172">Örneğin, bir `String` değişken içeriyor, herhangi bir şey, "True" veya "False" onu dönüştürülemiyor dışında `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="8378a-172">For example, if a `String` variable contains anything other than "True" or "False," it cannot be converted to `Boolean`.</span></span> <span data-ttu-id="8378a-173">Noktalama karakterleri içeriyorsa, herhangi bir sayısal tür dönüştürme başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="8378a-173">If it contains punctuation characters, conversion to any numeric type fails.</span></span> <span data-ttu-id="8378a-174">Bilmiyorsanız, `String` değişken her zaman hedef türünü kabul edebilir değerlerini tutan, dönüştürme denemelisiniz değil.</span><span class="sxs-lookup"><span data-stu-id="8378a-174">Unless you know that your `String` variable always holds values that the destination type can accept, you should not try a conversion.</span></span>  
  
 <span data-ttu-id="8378a-175">Dönüştürürseniz gerekir, `String` başka bir veri türüne güvenli denenen dönüştürmede kapsamak için yordamdır [deneyin... Catch... Finally ifadesi](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8378a-175">If you must convert from `String` to another data type, the safest procedure is to enclose the attempted conversion in the [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="8378a-176">Bu, bir çalışma zamanı hatası ile ilgilenir sağlar.</span><span class="sxs-lookup"><span data-stu-id="8378a-176">This lets you deal with a run-time failure.</span></span>  
  
### <a name="character-arrays"></a><span data-ttu-id="8378a-177">Karakter dizileri</span><span class="sxs-lookup"><span data-stu-id="8378a-177">Character Arrays</span></span>  
 <span data-ttu-id="8378a-178">Tek bir `Char` ve bir dizi `Char` her ikisi de genişletmek için öğeleri `String`.</span><span class="sxs-lookup"><span data-stu-id="8378a-178">A single `Char` and an array of `Char` elements both widen to `String`.</span></span> <span data-ttu-id="8378a-179">Ancak, `String` için genişletmek değil `Char()`.</span><span class="sxs-lookup"><span data-stu-id="8378a-179">However, `String` does not widen to `Char()`.</span></span> <span data-ttu-id="8378a-180">Dönüştürülecek bir `String` değeri bir `Char` kullanabileceğiniz diziye <xref:System.String.ToCharArray%2A> yöntemi <xref:System.String?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="8378a-180">To convert a `String` value to a `Char` array, you can use the <xref:System.String.ToCharArray%2A> method of the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
### <a name="meaningless-values"></a><span data-ttu-id="8378a-181">Anlamsız değerleri</span><span class="sxs-lookup"><span data-stu-id="8378a-181">Meaningless Values</span></span>  
 <span data-ttu-id="8378a-182">Genel olarak, `String` değerlerini diğer veri türleri anlamlı değildir ve dönüştürme, yüksek oranda yapay ve tehlikeli.</span><span class="sxs-lookup"><span data-stu-id="8378a-182">In general, `String` values are not meaningful in other data types, and conversion is highly artificial and dangerous.</span></span> <span data-ttu-id="8378a-183">Mümkün olduğunda, kullanımını kısıtlamalısınız `String` , bunlar tasarlanan karakter dizileri değişkenleri.</span><span class="sxs-lookup"><span data-stu-id="8378a-183">Whenever possible, you should restrict usage of `String` variables to the character sequences for which they are designed.</span></span> <span data-ttu-id="8378a-184">Hiçbir zaman diğer türleri eşdeğer değerleri dayanan kod yazmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8378a-184">You should never write code that relies on equivalent values in other types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8378a-185">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8378a-185">See Also</span></span>  
 [<span data-ttu-id="8378a-186">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="8378a-186">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="8378a-187">Tür karakterleri</span><span class="sxs-lookup"><span data-stu-id="8378a-187">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="8378a-188">Değer türleri ve başvuru türleri</span><span class="sxs-lookup"><span data-stu-id="8378a-188">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="8378a-189">Visual Basic'de tür dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="8378a-189">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="8378a-190">Veri türleri</span><span class="sxs-lookup"><span data-stu-id="8378a-190">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="8378a-191">Tür dönüşüm işlevleri</span><span class="sxs-lookup"><span data-stu-id="8378a-191">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="8378a-192">Veri türlerinin etkili kullanımı</span><span class="sxs-lookup"><span data-stu-id="8378a-192">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)