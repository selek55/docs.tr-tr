---
title: "Genel Sınıflar (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c92efd63f7b24917dc50ca0864f1a132c5c2bf00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="generic-classes-c-programming-guide"></a>Genel Sınıflar (C# Programlama Kılavuzu)
Genel sınıflar belirli veri türüne özgü olmayan işlemler kapsüller. Bağlantılı listeleri, karma tabloları, yığınları, kuyruklar, ağaçlar ve benzeri gibi koleksiyonlarıyla genel sınıfları için en yaygın kullanımı içindir. Öğeler ekleme ve koleksiyondan kaldırma gibi işlemleri temelde aynı şekilde depolanmasını veri türü bağımsız olarak gerçekleştirilir.  
  
 Koleksiyon sınıfları gerektiren çoğu senaryolar için .NET Framework Sınıf Kitaplığı'nda sağlanan olanları kullanmak önerilen yaklaşımdır. Bu sınıfları kullanma hakkında daha fazla bilgi için bkz: [.NET Framework Sınıf Kitaplığı'nda genel türler](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).  
  
 Genellikle, varolan bir somut sınıfı ile başlatarak ve en iyi dengeyi Genelleştirme ve kullanılabilirlik ulaşana kadar aynı anda bir tür parametreleri türlerini değiştirme genel sınıflar oluşturun. Genel sınıflarınızı oluştururken, önemli noktalar şunlardır:  
  
-   Tür parametreleri genelleştirmek için hangi tür.  
  
     Bir kural, Parametreleştirme daha fazla türleri, daha esnek ve yeniden kullanılabilir kodunuzu haline gelir. Ancak, çok fazla Genelleştirme okumak veya anlamak diğer geliştiriciler için zordur kod oluşturabilirsiniz.  
  
-   Tür parametreleri uygulamak için varsa hangi kısıtlamaları (bkz [tür parametrelerindeki kısıtlamalar](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).  
  
     Hala işlemesi gerekir türleri işlemenize olanak sağlayacak maksimum kısıtlamaları olası uygulamak iyi bir kuraldır. Başvuru türleri yalnızca kullanmaya genel sınıfınız yönelik biliyorsanız, örneğin, sınıf kısıtlaması uygulayın. Değer türleri ile sınıfınız istenmeyen kullanımını engeller ve kullanmanıza olanak tanır `as` işlecinin `T`ve null değerler denetleyin.  
  
-   Temel sınıflar ve alt sınıfların genel davranış faktörü görüntülenmeyeceğini belirtir.  
  
     Genel sınıflar temel sınıf olarak kullanılabileceği için aynı tasarım konuları burada geçerli olarak genel olmayan sınıflarla. Bu konunun ilerleyen bölümlerinde genel temel sınıflardan devralan hakkında kurallar konusuna bakın.  
  
-   Bir veya daha fazla genel arabirimlerini görüntülenmeyeceğini belirtir.  
  
     Örneğin, bir genel türler tabanlı koleksiyon öğeleri oluşturmak için kullanılan bir sınıfı tanımlıyorsanız, bir arabirim gibi uygulama gerekebilir <xref:System.IComparable%601> burada `T` sınıfınız türüdür.  
  
 Basit genel bir sınıf örneği için bkz: [genel türlere giriş](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 Tür parametreleri ve kısıtlamalar için kuralları, özellikle devralma ve üye erişilebilirlik ile ilgili genel bir sınıf davranışı için birkaç etkiler. Devam etmeden önce bazı koşulları anlamanız gerekir. Genel bir sınıf için `Node<T>,` istemci kodu sınıfı başvuru ya da kapalı oluşturulan türü oluşturmak için bir tür bağımsız değişkeni belirterek (`Node<int>`). Alternatif olarak, genel bir taban sınıfı belirtin, örneğin belirtilmeyen tür parametresi bırakabilirsiniz, açık bir oluşturmak için türü oluşturulan (`Node<T>`). Genel sınıflar somut, kapalı oluşturulan veya açık oluşturulan temel sınıflardan devrettiği:  
  
 [!code-csharp[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]  
  
 Genel olmayan başka bir deyişle, somut, sınıflar devral kapalı oluşturulan temel sınıfları, ancak olmayan sınıflardan açık oluşturulan veya tür parametreleri örneği oluşturmak için gerekli tür bağımsız değişkeni sağlamak istemci kodu için çalışma zamanında hiçbir şekilde olduğundan temel sınıf.  
  
 [!code-csharp[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]  
  
 Açık oluşturulan türler devralınan genel sınıflar, aşağıdaki kodda gösterildiği gibi türetilen sınıf tarafından paylaşılmayan herhangi bir temel sınıf türü parametre için tür bağımsız değişkenleri sağlamanız gerekir:  
  
 [!code-csharp[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]  
  
 Açık oluşturulan türler devralınan genel sınıflar bir alt kümesi olan kısıtlamaları belirtir veya gelmez, temel türü kısıtlamalar:  
  
 [!code-csharp[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]  
  
 Genel türler birden çok tür parametreleri ve kısıtlamaları, aşağıdaki gibi kullanabilirsiniz:  
  
 [!code-csharp[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]  
  
 Açık oluşturulan ve kapalı oluşturulan türler yöntem parametreleri olarak kullanılabilir:  
  
 [!code-csharp[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]  
  
 Genel bir sınıf bir arabirim uygularsa, bu sınıfın tüm örnekleri için bu arabirimi çevirebilirsiniz.  
  
 Genel sınıflar değişmez. Diğer bir deyişle, bir giriş parametresi belirtiyorsa bir `List<BaseClass>`, sağlamak çalışırsa, bir derleme zamanı hatası alırsınız bir `List<DerivedClass>`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Collections.Generic>  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Genel türler](../../../csharp/programming-guide/generics/index.md)  
 [Numaralandırmalar durumunu kaydetme](http://go.microsoft.com/fwlink/?LinkId=112390)  
 [Bir devralma Bulmacanın bölüm bir](http://go.microsoft.com/fwlink/?LinkId=112380)
