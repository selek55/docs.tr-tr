---
title: "WCF Dağıtımı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 51cf7c6e4db1ee0ff68bcc7fccb46fd643f04bf4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="96c67-102">WCF Dağıtımı</span><span class="sxs-lookup"><span data-stu-id="96c67-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="96c67-103">Okuma ve bunları oluşturmak yanı sıra bir hizmet uç noktasında kullanıma olanak tanıyan Atom, RSS veya diğer özel biçimler dağıtım akışlarını kolayca çalışmak için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="96c67-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="96c67-104">Bu bölümdeki konularda ayrıntılı dağıtım için bu programlama modeli açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="96c67-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96c67-105">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="96c67-105">In This Section</span></span>  
 [<span data-ttu-id="96c67-106">WCF dağıtımı genel bakış</span><span class="sxs-lookup"><span data-stu-id="96c67-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="96c67-107">Tarafından sağlanan dağıtım desteği'ne genel bakış sağlar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c67-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="96c67-108">Dağıtım mimarisi</span><span class="sxs-lookup"><span data-stu-id="96c67-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="96c67-109">Nesne modeli ve dağıtım genişletilebilirliği sınıflarda açıklar.</span><span class="sxs-lookup"><span data-stu-id="96c67-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="96c67-110">WCF dağıtım nesnesi modeli Atom ve RSS nasıl eşlendiğini</span><span class="sxs-lookup"><span data-stu-id="96c67-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="96c67-111">Akışları WCF dağıtım nesnesi modeli içinde nasıl temsil edildiğini ve nasıl RSS'ye dönüştürülür ve Atom akışları açıklar.</span><span class="sxs-lookup"><span data-stu-id="96c67-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="96c67-112">Nasıl yapılır: temel bir RSS akışı oluşturma</span><span class="sxs-lookup"><span data-stu-id="96c67-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="96c67-113">Temel bir RSS akışı kullanılabilmesini bir hizmetin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="96c67-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="96c67-114">Nasıl yapılır: temel bir Atom akışı oluşturma</span><span class="sxs-lookup"><span data-stu-id="96c67-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="96c67-115">Akış temel bir ATOM kullanılabilmesini bir hizmetin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="96c67-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="96c67-116">Nasıl yapılır: bir akışı hem Atom olarak kullanıma sunmak ve RSS</span><span class="sxs-lookup"><span data-stu-id="96c67-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="96c67-117">ATOM ve RSS ile aynı akışın kullanılabilmesini bir hizmetin nasıl oluşturulacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="96c67-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="96c67-118">Dağıtım genişletilebilirliği</span><span class="sxs-lookup"><span data-stu-id="96c67-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="96c67-119">Akış bir dağıtım için öznitelikler ve özel öğeleri ekleme yöntemleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="96c67-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96c67-120">Başvuru</span><span class="sxs-lookup"><span data-stu-id="96c67-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96c67-121">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="96c67-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c67-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="96c67-122">See Also</span></span>  
 [<span data-ttu-id="96c67-123">WCF Web HTTP programlama modeli</span><span class="sxs-lookup"><span data-stu-id="96c67-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="96c67-124">Kısmi güven</span><span class="sxs-lookup"><span data-stu-id="96c67-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)