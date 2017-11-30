---
title: "WCF ve Uluslararası Hale Getirilmiş Etki Alanı Adları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab9346e7826fcef5151ef976b6ca7f25120fa5a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="428d2-102">WCF ve Uluslararası Hale Getirilmiş Etki Alanı Adları</span><span class="sxs-lookup"><span data-stu-id="428d2-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="428d2-103">WCF hizmetleri Uluslararası yapılan etki alanı adları (IDN) ile izin vermek için destek eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="428d2-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="428d2-104">Uluslararası etki alanı ASCII olmayan karakterler içeren bir etki alanı adıdır.</span><span class="sxs-lookup"><span data-stu-id="428d2-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="428d2-105">Bu destek bir IDN adı ve bir web hizmetini bir IDN adı ile iletişim kuran bir WCF istemcisi ile WCF Hizmeti barındırma her iki özelliği içerir.</span><span class="sxs-lookup"><span data-stu-id="428d2-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="428d2-106">System.Uri ve IDN</span><span class="sxs-lookup"><span data-stu-id="428d2-106">System.Uri and IDN</span></span>  
 <span data-ttu-id="428d2-107"><xref:System.Uri>iki özelliğe sahip <xref:System.Uri.Host%2A> ve <xref:System.Uri.DnsSafeHost%2A>.</span><span class="sxs-lookup"><span data-stu-id="428d2-107"><xref:System.Uri> has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="428d2-108">Bu özellikleri IDN yapılandırma ayarlarına bağlı olarak Unicode ya da Punycode değerlerini içerir.</span><span class="sxs-lookup"><span data-stu-id="428d2-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="428d2-109">Bir uygulamanın yapılandırma dosyasında aşağıdaki XML kullanarak IDN etkin</span><span class="sxs-lookup"><span data-stu-id="428d2-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="428d2-110">\<IDN > öğesi içeriyor etkin özniteliği aşağıdaki değerlerden birine ayarlayın:</span><span class="sxs-lookup"><span data-stu-id="428d2-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1.  <span data-ttu-id="428d2-111">"Hiçbiri"</span><span class="sxs-lookup"><span data-stu-id="428d2-111">"None"</span></span>  
  
2.  <span data-ttu-id="428d2-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="428d2-112">"AllExceptIntranet"</span></span>  
  
3.  <span data-ttu-id="428d2-113">"Tümü"</span><span class="sxs-lookup"><span data-stu-id="428d2-113">"All"</span></span>  
  
 <span data-ttu-id="428d2-114">IDN ayarını "Yok" olarak ayarlandığında, hiçbir dönüşümleri Uri.Host veya Uri.DnsSafeHost tarafından gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="428d2-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="428d2-115">Ne zaman IDN ayarı "Tümü", URI ayarlanır. Ana bilgisayar Unicode ve URI kalır. DnsSafeHost kodlar, zayıf koda dönüştürülür.</span><span class="sxs-lookup"><span data-stu-id="428d2-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="428d2-116">Ne zaman IDN ayarı "AllExceptIntranet için", URI ayarlanır. DnsSafeHost internet adresleri için kodlar, zayıf koda dönüştürülür ve intranet adresleri için Unicode kalır.</span><span class="sxs-lookup"><span data-stu-id="428d2-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="428d2-117">Bu ayar, doğru DNS ad çözümlemesi için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="428d2-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="428d2-118">Bu ayar Windows 8 ve daha yeni sürümleri için yapılandırılması için gerekli olmayan unutmayın.</span><span class="sxs-lookup"><span data-stu-id="428d2-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="428d2-119">Hiçbir sabit kodlu gereken zayıf kod kullanarak bir adres.</span><span class="sxs-lookup"><span data-stu-id="428d2-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="428d2-120">WCF, uyguladığınız yapılandırma ayarlarınızı temel alan grafiği dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="428d2-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="428d2-121">Unicode karakterler için applicationHost.exe.config eklerken, UTF-8 kodlaması kullanarak dosyayı kaydedin.</span><span class="sxs-lookup"><span data-stu-id="428d2-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428d2-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="428d2-122">See Also</span></span>  
 [<span data-ttu-id="428d2-123">System.Uri</span><span class="sxs-lookup"><span data-stu-id="428d2-123">System.Uri</span></span>](http://msdn.microsoft.com/library/system.uri.aspx)