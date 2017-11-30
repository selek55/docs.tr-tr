---
title: "extern (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 106ceb6a4acf57daa01919acb38e4245655fca2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="extern-c-reference"></a><span data-ttu-id="35f08-102">extern (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="35f08-102">extern (C# Reference)</span></span>
<span data-ttu-id="35f08-103">`extern` Değiştiricisi harici olarak uygulanan bir yöntem bildirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="35f08-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="35f08-104">Yaygın kullanımı `extern` değiştiricisi durumdayken `DllImport` yönetilmeyen koda çağırmak için birlikte çalışma hizmetleri kullanırken özniteliği.</span><span class="sxs-lookup"><span data-stu-id="35f08-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="35f08-105">Bu durumda, yöntem de olarak bildirilmelidir `static`, aşağıdaki örnekte gösterildiği gibi:</span><span class="sxs-lookup"><span data-stu-id="35f08-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="35f08-106">`extern` Anahtar sözcüğü de tek bir derleme içinde aynı bileşenin farklı sürümlerini başvuru mümkün kılan bir dış derleme diğer ad tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="35f08-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="35f08-107">Daha fazla bilgi için bkz: [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="35f08-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="35f08-108">Kullanmak için bir hata olduğunu [soyut](../../../csharp/language-reference/keywords/abstract.md) ve `extern` değiştiricileri birlikte aynı üye değiştirin.</span><span class="sxs-lookup"><span data-stu-id="35f08-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="35f08-109">Kullanarak `extern` değiştiricisi anlamına gelir C# kodu dışında uygulanan yöntemi kullanarak ancak `abstract` değiştiricisi anlamına gelir yöntem uygulaması sınıfında sağlanmadı.</span><span class="sxs-lookup"><span data-stu-id="35f08-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="35f08-110">extern anahtar sözcüğünün kullanımları, C++'a göre C#'de daha fazladır.</span><span class="sxs-lookup"><span data-stu-id="35f08-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="35f08-111">C# anahtar sözcüğünü C++ anahtar sözcüğüyle karşılaştırmak için, C++ Dilinde Bağlantı Belirtmek için extern Kullanma Başvurusu'na bakın.</span><span class="sxs-lookup"><span data-stu-id="35f08-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35f08-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="35f08-112">Example</span></span>  
 <span data-ttu-id="35f08-113">**Örnek 1.**</span><span class="sxs-lookup"><span data-stu-id="35f08-113">**Example 1.**</span></span> <span data-ttu-id="35f08-114">Bu örnekte, kullanıcıdan bir dize alır ve program içinde bir ileti kutusu görüntüler.</span><span class="sxs-lookup"><span data-stu-id="35f08-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="35f08-115">Program kullanan `MessageBox` yöntemi User32.dll kitaplığından içeri aktarıldı.</span><span class="sxs-lookup"><span data-stu-id="35f08-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="35f08-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="35f08-116">Example</span></span>  
 <span data-ttu-id="35f08-117">**Örnek 2.**</span><span class="sxs-lookup"><span data-stu-id="35f08-117">**Example 2.**</span></span> <span data-ttu-id="35f08-118">Bu örnekte, bir C Kitaplığı'na (yerel DLL) çağıran bir C# programı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="35f08-118">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="35f08-119">Aşağıdaki C dosyası oluşturun ve adlandırın `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="35f08-119">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="35f08-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="35f08-120">Example</span></span>  
 2. <span data-ttu-id="35f08-121">Visual Studio yükleme dizininden bir Visual Studio x64 (veya x32) yerel Araçları Komut İstemi penceresi açın ve derleme `cmdll.c` yazarak dosya **cl /LD cmdll.c** komut isteminde.</span><span class="sxs-lookup"><span data-stu-id="35f08-121">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="35f08-122">Aynı dizinde aşağıdaki C# dosyası oluşturun ve adlandırın `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="35f08-122">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="35f08-123">Örnek</span><span class="sxs-lookup"><span data-stu-id="35f08-123">Example</span></span>  
 3. <span data-ttu-id="35f08-124">Visual Studio yükleme dizininden bir Visual Studio x64 (veya x32) yerel Araçları Komut İstemi penceresi açın ve derleme `cm.cs` yazarak dosyası:</span><span class="sxs-lookup"><span data-stu-id="35f08-124">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="35f08-125">**CSC cm.cs** (x64 için komut istemi)</span><span class="sxs-lookup"><span data-stu-id="35f08-125">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="35f08-126">—veya—</span><span class="sxs-lookup"><span data-stu-id="35f08-126">—or—</span></span>  
> <span data-ttu-id="35f08-127">**CSC /platform:x 86 cm.cs** (x32 için komut istemi)</span><span class="sxs-lookup"><span data-stu-id="35f08-127">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="35f08-128">Bu yürütülebilir dosya oluşturacak `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="35f08-128">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="35f08-129">Çalıştırma `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="35f08-129">Run `cm.exe`.</span></span> <span data-ttu-id="35f08-130">`SampleMethod` Yöntemi tarafından 10 çarpılan değeri döndürür DLL dosyasının 5 değerini iletir.</span><span class="sxs-lookup"><span data-stu-id="35f08-130">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="35f08-131">Program şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="35f08-131">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="35f08-132">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="35f08-132">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35f08-133">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35f08-133">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>  
 [<span data-ttu-id="35f08-134">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="35f08-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="35f08-135">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="35f08-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="35f08-136">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="35f08-136">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="35f08-137">Değiştiriciler</span><span class="sxs-lookup"><span data-stu-id="35f08-137">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)