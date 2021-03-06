---
title: "Özel korumalı (C# Başvurusu)"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a>Özel korumalı (C# Başvurusu)
`private protected` Anahtar sözcüğü birleşimi olan bir üye erişim değiştiricisi. Özel bir korumalı üye içeren sınıfından ancak kendi içeren derleme içinde yalnızca türetilmiş türler tarafından erişilebilir. Bir karşılaştırması `private protected` diğer erişim değiştiricileri ile bkz [erişilebilirlik düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md). 
   
## <a name="example"></a>Örnek  
 Yalnızca statik değişkeni türetilmiş sınıf türü türündeyse bir taban sınıf, özel korumalı üyesi içeren derleme türetilmiş türlerde erişilebilir. Örneğin, aşağıdaki kod kesimi göz önünde bulundurun:  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 Bu örnek iki dosya içerir `Assembly1.cs` ve `Assembly2.cs`. İlk dosya ortak bir taban sınıf içeren `BaseClass`ve bu sınıftan türetilen tür `DerivedClass1`. `BaseClass`özel bir korumalı üye sahibi `myValue`, hangi `DerivedClass1` iki yolla erişmeyi dener. İlk erişim girişiminde `myValue` örneği üzerinden `BaseClass` hataya neden olur. Ancak, devralınan bir üyesi olarak kullanmayı denerseniz `DerivedClass1` başarılı olur.
İkinci dosyasında, erişme denemesi `myValue` devralınan bir üyesi olarak `DerivedClass2` yalnızca Assembly1 türetilmiş türlerde tarafından erişilebilir durumda olduğu gibi bir hata oluşturur. 

 Yapı üyeleri olamaz `private protected` yapısı devraldığından.  
  
## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)   
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)   
 [C# anahtar sözcükleri](../../../csharp/language-reference/keywords/index.md)   
 [Erişim değiştiricileri](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Erişilebilirlik düzeyleri](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Değiştiriciler](../../../csharp/language-reference/keywords/modifiers.md)   
 [Ortak](../../../csharp/language-reference/keywords/public.md)   
 [Özel](../../../csharp/language-reference/keywords/private.md)   
 [İç](../../../csharp/language-reference/keywords/internal.md)   
 [İç sanal anahtar ile ilgili güvenlik konuları](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
