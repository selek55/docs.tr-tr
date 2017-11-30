---
title: "Tarih ve saatlerle aritmetik işlemler gerçekleştirme"
ms.custom: 
ms.date: 04/10/2017
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
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: def43f84186b53f9b0d2ade0a5a92e59606ee2af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="8c64d-102">Tarih ve saatlerle aritmetik işlemler gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="8c64d-102">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="8c64d-103">Olsa da hem <xref:System.DateTime> ve <xref:System.DateTimeOffset> aritmetik işlemler sonuçlarını çok farklı olan, yapıları değerlerine aritmetik işlemler gerçekleştirme üyeleri belirtin.</span><span class="sxs-lookup"><span data-stu-id="8c64d-103">Although both the <xref:System.DateTime> and the <xref:System.DateTimeOffset> structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="8c64d-104">Bu konuda bu farklılıkları inceler, tarih ve saat verilerini saat dilimi tanıma derece ilgilidir ve tam olarak tarih ve saat verilerini kullanarak saat dilimi kullanan işlemlerini gerçekleştirmek nasıl ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="8c64d-104">This topic examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="8c64d-105">Karşılaştırmaları ve DateTime değerlerini içeren aritmetik işlemler</span><span class="sxs-lookup"><span data-stu-id="8c64d-105">Comparisons and arithmetic operations with DateTime values</span></span>

<span data-ttu-id="8c64d-106"><xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Özelliği sağlayan bir <xref:System.DateTimeKind> tarih ve saat yerel saat, Eşgüdümlü Evrensel Saat (UTC) veya belirtilmeyen bir saat dilimi süreyi temsil edip etmediğini göstermek için atanacak değer.</span><span class="sxs-lookup"><span data-stu-id="8c64d-106">The <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> property allows a <xref:System.DateTimeKind> value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="8c64d-107">Ancak, bu sınırlı saat dilimi bilgilerini karşılaştırma veya tarih ve saat aritmetiği üzerinde gerçekleştirme göz ardı edilir <xref:System.DateTimeKind> değerleri.</span><span class="sxs-lookup"><span data-stu-id="8c64d-107">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on <xref:System.DateTimeKind> values.</span></span> <span data-ttu-id="8c64d-108">Geçerli yerel saat geçerli UTC saati ile karşılaştırır, aşağıdaki örnekte bu gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-108">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<span data-ttu-id="8c64d-109"><xref:System.DateTime.CompareTo%28System.DateTime%29> Yöntemi raporları yerel saat öncesi olduğunu (veya küçüktür) UTC saati ve çıkarma işlemi gösterir, UTC ve bir sistem için yerel saati arasındaki farkı ABD Pasifik Standart saat dilimi yedi saattir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-109">The <xref:System.DateTime.CompareTo%28System.DateTime%29> method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="8c64d-110">Ancak bu iki değer zamanında tek bir noktadan farklı sunumu sağladığından, bu durumda bu zaman aralığı UTC yerel saat diliminin uzaklık tamamen önlemlerine temizleyin.</span><span class="sxs-lookup"><span data-stu-id="8c64d-110">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span>

<span data-ttu-id="8c64d-111">Genellikle daha <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> özellik tarafından döndürülen sonuçlar etkilemez <xref:System.DateTime.Kind> karşılaştırma ve aritmetik yöntemleri (zaman içinde iki özdeş noktaları karşılaştırması da anlaşılacağı gibi), ancak bu sonuçlar yorumu etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-111">More generally, the <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> property does not affect the results returned by <xref:System.DateTime.Kind> comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="8c64d-112">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="8c64d-112">For example:</span></span>

* <span data-ttu-id="8c64d-113">İki tarih ve saat değerleri, tüm aritmetik işlemin sonucu olarak gerçekleştirilen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> özellikleri her iki eşit <xref:System.DateTimeKind> iki değer arasındaki gerçek zaman aralığını yansıtır.</span><span class="sxs-lookup"><span data-stu-id="8c64d-113">The result of any arithmetic operation performed on two date and time values whose <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> properties both equal <xref:System.DateTimeKind> reflects the actual time interval between the two values.</span></span> <span data-ttu-id="8c64d-114">Benzer şekilde, bu tür iki tarih ve saat değerleri karşılaştırma doğru şekilde zamanları arasında ilişki yansıtır.</span><span class="sxs-lookup"><span data-stu-id="8c64d-114">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="8c64d-115">İki tarih ve saat değerleri, tüm aritmetik veya Karşılaştırma işleminin sonucu gerçekleştirilen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> özellikleri her iki eşit <xref:System.DateTimeKind> veya farklı olan iki tarih ve saat değerleri <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> özellik değerlerini saatin fark yansıtır iki değer arasında.</span><span class="sxs-lookup"><span data-stu-id="8c64d-115">The result of any arithmetic or comparison operation performed on two date and time values whose <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> properties both equal <xref:System.DateTimeKind> or on two date and time values with different <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> property values reflects the difference in clock time between the two values.</span></span>

* <span data-ttu-id="8c64d-116">Yerel tarih ve saat değerleri aritmetik veya karşılaştırma işlemleri belirli bir değeri belirsiz veya geçersiz ya da yerel saat diliminin geçiş ya da gün ışığından yararlanma neden herhangi ayarlama kuralları etkisini hesabı yararlanabilir mi olup olmadığını düşünün zaman kazandırır.</span><span class="sxs-lookup"><span data-stu-id="8c64d-116">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="8c64d-117">Karşılaştırır veya UTC ve yerel saat arasındaki farkı hesaplar herhangi bir işlem sonucu UTC yerel saat diliminin uzaklık eşit bir zaman aralığı içerir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-117">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span>

* <span data-ttu-id="8c64d-118">Karşılaştırır veya belirtilmeyen bir saat ve UTC veya yerel saat arasındaki farkı hesaplar herhangi bir işlem basit saatin yansıtır.</span><span class="sxs-lookup"><span data-stu-id="8c64d-118">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="8c64d-119">Saat dilimi farkları değil olarak kabul edilir ve sonuç saat dilimi ayarlama kuralları uygulama yansıtmaz.</span><span class="sxs-lookup"><span data-stu-id="8c64d-119">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span>

* <span data-ttu-id="8c64d-120">Karşılaştırır veya iki arasındaki farkı hesaplar herhangi bir işlem süreleri, iki farklı saat diliminde saati arasındaki farkı yansıtır bilinmeyen bir aralık içerebilir belirtilmemiş.</span><span class="sxs-lookup"><span data-stu-id="8c64d-120">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="8c64d-121">Hangi saat diliminde farklar tarih ve saat hesaplamaları etkilemez birçok senaryo vardır (bunlardan bazıları, tartışma için bkz [DateTime, DateTimeOffset, TimeSpan ve Timezoneınfo arasında seçim](../../../docs/standard/datetime/choosing-between-datetime.md)) veya içine bağlamı Tarih ve saat veri karşılaştırma veya aritmetik işlemler anlamını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="8c64d-121">There are many scenarios in which time zone differences do not affect date and time calculations (for a discussion of some of these, see [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="8c64d-122">Karşılaştırmaları ve DateTimeOffset değerlerle aritmetik işlemler</span><span class="sxs-lookup"><span data-stu-id="8c64d-122">Comparisons and arithmetic operations with DateTimeOffset values</span></span>

<span data-ttu-id="8c64d-123">A <xref:System.DateTimeOffset> değil yalnızca bir tarih ve saat, aynı zamanda bu tarih ve saat UTC'ye göre belirsizliğe tanımlayan bir uzaklık değeri içerir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-123">A <xref:System.DateTimeOffset> value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="8c64d-124">Bu biraz farklı biçimde bir eşitlik için tanımlamanızı mümkün kılar <xref:System.DateTimeOffset> değerleri.</span><span class="sxs-lookup"><span data-stu-id="8c64d-124">This makes it possible to define equality somewhat differently than for <xref:System.DateTimeOffset> values.</span></span> <span data-ttu-id="8c64d-125">Oysa <xref:System.DateTime> değerleri aynı tarih ve saat değeri varsa eşit olan <xref:System.DateTimeOffset> değerler her ikisi de aynı noktasına zamanında başvurursanız eşit.</span><span class="sxs-lookup"><span data-stu-id="8c64d-125">Whereas <xref:System.DateTime> values are equal if they have the same date and time value, <xref:System.DateTimeOffset> values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="8c64d-126">Böylece bir <xref:System.DateTimeOffset> değeri daha kesin ve küçük karşılaştırmaları ve iki tarih ve saat arasındaki aralığı belirlemek çoğu aritmetik işlemler kullanıldığında yorumlama gerekmektedir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-126">This makes a <xref:System.DateTimeOffset> value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="8c64d-127">Aşağıdaki örnek, <xref:System.DateTimeOffset> UTC ve yerel karşılaştırıldığında önceki örnek eşdeğer <xref:System.DateTimeOffset> değerlerini, davranış bu farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-127">The following example, which is the <xref:System.DateTimeOffset> equivalent to the previous example that compared local and UTC <xref:System.DateTimeOffset> values, illustrates this difference in behavior.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

<span data-ttu-id="8c64d-128">Bu örnekte, <xref:System.DateTimeOffset.CompareTo%2A> yöntemi gösterir geçerli yerel saat ve geçerli UTC saati olduğundan eşittir ve çıkarma, <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> değerlerini gösteren iki kez arasındaki fark olduğunu <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8c64d-128">In this example, the <xref:System.DateTimeOffset.CompareTo%2A> method indicates that the current local time and the current UTC time are equal, and subtraction of <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> values indicates that the difference between the two times is <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8c64d-129">Kullanmanın baş sınırlaması <xref:System.DateTimeOffset> tarih ve saat aritmetiği değerleri olduğundan, bu, ancak <xref:System.DateTimeOffset> değerlere sahip bazı saat dilimi tanıma, bunlar tam olarak saat dilimi farkında değildir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-129">The chief limitation of using <xref:System.DateTimeOffset> values in date and time arithmetic is that although <xref:System.DateTimeOffset> values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="8c64d-130">Ancak <xref:System.DateTimeOffset> değerinin uzaklığı yansıtır UTC saat diliminin uzaklığı olduğunda bir <xref:System.DateTimeOffset> değişken değeri ilk atandığı, saat dilimine bundan sonra ilişkilendirmesi haline gelir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-130">Although the <xref:System.DateTimeOffset> value's offset reflects a time zone's offset from UTC when a <xref:System.DateTimeOffset> variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="8c64d-131">Artık doğrudan tanımlanabilen bir saat ile ilişkili olduğundan, toplama ve çıkarma tarih ve saat aralığı dikkate almaz bir saat diliminin ayarlama kuralları.</span><span class="sxs-lookup"><span data-stu-id="8c64d-131">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span>

<span data-ttu-id="8c64d-132">Göstermek için gün ışığından yararlanma saati ABD geçişi Orta standart saat dilimi 2: 00'da gerçekleşir</span><span class="sxs-lookup"><span data-stu-id="8c64d-132">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="8c64d-133">9 Mart 2008'de.</span><span class="sxs-lookup"><span data-stu-id="8c64d-133">on March 9, 2008.</span></span> <span data-ttu-id="8c64d-134">Bu, iki ve bir yarım saat aralığı 1: 30'da, Orta Standart Saati için ekleme anlamına gelir</span><span class="sxs-lookup"><span data-stu-id="8c64d-134">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="8c64d-135">9 Mart 2008'de bir tarih ve saat 5: 00'da, üretmesi gerekir</span><span class="sxs-lookup"><span data-stu-id="8c64d-135">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="8c64d-136">9 Mart 2008'de.</span><span class="sxs-lookup"><span data-stu-id="8c64d-136">on March 9, 2008.</span></span> <span data-ttu-id="8c64d-137">Aşağıdaki örnekte gösterildiği gibi ancak ek 4: 00'da sonucudur</span><span class="sxs-lookup"><span data-stu-id="8c64d-137">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="8c64d-138">9 Mart 2008'de.</span><span class="sxs-lookup"><span data-stu-id="8c64d-138">on March 9, 2008.</span></span> <span data-ttu-id="8c64d-139">Zaman içinde duyuyoruz ilgilenen saat diliminde olmasa da bu işlem bu sonucunu doğru noktası, zaman içindeki temsil Not (diğer bir deyişle, beklenen saat dilimi yok uzaklığı).</span><span class="sxs-lookup"><span data-stu-id="8c64d-139">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="8c64d-140">Saat dilimleri kez aritmetik işlemler</span><span class="sxs-lookup"><span data-stu-id="8c64d-140">Arithmetic operations with times in time zones</span></span>

<span data-ttu-id="8c64d-141"><xref:System.TimeZoneInfo> Sınıfı, bunlar zaman bir saat diliminden diğerine dönüştürme yükleyen ayarlamalar otomatik olarak Uygula dönüştürme yöntemleri sayısını içerir.</span><span class="sxs-lookup"><span data-stu-id="8c64d-141">The <xref:System.TimeZoneInfo> class includes a number of conversion methods that automatically apply adjustments when they convert times from one time zone to another.</span></span> <span data-ttu-id="8c64d-142">Bunlar aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="8c64d-142">These include the following:</span></span>

* <span data-ttu-id="8c64d-143"><xref:System.TimeZoneInfo.ConvertTime%2A> Ve <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> saatleri herhangi iki saat dilimleri arasında dönüştürme yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="8c64d-143">The <xref:System.TimeZoneInfo.ConvertTime%2A> and <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> methods, which convert times between any two time zones.</span></span>

* <span data-ttu-id="8c64d-144"><xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> Ve <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> belirli bir saat dilimi zamanında UTC'ye dönüştürmek veya belirli bir saat dilimi zamana UTC Dönüştürme yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="8c64d-144">The <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> and <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> methods, which convert the time in a particular time zone to UTC, or convert UTC to the time in a particular time zone.</span></span>

<span data-ttu-id="8c64d-145">Ayrıntılar için bkz [saatleri saat dilimleri arasında dönüştürme](../../../docs/standard/datetime/converting-between-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="8c64d-145">For details, see [Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md).</span></span>

<span data-ttu-id="8c64d-146"><xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> Sınıfı, tarih ve saat aritmetiği gerçekleştirdiğinizde, otomatik olarak ayarlama kuralları geçerli herhangi bir yöntem sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="8c64d-146">The <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="8c64d-147">Ancak, sizin için UTC saati bir saat diliminde dönüştürülürken aritmetik işlemi gerçekleştiren ve saat dilimi zamanında dön UTC Dönüştürme bunu yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8c64d-147">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="8c64d-148">Ayrıntılar için bkz [nasıl yapılır: tarih ve saat aritmetiği saat dilimini kullanır](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).</span><span class="sxs-lookup"><span data-stu-id="8c64d-148">For details, see [How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="8c64d-149">Örneğin, aşağıdaki kod iki-ve-a-yarım saat 2: 00'da için eklenen önceki kod benzer</span><span class="sxs-lookup"><span data-stu-id="8c64d-149">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="8c64d-150">9 Mart 2008'de.</span><span class="sxs-lookup"><span data-stu-id="8c64d-150">on March 9, 2008.</span></span> <span data-ttu-id="8c64d-151">Ancak, tarih ve saat aritmetiği gerçekleştirir ve ardından sonucu geri Orta Standart Saati UTC dönüştürür önce UTC'ye Orta Standart Saati dönüştürmesi nedeniyle sonuçta elde edilen zaman Orta standart saat diliminin gün ışığından geçiş yansıtır süre.</span><span class="sxs-lookup"><span data-stu-id="8c64d-151">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a><span data-ttu-id="8c64d-152">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="8c64d-152">See also</span></span>

<span data-ttu-id="8c64d-153">[Tarih, saat ve saat dilimleri](../../../docs/standard/datetime/index.md)
[nasıl yapılır: tarih ve saat aritmetiği saat dilimini kullanır](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)</span><span class="sxs-lookup"><span data-stu-id="8c64d-153">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)</span></span>