---
title: ".NET Framework Şifreleme Modeli"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- cryptography [.NET Framework], model
- encryption [.NET Framework], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9fb0a726a4bef5b6efa67d5f63c1899468f7e8ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="net-framework-cryptography-model"></a><span data-ttu-id="31ae9-102">.NET Framework Şifreleme Modeli</span><span class="sxs-lookup"><span data-stu-id="31ae9-102">.NET Framework Cryptography Model</span></span>
<span data-ttu-id="31ae9-103">.NET Framework standart birçok şifreleme algoritması uygulamaları sağlar.</span><span class="sxs-lookup"><span data-stu-id="31ae9-103">The .NET Framework provides implementations of many standard cryptographic algorithms.</span></span> <span data-ttu-id="31ae9-104">Bu algoritmalar kullanın ve güvenli olası varsayılan özelliklere sahip kolaydır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-104">These algorithms are easy to use and have the safest possible default properties.</span></span> <span data-ttu-id="31ae9-105">Ayrıca, .NET Framework şifreleme modeli nesne devralma, akış tasarım ve yapılandırma son derece genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-105">In addition, the .NET Framework cryptography model of object inheritance, stream design, and configuration is extremely extensible.</span></span>  
  
## <a name="object-inheritance"></a><span data-ttu-id="31ae9-106">Nesne Devralma</span><span class="sxs-lookup"><span data-stu-id="31ae9-106">Object Inheritance</span></span>  
 <span data-ttu-id="31ae9-107">.NET Framework güvenlik sistemi, Genişletilebilir bir türetilmiş sınıf devralma deseni uygular.</span><span class="sxs-lookup"><span data-stu-id="31ae9-107">The .NET Framework security system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="31ae9-108">Hiyerarşi aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="31ae9-108">The hierarchy is as follows:</span></span>  
  
-   <span data-ttu-id="31ae9-109">Algoritma türü sınıfı, gibi <xref:System.Security.Cryptography.SymmetricAlgorithm>, <xref:System.Security.Cryptography.AsymmetricAlgorithm> veya <xref:System.Security.Cryptography.HashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="31ae9-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm> or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="31ae9-110">Bu düzey soyuttur.</span><span class="sxs-lookup"><span data-stu-id="31ae9-110">This level is abstract.</span></span>  
  
-   <span data-ttu-id="31ae9-111">Bir algoritma türü sınıfından devralan algoritma sınıfı; Örneğin, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2>, veya <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="31ae9-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RC2>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="31ae9-112">Bu düzey soyuttur.</span><span class="sxs-lookup"><span data-stu-id="31ae9-112">This level is abstract.</span></span>  
  
-   <span data-ttu-id="31ae9-113">Bir algoritma sınıfından devralan bir algoritma sınıfı uyarlamasını; Örneğin, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, veya <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="31ae9-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="31ae9-114">Bu düzey tam olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-114">This level is fully implemented.</span></span>  
  
 <span data-ttu-id="31ae9-115">Türetilen sınıfların bu deseni kullanarak yeni bir algoritma veya varolan bir algoritma için yeni bir uygulama eklemek de kolaydır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-115">Using this pattern of derived classes, it is easy to add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="31ae9-116">Örneğin, yeni bir ortak anahtar algoritması oluşturmak için devralınan <xref:System.Security.Cryptography.AsymmetricAlgorithm> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="31ae9-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="31ae9-117">Belirli bir algoritma yeni bir uygulama oluşturmak için bu algoritmasının Özet olmayan türetilmiş bir sınıf oluşturursunuz.</span><span class="sxs-lookup"><span data-stu-id="31ae9-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>  
  
## <a name="how-algorithms-are-implemented-in-the-net-framework"></a><span data-ttu-id="31ae9-118">.NET Framework algoritmaları nasıl uygulanır</span><span class="sxs-lookup"><span data-stu-id="31ae9-118">How Algorithms Are Implemented in the .NET Framework</span></span>  
 <span data-ttu-id="31ae9-119">Farklı uygulamaları için bir algoritma kullanılabilir bir örnek olarak, simetrik algoritmaları göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="31ae9-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="31ae9-120">Tüm simetrik algoritmaları temeli <xref:System.Security.Cryptography.SymmetricAlgorithm>, aşağıdaki algoritmaları tarafından devralınan:</span><span class="sxs-lookup"><span data-stu-id="31ae9-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by the following algorithms:</span></span>  
  
1.  <xref:System.Security.Cryptography.Aes>  
  
2.  <xref:System.Security.Cryptography.DES>  
  
3.  <xref:System.Security.Cryptography.RC2>  
  
4.  <xref:System.Security.Cryptography.Rijndael>  
  
5.  <xref:System.Security.Cryptography.TripleDES>  
  
 <span data-ttu-id="31ae9-121"><xref:System.Security.Cryptography.Aes>iki sınıflar tarafından devralınır: <xref:System.Security.Cryptography.AesCryptoServiceProvider> ve <xref:System.Security.Cryptography.AesManaged>.</span><span class="sxs-lookup"><span data-stu-id="31ae9-121"><xref:System.Security.Cryptography.Aes> is inherited by two classes: <xref:System.Security.Cryptography.AesCryptoServiceProvider> and <xref:System.Security.Cryptography.AesManaged>.</span></span> <span data-ttu-id="31ae9-122"><xref:System.Security.Cryptography.AesCryptoServiceProvider> Sınıftır Aes, Windows şifreleme API (CAPI) uyarlamasını çevresinde bir sarmalayıcı ancak <xref:System.Security.Cryptography.AesManaged> sınıfı, tamamen yönetilen kodda yazılır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-122">The <xref:System.Security.Cryptography.AesCryptoServiceProvider> class is a wrapper around the Windows Cryptography API (CAPI) implementation of Aes, whereas the <xref:System.Security.Cryptography.AesManaged> class is written entirely in managed code.</span></span> <span data-ttu-id="31ae9-123">Uygulamasında, yeni nesil şifreleme (CNG), yönetilen eklemeyi ve CAPI uygulamaları üçüncü türü yok.</span><span class="sxs-lookup"><span data-stu-id="31ae9-123">There is also a third type of implementation, Cryptography Next Generation (CNG), in addition to the managed and CAPI implementations.</span></span> <span data-ttu-id="31ae9-124">CNG algoritması örneğidir <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="31ae9-124">An example of a CNG algorithm is <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="31ae9-125">CNG algoritmaları ve sonrasında Windows Vista'da kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-125">CNG algorithms are available on Windows Vista and later.</span></span>  
  
 <span data-ttu-id="31ae9-126">Hangi sizin için en iyi uygulamadır seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31ae9-126">You can choose which implementation is best for you.</span></span>  <span data-ttu-id="31ae9-127">Yönetilen uygulamalar, .NET Framework desteği tüm platformlarda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-127">The managed implementations are available on all platforms that support the .NET Framework.</span></span>  <span data-ttu-id="31ae9-128">CAPI uygulamaları, eski işletim sistemlerinde kullanılabilir ve artık geliştirilmektedir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-128">The CAPI implementations are available on older operating systems, and are no longer being developed.</span></span> <span data-ttu-id="31ae9-129">CNG yeni geliştirme burada gerçekleşecek en son uygulamasıdır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-129">CNG is the very latest implementation where new development will take place.</span></span> <span data-ttu-id="31ae9-130">Ancak, yönetilen uygulamaları Federal Bilgi işleme standartları (FIPS tarafından) uygunluğu onaylanmamıştır ve sarmalayıcı sınıflar yavaş olabilir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-130">However, the managed implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the wrapper classes.</span></span>  
  
## <a name="stream-design"></a><span data-ttu-id="31ae9-131">Akış tasarım</span><span class="sxs-lookup"><span data-stu-id="31ae9-131">Stream Design</span></span>  
 <span data-ttu-id="31ae9-132">Ortak dil çalışma zamanı simetrik algoritmaları ve karma algoritmaları uygulamak için bir akış Odaklı Tasarım kullanır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-132">The common language runtime uses a stream-oriented design for implementing symmetric algorithms and hash algorithms.</span></span> <span data-ttu-id="31ae9-133">Bu tasarım çekirdeği <xref:System.Security.Cryptography.CryptoStream> türeyen sınıf <xref:System.IO.Stream> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="31ae9-133">The core of this design is the <xref:System.Security.Cryptography.CryptoStream> class, which derives from the <xref:System.IO.Stream> class.</span></span> <span data-ttu-id="31ae9-134">Akış tabanlı şifreleme nesnelerini destekleyen tek bir standart arabirimi (`CryptoStream`) nesne veri aktarımı bölümü işlemek için.</span><span class="sxs-lookup"><span data-stu-id="31ae9-134">Stream-based cryptographic objects support a single standard interface (`CryptoStream`) for handling the data transfer portion of the object.</span></span> <span data-ttu-id="31ae9-135">Tüm nesneler üzerinde standart bir arabirim oluşturulur çünkü birden çok nesne (örneğin, bir şifreleme nesnesi tarafından izlenen bir karma nesnesi) zincir ve herhangi bir ara depolama alanı için gerek kalmadan veriler üzerinde birden çok işlemler gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="31ae9-135">Because all the objects are built on a standard interface, you can chain together multiple objects (such as a hash object followed by an encryption object), and you can perform multiple operations on the data without needing any intermediate storage for it.</span></span> <span data-ttu-id="31ae9-136">Akış modeli daha küçük nesnelerine nesnelerden oluşturmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="31ae9-136">The streaming model also enables you to build objects from smaller objects.</span></span> <span data-ttu-id="31ae9-137">Örneğin, bu nesne akışı nesneleri kümesinden yerleştirilmiş olabilir ancak birleşik bir şifreleme ve karma algoritma tek stream nesnesi olarak görüntülenebilir.</span><span class="sxs-lookup"><span data-stu-id="31ae9-137">For example, a combined encryption and hash algorithm can be viewed as a single stream object, although this object might be built from a set of stream objects.</span></span>  
  
## <a name="cryptographic-configuration"></a><span data-ttu-id="31ae9-138">Şifreleme yapılandırması</span><span class="sxs-lookup"><span data-stu-id="31ae9-138">Cryptographic Configuration</span></span>  
 <span data-ttu-id="31ae9-139">Şifreleme yapılandırması, .NET Framework şifreleme sınıflarını genişletilebilirlik sağlayan bir algoritma adı için bir algoritma, belirli bir uygulamasına çözümlemenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-139">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET Framework cryptography classes.</span></span> <span data-ttu-id="31ae9-140">Bir algoritma kendi donanım veya yazılım uygulaması eklemek ve uygulama tercih ettiğiniz algoritma adı eşleyin.</span><span class="sxs-lookup"><span data-stu-id="31ae9-140">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="31ae9-141">Bir algoritma yapılandırma dosyasında belirtilmezse, varsayılan ayarlar kullanılır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-141">If an algorithm is not specified in the configuration file, the default settings are used.</span></span> <span data-ttu-id="31ae9-142">Şifreleme yapılandırması hakkında daha fazla bilgi için bkz: [şifreleme sınıflarını yapılandırma](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span><span class="sxs-lookup"><span data-stu-id="31ae9-142">For more information about cryptographic configuration, see [Configuring Cryptography Classes](../../../docs/framework/configure-apps/configure-cryptography-classes.md).</span></span>  
  
## <a name="choosing-an-algorithm"></a><span data-ttu-id="31ae9-143">Bir algoritma seçme</span><span class="sxs-lookup"><span data-stu-id="31ae9-143">Choosing an Algorithm</span></span>  
 <span data-ttu-id="31ae9-144">Çeşitli nedenlerle bir algoritma seçebilirsiniz: Örneğin, veri bütünlüğü, veri gizliliği için ya da bir anahtar oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="31ae9-144">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="31ae9-145">Simetrik ve karma algoritmaları bütünlüğü nedenleri (değişikliği koruma) veya (görüntülemesini koruma) gizlilik nedeniyle verileri korumak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-145">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="31ae9-146">Karma algoritmaları öncelikle veri bütünlüğü için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="31ae9-146">Hash algorithms are used primarily for data integrity.</span></span>  
  
 <span data-ttu-id="31ae9-147">Uygulama tarafından önerilen algoritmaları listesi aşağıdadır:</span><span class="sxs-lookup"><span data-stu-id="31ae9-147">Here is a list of recommended algorithms by application:</span></span>  
  
-   <span data-ttu-id="31ae9-148">Veri gizliliği:</span><span class="sxs-lookup"><span data-stu-id="31ae9-148">Data privacy:</span></span>  
  
    -   <xref:System.Security.Cryptography.Aes>  
  
-   <span data-ttu-id="31ae9-149">Veri bütünlüğü:</span><span class="sxs-lookup"><span data-stu-id="31ae9-149">Data integrity:</span></span>  
  
    -   <xref:System.Security.Cryptography.HMACSHA256>  
  
    -   <xref:System.Security.Cryptography.HMACSHA512>  
  
-   <span data-ttu-id="31ae9-150">Dijital imza:</span><span class="sxs-lookup"><span data-stu-id="31ae9-150">Digital signature:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDsa>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="31ae9-151">Anahtar Değişimi:</span><span class="sxs-lookup"><span data-stu-id="31ae9-151">Key exchange:</span></span>  
  
    -   <xref:System.Security.Cryptography.ECDiffieHellman>  
  
    -   <xref:System.Security.Cryptography.RSA>  
  
-   <span data-ttu-id="31ae9-152">Rastgele sayı oluşturma:</span><span class="sxs-lookup"><span data-stu-id="31ae9-152">Random number generation:</span></span>  
  
    -   <xref:System.Security.Cryptography.RNGCryptoServiceProvider>  
  
-   <span data-ttu-id="31ae9-153">Bir anahtar parola durumundan oluşturuluyor:</span><span class="sxs-lookup"><span data-stu-id="31ae9-153">Generating a key from a password:</span></span>  
  
    -   <xref:System.Security.Cryptography.Rfc2898DeriveBytes>  
  
## <a name="see-also"></a><span data-ttu-id="31ae9-154">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="31ae9-154">See Also</span></span>  
 [<span data-ttu-id="31ae9-155">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="31ae9-155">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 