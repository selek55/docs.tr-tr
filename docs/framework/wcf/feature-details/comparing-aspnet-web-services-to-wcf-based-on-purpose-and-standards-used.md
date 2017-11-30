---
title: "ASP.NET Web Hizmetlerini Amaç ve Kullanılan Standartları Temel Alarak WCF ile Karşılaştırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6dc444b8a4c19dbe486eb904e0f054e05f6fe6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a><span data-ttu-id="89885-102">ASP.NET Web Hizmetlerini Amaç ve Kullanılan Standartları Temel Alarak WCF ile Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="89885-102">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>
<span data-ttu-id="89885-103">ASP.NET Web Hizmetleri, HTTP üzerinden Basit Nesne Erişim Protokolü (SOAP) kullanarak iletileri almasına ve göndermesine uygulamaları oluşturmak için geliştirildi.</span><span class="sxs-lookup"><span data-stu-id="89885-103">ASP.NET Web services was developed for building applications that send and receive messages by using the Simple Object Access Protocol (SOAP) over HTTP.</span></span> <span data-ttu-id="89885-104">İletileri yapısını bir XML Şeması kullanılarak tanımlanabilir ve bir aracı iletilerini ve .NET Framework nesneleri seri hale getirme kolaylaştırmak için sağlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="89885-104">The structure of the messages can be defined using an XML Schema, and a tool is provided to facilitate serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="89885-105">Teknoloji Web Hizmetleri Web Hizmetleri Açıklama Dili (WSDL) tanımlamak için meta verileri otomatik olarak oluşturabilir ve Web Hizmetleri için istemcileri WSDL oluşturmak için ikinci bir aracı sağlanır.</span><span class="sxs-lookup"><span data-stu-id="89885-105">The technology can automatically generate metadata to describe Web services in the Web Services Description Language (WSDL), and a second tool is provided for generating clients for Web services from the WSDL.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89885-106">diğer yazılım varlıklarla ileti alışverişinde bulunmak .NET Framework uygulamaları için etkinleştirmektir.</span><span class="sxs-lookup"><span data-stu-id="89885-106"> is for enabling .NET Framework applications to exchange messages with other software entities.</span></span> <span data-ttu-id="89885-107">SOAP varsayılan olarak kullanılır, ancak iletiler herhangi bir biçimde olabilir ve herhangi bir aktarım protokolünü kullanarak ilettiği.</span><span class="sxs-lookup"><span data-stu-id="89885-107">SOAP is used by default, but the messages can be in any format, and conveyed by using any transport protocol.</span></span> <span data-ttu-id="89885-108">İletileri yapısını bir XML Şeması kullanılarak tanımlanabilir ve iletilerini ve .NET Framework nesneleri serileştirmek için çeşitli seçenekleriniz vardır.</span><span class="sxs-lookup"><span data-stu-id="89885-108">The structure of the messages can be defined using an XML Schema, and there are various options for serializing the messages to and from .NET Framework objects.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="89885-109">WSDL içinde teknolojisi kullanılarak oluşturulan uygulamaların açıklamak için meta verileri otomatik olarak oluşturabilir ve WSDL istemcileri için bu uygulamaları oluşturmak için de bir araç sağlar.</span><span class="sxs-lookup"><span data-stu-id="89885-109"> can automatically generate metadata to describe applications built using the technology in WSDL, and it also provides a tool for generating clients for those applications from the WSDL.</span></span>  
  
 <span data-ttu-id="89885-110">ASP.NET Web Hizmetleri tarafından desteklenen standartları belgelenmiştir [XML Web Hizmetleri oluşturulan kullanarak ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span><span class="sxs-lookup"><span data-stu-id="89885-110">The standards supported by ASP.NET Web services are documented in [XML Web Services Created Using ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span></span> <span data-ttu-id="89885-111">Tarafından desteklenen standartları daha kapsamlı listesini [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] adresinde listelenmiş [Web Hizmetleri protokolleri desteklenen System-Provided birlikte kullanılabilirlik bağlamaları ile](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="89885-111">The more extensive list of standards supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are listed at [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89885-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="89885-112">See Also</span></span>  
 [<span data-ttu-id="89885-113">ASP.NET Web hizmetlerini geliştirmeye göre WCF karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="89885-113">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)