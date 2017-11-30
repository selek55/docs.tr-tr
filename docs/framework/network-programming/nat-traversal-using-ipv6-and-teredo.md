---
title: "NAT IPv6 ve Teredo kullanarak geçişi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 466e3faed9b2877671ca265afdb613607b12f0de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="nat-traversal-using-ipv6-and-teredo"></a><span data-ttu-id="ea2fe-102">NAT IPv6 ve Teredo kullanarak geçişi</span><span class="sxs-lookup"><span data-stu-id="ea2fe-102">NAT Traversal using IPv6 and Teredo</span></span>
<span data-ttu-id="ea2fe-103">Ağ adresi çevirisi (NAT) geçişi için destek sağlayan geliştirmeler yapıldı.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-103">Enhancements were made that provide support for Network Address Translation (NAT) traversal.</span></span> <span data-ttu-id="ea2fe-104">Bu değişiklikler, IPv6 ve Teredo kullanmak için tasarlanmıştır ancak de teknolojileri tünel diğer IP uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-104">These changes are designed for use with IPv6 and Teredo, but they are also applicable to other IP tunneling technologies.</span></span> <span data-ttu-id="ea2fe-105">Bu geliştirmeler sınıflarda etkileyen <xref:System.Net> ve ilgili ad alanları.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-105">These enhancements affect classes in the <xref:System.Net> and related namespaces.</span></span>  
  
 <span data-ttu-id="ea2fe-106">Bu değişiklikler IP teknolojileri tünel kullanmayı planlıyorsanız istemci ve sunucu uygulamaları etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-106">These changes can affect client and server applications that plan to use IP tunneling technologies.</span></span>  
  
 <span data-ttu-id="ea2fe-107">NAT geçişi desteklemek için değişiklikler yalnızca .NET Framework sürüm 4 kullanan uygulamalar için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-107">The changes to support NAT traversal are available only for applications using .NET Framework version 4.</span></span> <span data-ttu-id="ea2fe-108">Bu özellikler, .NET Framework'ün önceki sürümlerinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-108">These features are not available on earlier versions of the .NET Framework.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="ea2fe-109">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="ea2fe-109">Overview</span></span>  
 <span data-ttu-id="ea2fe-110">Internet Protokolü sürüm 4 (IPv4) bir IPv4 adresi 32 bit uzunluğunda tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-110">The Internet Protocol version 4 (IPv4) defined an IPv4 address as 32 bits long.</span></span> <span data-ttu-id="ea2fe-111">Sonuç olarak, IPv4 yaklaşık 4 milyar benzersiz IP adreslerini destekler (2 ^ 32).</span><span class="sxs-lookup"><span data-stu-id="ea2fe-111">As a result, IPv4 supports approximately 4 billion unique IP addresses (2^32).</span></span> <span data-ttu-id="ea2fe-112">Bilgisayarları ve ağ aygıtları 1990'ların genişletilmiş Internet'te sayısı IPv4 adres alanı sınırları belirgin hale geldi.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-112">As the number of computers and network devices on the Internet expanded in the 1990s, the limits of the IPv4 address space became apparent.</span></span>  
  
 <span data-ttu-id="ea2fe-113">Çok sayıda özel IP temsil etmek tek benzersiz bir ortak IP adresi izin vermek için NAT dağıtmak için açıldı IPv4 ömrü genişletmek için kullanılan birkaç teknikleri birini adresleri (özel Intranet).</span><span class="sxs-lookup"><span data-stu-id="ea2fe-113">One of several techniques used to extend the lifetime of IPv4 has been to deploy NAT to allow a single unique public IP address to represent a large number of private IP addresses (private Intranet).</span></span> <span data-ttu-id="ea2fe-114">NAT cihazının arkasında özel IP adresleri tek genel IPv4 adresi paylaşır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-114">The private IP addresses behind the NAT device share the single public IPv4 address.</span></span> <span data-ttu-id="ea2fe-115">NAT cihazının adanmış bir donanımsal cihaz (bir ucuz kablosuz erişim noktası ve yönlendirici, örneğin) ya da NAT sağlamak için bir hizmeti çalıştıran bir bilgisayar olabilir</span><span class="sxs-lookup"><span data-stu-id="ea2fe-115">The NAT device may be a dedicated hardware device (an inexpensive Wireless Access Point and router, for example) or a computer running a service to provide NAT.</span></span> <span data-ttu-id="ea2fe-116">Bir aygıt veya hizmeti bu ortak IP adresi için ortak Internet ve özel Intranet arasında IP ağ paketlerinin çevirir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-116">A device or service for this public IP address translates IP network packets between the public Internet and the private Intranet.</span></span>  
  
 <span data-ttu-id="ea2fe-117">Bu düzen de Internet üzerindeki diğer IP adresleri (genellikle sunucuları) istekleri göndermek özel Intranet üzerinde çalışan istemci uygulamalar için çalışır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-117">This scheme works well for client applications running on the private Intranet that send requests to other IP addresses (usually servers) on the Internet.</span></span> <span data-ttu-id="ea2fe-118">Yanıtın gönderileceği yeri bildiği bir yanıt döndürdü NAT cihazı veya sunucu, istemci istekleri eşleme bunu tutabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-118">The NAT device or server can keep a mapping of client requests so when a response is returned it knows where to send the response.</span></span> <span data-ttu-id="ea2fe-119">Ancak bu düzeni istediğiniz hizmetleri sağlamak, paketlerini dinleme ve yanıt özel intranet NAT cihazının arkasında çalışan uygulamalar için sorunlar doğurur.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-119">But this scheme poses problems for applications running in the private Intranet behind the NAT device that want to provide services, listen for packets, and respond.</span></span> <span data-ttu-id="ea2fe-120">Bu durum özellikle eşler arası uygulamaları için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-120">This is particularly the case for peer-to-peer applications.</span></span>  
  
 <span data-ttu-id="ea2fe-121">IPv6 protokolü, bir IPv4 adresi 128 bit uzunluğunda tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-121">The IPv6 protocol defined an IPv4 address as 128 bits long.</span></span> <span data-ttu-id="ea2fe-122">Sonuç olarak, bir çok büyük IP adresi alanı 3.2 x 10 IPv6'yı destekleyen ^ 38 benzersiz adresler (2 ^ 128).</span><span class="sxs-lookup"><span data-stu-id="ea2fe-122">As a result, IPv6 supports very a large IP address space of 3.2 x 10^38 unique addresses (2^128).</span></span> <span data-ttu-id="ea2fe-123">Bu boyutta bir adres alanıyla benzersiz bir adresi verilecek Internet'e bağlı her bir aygıtı mümkündür.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-123">With an address space of this size, it is possible for every device connected to the Internet to be given a unique address.</span></span> <span data-ttu-id="ea2fe-124">Ancak sorunları vardır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-124">But there are problems.</span></span> <span data-ttu-id="ea2fe-125">Büyük bir dünya hala yalnızca IPv4 kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-125">Much of the world is still using only IPv4.</span></span> <span data-ttu-id="ea2fe-126">Özellikle, mevcut yönlendiriciler ve küçük şirketler, kuruluşlar ve ekleyebileceği tarafından kullanılan kablosuz erişim noktaları çoğu IPv6 desteklemez.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-126">In particular, many of the existing routers and wireless access points used by small companies, organizations, and households do not support IPv6.</span></span> <span data-ttu-id="ea2fe-127">Ayrıca bu müşterilerin hizmet bazı Internet hizmet sağlayıcıları desteklemiyor ya da IPv6 desteği yapılandırılmadı.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-127">Also some Internet service providers that serve these customers either do not support or have not configured support for IPv6.</span></span>  
  
 <span data-ttu-id="ea2fe-128">Birden fazla IPv6 geçiş teknolojileri, IPv4 paketinin tünel IPv6 adresleri için geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-128">Several IPv6 transition technologies have been developed to tunnel IPv6 addresses in an IPv4 packet.</span></span> <span data-ttu-id="ea2fe-129">Teredo IPv6 ana IP4 ağları diğer IPv6 ağları ulaşmak için geçmesi gereken zaman, tek noktaya yayın IPv6 trafiği için adres ataması ve ana otomatik tünel sağlayan tünelleri ve 6to4, ISATAP, bu teknolojileri içerir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-129">These technologies include 6to4, ISATAP, and Teredo tunnels that provide address assignment and host-to-host automatic tunneling for unicast IPv6 traffic when IPv6 hosts must traverse IP4 networks to reach other IPv6 networks.</span></span> <span data-ttu-id="ea2fe-130">IPv6 paketlerini IPv4 paketleri tünel gönderilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-130">IPv6 packets are sent tunneled as IPv4 packets.</span></span> <span data-ttu-id="ea2fe-131">Bir NAT cihazı üzerinden IPv6 adresleri için NAT geçişi sağlayan birkaç tünel teknikleri kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-131">Several tunneling techniques are being used that allow NAT traversal for IPv6 addresses through a NAT device.</span></span>  
  
 <span data-ttu-id="ea2fe-132">Teredo IPv4 ağları için IPv6 bağlantısı sunan IPv6 geçiş teknolojileri biridir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-132">Teredo is one of the IPv6 transition technologies which brings IPv6 connectivity to IPv4 networks.</span></span> <span data-ttu-id="ea2fe-133">Teredo RFC Internet Engineering Task Force (IETF) tarafından yayımlanan 4380 belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-133">Teredo is documented in RFC 4380 published by the Internet Engineering Task Force (IETF).</span></span> <span data-ttu-id="ea2fe-134">Windows XP SP2 ve daha sonra bir genel IPv6 adresi aralığı 2001:0 sağlayan sanal bir Teredo bağdaştırıcı için destek sağlayabilirsiniz:: / 32.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-134">Windows XP SP2 and later provide support for a virtual Teredo adapter which can provide a public IPv6 address in the range 2001:0::/32.</span></span> <span data-ttu-id="ea2fe-135">Şu IPv6 adresi Internet'ten gelen bağlantıları dinlemek için kullanılan ve dinleme hizmetine bağlanmak istemezseniz IPv6 etkin istemciler için sağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-135">This IPv6 address can be used to listen for incoming connections from the Internet and can be provided to IPv6 enabled clients that wish to connect to the listening service.</span></span> <span data-ttu-id="ea2fe-136">Bu uygulama yalnızca IPv6 Teredo adresini kullanarak bağlanabilmesi bu yana bir bilgisayarı bir NAT cihazının arkasında adres konusunda kaygı bir uygulamanın boşaltır.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-136">This frees an application from worrying about how to address a computer behind a NAT device, since the application can just connect to it using its IPv6 Teredo address.</span></span>  
  
## <a name="enhancements-to-support-nat-traversal-and-teredo"></a><span data-ttu-id="ea2fe-137">Destek NAT geçişi ve Teredo geliştirmeleri</span><span class="sxs-lookup"><span data-stu-id="ea2fe-137">Enhancements to Support NAT Traversal and Teredo</span></span>  
 <span data-ttu-id="ea2fe-138">Geliştirmeleri eklenmiştir <xref:System.Net>, <xref:System.Net.NetworkInformation>, ve <xref:System.Net.Sockets> IPv6 ve Teredo kullanarak NAT geçişi desteklemek için ad alanları.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-138">Enhancements are added to the <xref:System.Net>, <xref:System.Net.NetworkInformation>, and <xref:System.Net.Sockets> namespaces for supporting NAT traversal using IPv6 and Teredo.</span></span>  
  
 <span data-ttu-id="ea2fe-139">Çeşitli yöntemler eklenir <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType> tek noktaya yayın listesi konakta IP adreslerini almak için sınıf.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-139">Several methods are added to the <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType> class to get the list of unicast IP addresses on the host.</span></span> <span data-ttu-id="ea2fe-140"><xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> Yöntemi yerel bilgisayarda kararlı tek noktaya yayın IP adresi tablosu almak için zaman uyumsuz isteği başlar.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-140">The <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> method begins an asynchronous request to retrieve the stable unicast IP address table on the local computer.</span></span> <span data-ttu-id="ea2fe-141"><xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> Yöntemi yerel bilgisayarda kararlı tek noktaya yayın IP adresi tablosu almak için bekleyen bir zaman uyumsuz istek sona erer.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-141">The <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> method ends a pending asynchronous request to retrieve the stable unicast IP address table on the local computer.</span></span> <span data-ttu-id="ea2fe-142"><xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> Yöntemdir adres tablosunu gerekirse kararlı hale gelinceye kadar bekleyen yerel bilgisayarda kararlı tek noktaya yayın IP adresi tablosu almak için zaman uyumlu bir istek.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-142">The <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> method is a synchronous request to retrieve the stable unicast IP address table on the local computer, waiting until the address table stabilizes if necessary.</span></span>  
  
 <span data-ttu-id="ea2fe-143"><xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType> Özelliği, belirlemek için kullanılabilir bir <xref:System.Net.IPAddress> bir IPv6 Teredo adres.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-143">The <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType> property can be used to determine if an <xref:System.Net.IPAddress> is an IPv6 Teredo address.</span></span>  
  
 <span data-ttu-id="ea2fe-144">Bu yeni kullanarak <xref:System.Net.NetworkInformation.IPGlobalProperties> sınıfı yöntemlerinin birlikte <xref:System.Net.IPAddress.IsIPv6Teredo%2A> özelliği, bir Teredo adresi kolayca bulmak uygulama izin verir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-144">Using these new <xref:System.Net.NetworkInformation.IPGlobalProperties> class methods in combination with the <xref:System.Net.IPAddress.IsIPv6Teredo%2A> property allows an application to easily find the Teredo address.</span></span> <span data-ttu-id="ea2fe-145">Uygulamanın normal olarak, yalnızca uzak uygulamalar için bu bilgileri halindeyse yerel Teredo adresini bilmeniz gerekiyor.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-145">An application normally only needs to know the local Teredo address if it is communicating this information to remote applications.</span></span> <span data-ttu-id="ea2fe-146">Örneğin, bir eşler arası uygulaması tüm kendi IPv6 adreslerini, sonra bunları başkalarına iletmek bir matchmaking sunucusuna eşlere doğrudan iletişim sağlamak için gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-146">For example, a peer-to-peer application might send all of its IPv6 addresses to a matchmaking server which can then forward them to others peers to enable direct communication.</span></span>  
  
 <span data-ttu-id="ea2fe-147">Bir uygulama üzerinde dinleme onun dinleme hizmeti normal şekilde ayarlamanız gerekir <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType> yerine yerel Teredo adres.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-147">An application should normally set its listening service to listen on <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType> rather than on the local Teredo address.</span></span> <span data-ttu-id="ea2fe-148">Bu nedenle bir uzak istemci veya eş için dinleme hizmeti konak doğrudan bir IPv6 yolunun varsa, istemci veya eş IPv6 kullanarak doğrudan bağlanabilir ve Teredo Tünel paketlerini kullanmak zorunda kalmazsınız.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-148">So if a remote client or peer has a direct IPv6 route to the host of the listening service, the client or peer can connect directly using IPv6 and not have to use Teredo to tunnel packets.</span></span>  
  
 <span data-ttu-id="ea2fe-149">TCP uygulamalar için <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType> sınıfına sahip bir <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> NAT geçişi etkinleştirmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-149">For TCP applications, the <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType> class has an <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> method to enable NAT traversal.</span></span> <span data-ttu-id="ea2fe-150">UDP uygulamalar için <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType> sınıfına sahip bir <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> NAT geçişi etkinleştirmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-150">For UDP applications, the <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType> class has an <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> method to enable NAT traversal.</span></span>  
  
 <span data-ttu-id="ea2fe-151">Kullanan uygulamalar için <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> ve ilgili sınıfların <xref:System.Net.Sockets.Socket.GetSocketOption%2A> ve <xref:System.Net.Sockets.Socket.SetSocketOption%2A> yöntemleri ile kullanılabilir <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> yuva sorgu etkinleştirmek ya da NAT geçişi devre dışı bırakmak için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-151">For applications that use the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> and related classes, the <xref:System.Net.Sockets.Socket.GetSocketOption%2A> and <xref:System.Net.Sockets.Socket.SetSocketOption%2A> methods can be used with the <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> socket option to query, enable, or disable NAT traversal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2fe-152">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ea2fe-152">See Also</span></span>  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>  
 <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=nameWithType>  
 <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=nameWithType>  
 <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=nameWithType>