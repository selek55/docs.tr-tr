---
title: "Eşleme kavramsal Model SQL Server'a kurallı işlevleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5c408b64beec87c62b2bb8274fe985187ba7e5e6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Eşleme kavramsal Model SQL Server'a kurallı işlevleri
Bu konuda nasıl kavramsal model kurallı işlevleri açıklanmaktadır karşılık gelen SQL Server işlevleri eşlenir.  
  
## <a name="date-and-time-functions"></a>Tarih ve saat işlevleri  
 Aşağıdaki tabloda eşleme tarih ve saat işlevleri açıklanmaktadır:  
  
|Kurallı işlevleri|SQL Server işlevleri|  
|-------------------------|--------------------------|  
|[AddDays(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (yıl, ay, gün, saat, dakika, saniye)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 ve SQL Server 2005, bir `datetime` biçimlendirilmiş değeri, sunucuda oluşturulur. SQL Server 2008 ve sonraki sürümlerinde, bir `datetime2` değeri, sunucuda oluşturulur.|  
|[CreateDateTimeOffset (yıl, ay, gün, saat, dakika, saniye, tzoffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|A `datetimeoffset` biçimlendirilmiş değeri, sunucuda oluşturulur.<br /><br /> SQL Server 2000 veya SQL Server 2005 desteklenmez.|  
|[CreateTime(hour, minute, second)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|A `time` biçimlendirilmiş değeri, sunucuda oluşturulur.<br /><br /> SQL Server 2000 veya SQL Server 2005 desteklenmez.|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` in SQLServer 2008.<br /><br /> `GetDate()`SQL Server 2000 ve SQL Server 2005'te.|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()`SQL Server 2008.<br /><br /> SQL Server 2000 veya SQL Server 2005 desteklenmez.|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` in SQLServer 2008. `GetUtcDate()`SQL Server 2000 ve SQL Server 2005'te.|  
|[DayOfYear(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (startExpression, endExpression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|SQL Server 2000 ve SQL Server 2005, bir kesilmiş `datetime` biçimlendirilmiş değeri, sunucuda oluşturulur. SQL Server 2008 ve sonraki sürümlerinde, bir kesilmiş `datetime2` veya `datetimeoffset` değeri, sunucuda oluşturulur.|  
|[Year(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Toplama İşlevleri  
 Aşağıdaki tabloda eşleme toplama işlevleri açıklanmaktadır:  
  
|Kurallı işlevleri|SQL Server işlevleri|  
|-------------------------|--------------------------|  
|[Avg(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count (deyim)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[SUM(Expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Matematik işlevleri  
 Aşağıdaki tabloda eşleme matematik işlevleri açıklanmaktadır:  
  
|Kurallı işlevleri|SQL Server işlevleri|  
|-------------------------|--------------------------|  
|[Abs(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(Value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Kesme](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Dize İşlevleri  
 Aşağıdaki tabloda eşleme dize işlevleri açıklanmaktadır:  
  
|Kurallı işlevleri|SQL Server işlevleri|  
|-------------------------|--------------------------|  
|[Contains(String, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat (dize1, dize2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|dize1 + dize2|  
|[EndsWith (dize, hedef)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Not** `CHARINDEX` işlev döndürür `false` varsa `string` sabit uzunluk dize sütununda depolanır ve `target` bir sabit değer. Bu durumda, sonunda boşluk doldurma dahil olmak üzere tüm dizeyi aranır. Dizeye geçirmeden önce sabit uzunlukta bir dize veriler kırpma için olası geçici bir çözüm değildir `EndsWith` , aşağıdaki örnekte olduğu gibi işlev:`EndsWith(TRIM(string), target)`|  
|[IndexOf (hedef, dize2)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Sol (dize1, uzunluk)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Uzunluğu (dize)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Sağa (dize1, uzunluk)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(String)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (dize1, dize2, string3)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Ters (dize)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith (dize, hedef)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (dize, başlangıç, uzunluk)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Bit düzeyinde işlevleri  
 Aşağıdaki tabloda eşleme Bitsel işlevleri açıklanmaktadır:  
  
|Kurallı işlevleri|SQL Server işlevleri|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Değer1 & value2|  
|[BitWiseNot (değer)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~ değeri|  
|[BitWiseOr (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 &#124; value2|  
|[BitWiseXor (value1, value2)](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|Değer1 ^ value2|
