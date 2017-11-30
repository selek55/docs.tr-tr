---
title: ".NET Framework Bileşenlerini COM'da Gösterme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9451504b64ddaa8dc0ea6b3a0754257b2c8b3824
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-net-framework-components-to-com"></a><span data-ttu-id="56eea-102">.NET Framework Bileşenlerini COM'da Gösterme</span><span class="sxs-lookup"><span data-stu-id="56eea-102">Exposing .NET Framework Components to COM</span></span>
<span data-ttu-id="56eea-103">.NET türü yazma ve bu tür yönetilmeyen koddan kullanan geliştiriciler için ayrı etkinliklerdir.</span><span class="sxs-lookup"><span data-stu-id="56eea-103">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="56eea-104">Bu bölümde COM istemcileri ile birlikte çalışan yönetilen kod yazma için birkaç ipuçları açıklanmaktadır:</span><span class="sxs-lookup"><span data-stu-id="56eea-104">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>  
  
-   <span data-ttu-id="56eea-105">[Birlikte çalışma için .NET türlerini niteleme](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="56eea-105">[Qualifying .NET types for interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).</span></span>  
  
     <span data-ttu-id="56eea-106">Tüm yönetilen türleri, yöntemler, özellikler, alanları ve COM kullanıma sunmak istediğiniz olayları ortak olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="56eea-106">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="56eea-107">Türleri com içinden çağrılabilen tek Oluşturucusu bir ortak varsayılan oluşturucu olmalıdır</span><span class="sxs-lookup"><span data-stu-id="56eea-107">Types must have a public default constructor, which is the only constructor that can be invoked through COM.</span></span>  
  
-   <span data-ttu-id="56eea-108">[Birlikte çalışma özniteliklerini uygulama](../../../docs/framework/interop/applying-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="56eea-108">[Applying interop attributes](../../../docs/framework/interop/applying-interop-attributes.md).</span></span>  
  
     <span data-ttu-id="56eea-109">Yönetilen kod içinde özel öznitelikleri bir bileşen birlikte çalışabilirliği geliştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56eea-109">Custom attributes within managed code can enhance the interoperability of a component.</span></span>  
  
-   <span data-ttu-id="56eea-110">[COM için derlemeyi paketleme](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="56eea-110">[Packaging an assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).</span></span>  
  
     <span data-ttu-id="56eea-111">COM geliştiricilerin başvuran ve derlemeleriniz dağıtma adımlarını özetleyen gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="56eea-111">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>  
  
 <span data-ttu-id="56eea-112">Ayrıca, bu bölümde bir COM istemciden yönetilen türü tüketen için ilgili görevleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="56eea-112">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>  
  
#### <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="56eea-113">COM yönetilen türünden kullanmak için</span><span class="sxs-lookup"><span data-stu-id="56eea-113">To consume a managed type from COM</span></span>  
  
1.  <span data-ttu-id="56eea-114">[Derlemeleri COM ile kaydetme](../../../docs/framework/interop/registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="56eea-114">[Register assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md).</span></span>  
  
     <span data-ttu-id="56eea-115">Derleme (ve tür kitaplıklarının) türleri tasarım zamanında kayıtlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="56eea-115">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="56eea-116">Bir yükleyici derleme kaydedilmiyorsa COM geliştiriciler Regasm.exe isteyin.</span><span class="sxs-lookup"><span data-stu-id="56eea-116">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>  
  
2.  <span data-ttu-id="56eea-117">[Com'dan .NET türlerine başvurma](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="56eea-117">[Reference .NET types from COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).</span></span>  
  
     <span data-ttu-id="56eea-118">Aynı araçları ve bugün kullandıkları teknikleri kullanarak derlemedeki türleri COM geliştiriciler başvurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="56eea-118">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>  
  
3.  <span data-ttu-id="56eea-119">[Bir .NET nesnesini çağıran](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33).</span><span class="sxs-lookup"><span data-stu-id="56eea-119">[Call a .NET object](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33).</span></span>  
  
     <span data-ttu-id="56eea-120">COM geliştiriciler, bunlar üzerinde herhangi bir yönetilmeyen türü yöntemlerini çağıran aynı şekilde .NET nesnesinde yöntemleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="56eea-120">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="56eea-121">Örneğin, COM **CoCreateInstance** API'si, .NET nesneleri etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="56eea-121">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>  
  
4.  <span data-ttu-id="56eea-122">[COM erişim için bir uygulamayı dağıtmak](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce).</span><span class="sxs-lookup"><span data-stu-id="56eea-122">[Deploy an application for COM access](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce).</span></span>  
  
     <span data-ttu-id="56eea-123">Tanımlayıcı adlı bir derleme genel derleme önbelleğinde yüklenebilir ve yayımcısını imzadan gerektirir.</span><span class="sxs-lookup"><span data-stu-id="56eea-123">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="56eea-124">İstemci uygulama dizininde değil tanımlayıcı adlı derlemeler yüklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="56eea-124">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56eea-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="56eea-125">See Also</span></span>  
 [<span data-ttu-id="56eea-126">Yönetilmeyen kod ile birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="56eea-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)  
 [<span data-ttu-id="56eea-127">COM birlikte çalışma örneği: COM istemcisi ve .NET sunucusu</span><span class="sxs-lookup"><span data-stu-id="56eea-127">COM Interop Sample: COM Client and .NET Server</span></span>](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)