---
title: "x:ClassModifier Yönergesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a>x:ClassModifier Yönergesi
XAML derleme davranışını değiştiren zaman `x:Class` de sağlanır. Özellikle, kısmi oluşturmak yerine `class` olan bir `Public` erişim düzeyine (varsayılan), sağlanan `x:Class` ile oluşturulan bir `NotPublic` erişim düzeyi. Bu davranış oluşturulmuş derlemeler sınıfında erişim düzeyini etkiler.  
  
## <a name="xaml-attribute-usage"></a>XAML Öznitelik Kullanımı  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a>XAML Değerleri  
  
|||  
|-|-|  
|*NotPublic*|Belirtmek için geçirmek için tam dizeyi <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> karşı <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , kullandığınız arka plan kodu programlama dili bağlı olarak değişir. Açıklamalar bakın.|  
  
## <a name="dependencies"></a>Bağımlılıklar  
 [x: Class](../../../docs/framework/xaml-services/x-class-directive.md) de aynı öğede sağlanması gerekir ve bu öğe bir sayfa kök öğe olmalıdır. Daha fazla bilgi için bkz: [ \[MS XAML\] bölüm 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
## <a name="remarks"></a>Açıklamalar  
 Değeri `x:ClassModifier` programlama dili tarafından kullanım .NET Framework XAML hizmetlerinde değişir. Her bir dilin nasıl uyguladığını kullanılacak dizesi bağlıdır, <xref:System.CodeDom.Compiler.CodeDomProvider> ve döndürür anlamı tanımlamak için tür dönüştürücüleri <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ve <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, ve bu dil büyük küçük harfe duyarlı olup olmadığını.  
  
-   İçin [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], atamak iletilecek dizeyi <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> olan `internal`.  
  
-   İçin [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], atamak iletilecek dizeyi <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> olan `Friend`.  
  
-   İçin [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], XAML derleme destekleyen hiçbir hedef var; Bu nedenle, geçirmek için değer belirtilmemiş.  
  
 Ayrıca belirtebilirsiniz <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` içinde [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` içinde [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); ancak, belirtme <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> seyrek yapılır, çünkü <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> zaten varsayılan davranıştır.  
  
 Eşdeğer kullanıcı kodu diğer değerlerle erişim düzeyi kısıtlamaları gibi `private` içinde [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], ilgili olmayan `x:ClassModifier` iç içe geçmiş sınıf başvurularını XAML'de desteklenmediğinden ve bu nedenle, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> değiştiricisi sahip aynı etkisi.  
  
## <a name="security-notes"></a>Güvenlik notları  
 Bildirilen gibi erişim düzeyini `x:ClassModifier` belirli çerçeveler ve yeteneklerini tarafından tercüme hala tabidir. WPF yüklemek ve türleri örneği için özellikleri içerir nerede `x:ClassModifier` olan `internal`, o sınıfın bir paketi URI başvuru aracılığıyla bir WPF kaynaktan başvuruluyor. Bu durumda ve diğerleri gibi bu diğer çerçeveler tarafından uygulanan gruplarındaki sonucu olarak, özel olarak üzerinde güvenmeyin `x:ClassModifier` olası tüm örneklemesi engelleyecek şekilde çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [x:Class Yönergesi](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Arka Plan Kod ve WPF İçindeki XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [x:FieldModifier Yönergesi](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [Güvenlik (WPF)](../../../docs/framework/wpf/security-wpf.md)  
 [WPF'den System.Xaml'e Geçirilen Türler](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
