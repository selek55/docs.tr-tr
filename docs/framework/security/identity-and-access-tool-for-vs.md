---
title: "Kimlik ve erişim aracı Visual Studio 2012 için"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a009f37e1f16646df10e693a10827990b073c65c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a><span data-ttu-id="a76b2-102">Kimlik ve erişim aracı Visual Studio 2012 için</span><span class="sxs-lookup"><span data-stu-id="a76b2-102">Identity and Access Tool for Visual Studio 2012</span></span>
<span data-ttu-id="a76b2-103">Bu konuda, Visual Studio 11 için yeni Kimlik ve Erişim Aracı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a76b2-103">This topic describes the new Identity and Access Tool for Visual Studio 11.</span></span> <span data-ttu-id="a76b2-104">Bu araç aşağıdaki URL'yi indirebilirsiniz: [http://go.microsoft.com/fwlink/?LinkID=245849](http://go.microsoft.com/fwlink/?LinkID=245849) veya doğrudan doğrudan uzantıları Yöneticisi'nde "kimlik" için arama tarafından Visual Studio 11 içinde.</span><span class="sxs-lookup"><span data-stu-id="a76b2-104">You can download this tool from the following URL: [http://go.microsoft.com/fwlink/?LinkID=245849](http://go.microsoft.com/fwlink/?LinkID=245849) or directly from within Visual Studio 11 by searching for "identity" directly in the Extensions Manager.</span></span>  
  
 <span data-ttu-id="a76b2-105">Visual Studio 11 için Kimlik ve Erişim Aracı, aşağıdaki önemli özelliklerle birlikte önemli ölçüde basitleştirilmiş bir geliştirme zamanı deneyimi sağlar:</span><span class="sxs-lookup"><span data-stu-id="a76b2-105">The Identity and Access Tool for Visual Studio 11 delivers a dramatically simplified development-time experience with the following highlights:</span></span>  
  
-   <span data-ttu-id="a76b2-106">Bu yeni araç ile, web uygulamaları proje türlerini kullanarak geliştirme yapabilir ve IIS express'i hedefleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a76b2-106">Using the new tool, you can develop using web applications project types and target IIS express.</span></span>  
  
-   <span data-ttu-id="a76b2-107">Yalnızca koruma paket kimlik doğrulamasının aksine, yeni araçla yerel ana bölge keşif sayfanızı/denetleyicinizi (uygulamanızda kimlik doğrulama deneyimini gerçekleştiren başka bir uç noktası) belirtebilirsiniz; WIF kimliği doğrulanmamış tüm istekleri STS'ye yönlendirmek yerine buraya gidecek şekilde yapılandıracaktır.</span><span class="sxs-lookup"><span data-stu-id="a76b2-107">Unlike with the blanket protection-only authentication, with the new tool, you can specify your local home realm discovery page/controller (or any other endpoint handling the authentication experience within your application) and WIF will configure all unauthenticated requests to go there, instead of redirecting them to the STS.</span></span>  
  
-   <span data-ttu-id="a76b2-108">Araç, hata ayıklama oturumu başlattığınızda yerel makinenizde çalışan bir test Güvenlik Belirteci Hizmeti (STS) içerir.</span><span class="sxs-lookup"><span data-stu-id="a76b2-108">The tool includes a test Security Token Service (STS) which runs on your local machine when you launch a debug session.</span></span> <span data-ttu-id="a76b2-109">Bu nedenle, uygulamalarınızı test etmek için ihtiyacınız olan talepleri almak üzere artık özel STS projeleri oluşturmanıza ve bunlara ince ayar yapmanıza gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="a76b2-109">Therefore, you no longer need to create custom STS projects and tweak them in order to get the claims you need to test your applications.</span></span> <span data-ttu-id="a76b2-110">Talep türleri ve değerler tamamen özelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="a76b2-110">The claim types and values are fully customizable.</span></span>  
  
-   <span data-ttu-id="a76b2-111">Ortak ayarları, web.config'i düzenlemek zorunda kalmadan doğrudan aracın kullanıcı arabirimiyle değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a76b2-111">You can modify common settings directly via the tool’s UI, without the need to edit web.config.</span></span>  
  
-   <span data-ttu-id="a76b2-112">Tek bir ekranda Active Directory Federasyon Hizmetleri (AD FS) 2.0 (veya diğer WS-Federasyon sağlayıcıları) ile federasyon oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a76b2-112">You can establish federation with Active Directory Federation Services (AD FS) 2.0 (or other WS-Federation providers) in a single screen.</span></span>  
  
-   <span data-ttu-id="a76b2-113">Araç, kullanmak istediğiniz tüm kimlik sağlayıcıları için basit bir onay kutusu listesiyle Microsoft Azure Erişim Denetimi Hizmeti (ACS) özelliklerini kullanır: Facebook, Google, Live ID, Yahoo!, tüm OpenID sağlayıcılar ve tüm WS-Federasyon sağlayıcıları.</span><span class="sxs-lookup"><span data-stu-id="a76b2-113">The tool leverages Windows Azure Access Control Service (ACS) capabilities with a simple list of checkboxes for all the identity providers that you want to use: Facebook, Google, Live ID, Yahoo!, any OpenID provider, and any WS-Federation provider.</span></span> <span data-ttu-id="a76b2-114">Kimlik sağlayıcılarınızı seçin, Tamam'a tıklayın ve F5'e basın; hem uygulamanız hem de ACS otomatik olarak yapılandırılacak ve test uygulamanız ACS'yi kullanacaktır.</span><span class="sxs-lookup"><span data-stu-id="a76b2-114">Select your identity providers, click OK, then F5, and both your application and ACS will be automatically configured and your test application will be ACS-aware.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76b2-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a76b2-115">See Also</span></span>  
 [<span data-ttu-id="a76b2-116">WIF özellikleri</span><span class="sxs-lookup"><span data-stu-id="a76b2-116">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)