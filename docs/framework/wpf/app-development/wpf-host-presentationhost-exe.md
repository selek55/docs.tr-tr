---
title: "WPF Konağı (PresentationHost.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7662213d7204675de7e8681b6fc8141f04dd21
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="2ef04-102">WPF Konağı (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2ef04-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="2ef04-103">Konağı (PresentationHost.exe) olan sağlayan uygulama [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] uyumlu tarayıcıda barındırılan uygulamalar (de dahil olmak üzere [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] ve üzeri).</span><span class="sxs-lookup"><span data-stu-id="2ef04-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="2ef04-104">Varsayılan olarak, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] konağı olarak kabuğa kayıtlı ve [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] işleyicisi için tarayıcıda barındırılan [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] içeren içerik:</span><span class="sxs-lookup"><span data-stu-id="2ef04-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="2ef04-105">Gevşek (derlenmemiş) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dosyaları (.xaml).</span><span class="sxs-lookup"><span data-stu-id="2ef04-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="2ef04-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="2ef04-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="2ef04-107">Bu tür dosyalar için [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] ana bilgisayar:</span><span class="sxs-lookup"><span data-stu-id="2ef04-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="2ef04-108">Kayıtlı başlatır [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] konak işleyicisine [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] içeriği.</span><span class="sxs-lookup"><span data-stu-id="2ef04-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="2ef04-109">Gerekli doğru sürümlerini yükler [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] ve [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] derlemeler.</span><span class="sxs-lookup"><span data-stu-id="2ef04-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="2ef04-110">Dağıtım bölgesi için uygun izin düzeylerinin yerinde olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ef04-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="2ef04-111">Bu konu, PresentationHost.exe ile kullanılabilen komut satırı parametreleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="2ef04-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2ef04-112">Kullanım</span><span class="sxs-lookup"><span data-stu-id="2ef04-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="2ef04-113">Parametreler</span><span class="sxs-lookup"><span data-stu-id="2ef04-113">Parameters</span></span>  
  
|<span data-ttu-id="2ef04-114">Parametre</span><span class="sxs-lookup"><span data-stu-id="2ef04-114">Parameter</span></span>|<span data-ttu-id="2ef04-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2ef04-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ef04-116">filename</span><span class="sxs-lookup"><span data-stu-id="2ef04-116">filename</span></span>|<span data-ttu-id="2ef04-117">Etkinleştirilecek dosyasının yolu.</span><span class="sxs-lookup"><span data-stu-id="2ef04-117">The path of the file to be activated.</span></span> <span data-ttu-id="2ef04-118">Aynı zamanda olabilir bir [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ef04-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="2ef04-119">-hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="2ef04-119">-debug</span></span>|<span data-ttu-id="2ef04-120">Bir uygulama etkinleştirilirken değil kendisine yürütün veya mağaza'dan çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="2ef04-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="2ef04-121">Bu, yalnızca yerel bir dosya etkinleştirildiğinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="2ef04-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="2ef04-122">-debugSecurityZoneURL \<url ></span><span class="sxs-lookup"><span data-stu-id="2ef04-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="2ef04-123">İle kullanılan bir [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] PresentationHost.exe'ye izin olarak dağıtıldıysa uygulama hata ayıklaması belirtmek için değer belirtilen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ef04-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="2ef04-124">Bu dağıtım bölgesini ve kaynak site belirler.</span><span class="sxs-lookup"><span data-stu-id="2ef04-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="2ef04-125">-katıştırma</span><span class="sxs-lookup"><span data-stu-id="2ef04-125">-embedding</span></span>|<span data-ttu-id="2ef04-126">OLE için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="2ef04-126">Required by OLE.</span></span> <span data-ttu-id="2ef04-127">Varsa `-event` veya `-debug` parametresi belirtilirse, belirtmek gerekli değildir `-embedding` parametresi, çünkü bu parametre dahili olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="2ef04-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="2ef04-128">-olay \<eventname ></span><span class="sxs-lookup"><span data-stu-id="2ef04-128">-event \<eventname></span></span>|<span data-ttu-id="2ef04-129">Bu ada sahip olayı açın ve PresentationHost.exe başlatılmış ve hazır konak olduğu sinyali [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] içeriği.</span><span class="sxs-lookup"><span data-stu-id="2ef04-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="2ef04-130">PresentationHost.exe sonlandırılacak olay açılırken bir hata varsa, eğer gibi zaten oluşturulmadı.</span><span class="sxs-lookup"><span data-stu-id="2ef04-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="2ef04-131">-launchApplication \<url ></span><span class="sxs-lookup"><span data-stu-id="2ef04-131">-launchApplication \<url></span></span>|<span data-ttu-id="2ef04-132">Tek başına başlatır [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] belirtilen URL'den uygulama.</span><span class="sxs-lookup"><span data-stu-id="2ef04-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]<span data-ttu-id="2ef04-133">ve .NET uygulamaları ile ilgili WinINet güvenlik ilkesi uygulanır.</span><span class="sxs-lookup"><span data-stu-id="2ef04-133"> and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="2ef04-134">Senaryolar</span><span class="sxs-lookup"><span data-stu-id="2ef04-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="2ef04-135">Kabuk işleyicisi</span><span class="sxs-lookup"><span data-stu-id="2ef04-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="2ef04-136">MIME işleyicisi</span><span class="sxs-lookup"><span data-stu-id="2ef04-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="2ef04-137">Visual Studio hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="2ef04-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="2ef04-138">Visual Studio bölgesinde hata ayıklaması</span><span class="sxs-lookup"><span data-stu-id="2ef04-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="2ef04-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2ef04-139">See Also</span></span>  
 [<span data-ttu-id="2ef04-140">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="2ef04-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)