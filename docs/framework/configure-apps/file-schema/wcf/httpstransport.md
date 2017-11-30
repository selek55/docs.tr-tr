---
title: '&lt;httpsTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6ed4bc0-7e38-4348-9259-30bf61eb9435
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b6e89c0caac2ad1d967dedeecbb83e5779f9388
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="lthttpstransportgt"></a><span data-ttu-id="6c765-102">&lt;httpsTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="6c765-102">&lt;httpsTransport&gt;</span></span>
<span data-ttu-id="6c765-103">SOAP iletilerine özel bağlama için iletmek için bir HTTP taşıması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-103">Specifies an HTTP transport for transmitting SOAP messages for a custom binding.</span></span>  
  
 <span data-ttu-id="6c765-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c765-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6c765-105">\<bağlamaları ></span><span class="sxs-lookup"><span data-stu-id="6c765-105">\<bindings></span></span>  
<span data-ttu-id="6c765-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6c765-106">\<customBinding></span></span>  
<span data-ttu-id="6c765-107">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="6c765-107">\<binding></span></span>  
<span data-ttu-id="6c765-108">\<httpsTransport ></span><span class="sxs-lookup"><span data-stu-id="6c765-108">\<httpsTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c765-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6c765-109">Syntax</span></span>  
  
```xml  
<httpsTransport  
    allowCookies=Boolean"  
    authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"  
    bypassProxyOnLocal=Boolean"  
    hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
    manualAddressing="Boolean"  
    maxBufferPoolSize="Integer"  
    maxBufferSize="Integer"  
    maxReceivedMessageSize="Integer"  
    proxyAddress="Uri"  
    proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"        realm="String"  
    requireClientCertificate=Boolean"  
    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        unsafeConnectionNtlmAuthentication="Boolean"  
....useDefaultWebProxy="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c765-110">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c765-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6c765-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6c765-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c765-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="6c765-112">Attributes</span></span>  
  
|<span data-ttu-id="6c765-113">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="6c765-113">Attribute</span></span>|<span data-ttu-id="6c765-114">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c765-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c765-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="6c765-115">allowCookies</span></span>|<span data-ttu-id="6c765-116">İstemcinin tanımlama bilgilerini kabul eder ve sonraki isteklerde yayar belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-116">A Boolean value that specifies whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="6c765-117">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="6c765-118">Tanımlama bilgileri kullan ASMX Web Hizmetleri ile etkileşim kurarken, bu öznitelik kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6c765-118">You can use this attribute when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="6c765-119">Bu şekilde, sunucudan döndürülen tanımlama bilgilerini tüm gelecekteki istemci isteklerine hizmet otomatik olarak kopyalandığından emin olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c765-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="6c765-120">authenticationScheme</span><span class="sxs-lookup"><span data-stu-id="6c765-120">authenticationScheme</span></span>|<span data-ttu-id="6c765-121">Bir HTTP dinleyicisi tarafından işlenen istemci isteklerinin kimliğini doğrulamak için kullanılacak protokolü belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-121">Specifies the protocol used to authenticate client requests being processed by an HTTP listener.</span></span> <span data-ttu-id="6c765-122">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c765-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c765-123">-Özeti: Özet kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-123">-   Digest: Specifies digest authentication.</span></span><br /><span data-ttu-id="6c765-124">-Anlaş: kimlik doğrulama düzenini belirlemek için istemci ile görüşür.</span><span class="sxs-lookup"><span data-stu-id="6c765-124">-   Negotiate: Negotiates with the client to determine the authentication scheme.</span></span> <span data-ttu-id="6c765-125">İstemci ve sunucu Kerberos destekliyorsa, kullanılır; Aksi halde, NTLM kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6c765-125">If both client and server support Kerberos, it is used; otherwise, NTLM is used.</span></span><br /><span data-ttu-id="6c765-126">-Ntlm: NTLM kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-126">-   Ntlm: Specifies NTLM authentication.</span></span><br /><span data-ttu-id="6c765-127">-Temel: temel kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-127">-   Basic: Specifies basic authentication.</span></span><br /><span data-ttu-id="6c765-128">-Anonim: Anonim kimlik doğrulamasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-128">-   Anonymous: Specifies anonymous authentication.</span></span><br /><br /> <span data-ttu-id="6c765-129">Anonim varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6c765-129">The default is Anonymous.</span></span> <span data-ttu-id="6c765-130">Bu öznitelik türünde <xref:System.Net.AuthenticationSchemes>.</span><span class="sxs-lookup"><span data-stu-id="6c765-130">This attribute is of type <xref:System.Net.AuthenticationSchemes>.</span></span> <span data-ttu-id="6c765-131">Bu öznitelik yalnızca bir kez ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="6c765-131">This attribute can only be set once.</span></span>|  
|<span data-ttu-id="6c765-132">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="6c765-132">bypassProxyOnLocal</span></span>|<span data-ttu-id="6c765-133">Yerel adresler için proxy sunucuyu atla kılmayacağını gösteren bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-133">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="6c765-134">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-134">The default is `false`.</span></span><br /><br /> <span data-ttu-id="6c765-135">Yerel bir adres yerel LAN ya da intranet biridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-135">A local address is one that is on the local LAN or intranet.</span></span><br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="6c765-136">her zaman hizmeti adresi http://localhost ile başlıyorsa proxy yok sayar.</span><span class="sxs-lookup"><span data-stu-id="6c765-136"> always ignores the proxy if the service address begins with http://localhost.</span></span><br /><br /> <span data-ttu-id="6c765-137">İstemcileri bir proxy üzerinden hizmetler için aynı makinede konuşurken gitmek için isterseniz localhost yerine ana bilgisayar adı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c765-137">You should use the host name rather than localhost if you want clients to go through a proxy when talking to services on the same machine.</span></span>|  
|<span data-ttu-id="6c765-138">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="6c765-138">hostnameComparisonMode</span></span>|<span data-ttu-id="6c765-139">URI'ler ayrıştırmak için kullanılan HTTP ana bilgisayar adı karşılaştırma modunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-139">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="6c765-140">Geçerli değerler,</span><span class="sxs-lookup"><span data-stu-id="6c765-140">Valid values are,</span></span><br /><br /> <span data-ttu-id="6c765-141">-StrongWildcard: ("+") belirtilen şema, bağlantı noktası ve göreli URI bağlamında tüm olası ana bilgisayar adı ile eşleşir.</span><span class="sxs-lookup"><span data-stu-id="6c765-141">-   StrongWildcard: ("+") matches all possible hostnames in the context of the specified scheme, port and relative URI.</span></span><br /><span data-ttu-id="6c765-142">-Tam: joker</span><span class="sxs-lookup"><span data-stu-id="6c765-142">-   Exact: no wildcards</span></span><br /><span data-ttu-id="6c765-143">-WeakWildcard: ("*") bağlamında belirtilen düzenini, bağlantı noktası ve açıkça eşlenen olmayan göreli UIR ya da güçlü joker mekanizması aracılığıyla olası tüm ana bilgisayar adı ile eşleşir.</span><span class="sxs-lookup"><span data-stu-id="6c765-143">-   WeakWildcard: ("*") matches all possible hostname in the context of the specified scheme, port and relative UIR that have not been matched explicitly or through the strong wildcard mechanism.</span></span><br /><br /> <span data-ttu-id="6c765-144">StrongWildcard varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6c765-144">The default is StrongWildcard.</span></span> <span data-ttu-id="6c765-145">Bu öznitelik türünde `System.ServiceModel.HostnameComparison`.</span><span class="sxs-lookup"><span data-stu-id="6c765-145">This attribute is of type `System.ServiceModel.HostnameComparison`.</span></span>|  
|<span data-ttu-id="6c765-146">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="6c765-146">manualAddressing</span></span>|<span data-ttu-id="6c765-147">Kullanıcının ileti adresleme denetimini olanak tanıyan bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-147">A Boolean value that enables the user to take control of message addressing.</span></span> <span data-ttu-id="6c765-148">Bu özellik genellikle burada hangisinin bir ileti göndermek için birden fazla hedef uygulama belirler yönlendirici senaryolarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6c765-148">This property is usually used in router scenarios, where the application determines which one of several destinations to send a message to.</span></span><br /><br /> <span data-ttu-id="6c765-149">Ayarlandığında `true`, ileti zaten giderilmiş ve ek bilgiler için eklemez kanal varsayar.</span><span class="sxs-lookup"><span data-stu-id="6c765-149">When set to `true`, the channel assumes the message has already been addressed and does not add any additional information to it.</span></span> <span data-ttu-id="6c765-150">Kullanıcı daha sonra her ileti tek tek ele alabilir.</span><span class="sxs-lookup"><span data-stu-id="6c765-150">The user can then address every message individually.</span></span><br /><br /> <span data-ttu-id="6c765-151">Ayarlandığında `false`, varsayılan Windows Communication Foundation (WCF) adresleme mekanizması adresleri tüm iletiler için otomatik olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6c765-151">When set to `false`, the default Windows Communication Foundation (WCF) addressing mechanism automatically creates addresses for all messages.</span></span><br /><br /> <span data-ttu-id="6c765-152">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-152">The default is `false`.</span></span>|  
|<span data-ttu-id="6c765-153">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="6c765-153">maxBufferPoolSize</span></span>|<span data-ttu-id="6c765-154">Arabellek havuzu boyutunun üst sınırını belirtir pozitif bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="6c765-154">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="6c765-155">524288 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6c765-155">The default is 524288.</span></span><br /><br /> <span data-ttu-id="6c765-156">WCF pek çok bölümü arabellekleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="6c765-156">Many parts of WCF use buffers.</span></span> <span data-ttu-id="6c765-157">Oluşturma ve her defa arabellek yok etme pahalıdır ve atık toplama arabellekleri için de pahalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c765-157">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="6c765-158">Arabellek havuzu ile havuzdan bir arabellek ayırın, kullanmak ve tamamladıktan sonra havuza geri dönemez.</span><span class="sxs-lookup"><span data-stu-id="6c765-158">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="6c765-159">Bu nedenle oluşturma ve yok etme arabellekleri ek yük önlenmiş olur.</span><span class="sxs-lookup"><span data-stu-id="6c765-159">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="6c765-160">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="6c765-160">maxBufferSize</span></span>|<span data-ttu-id="6c765-161">Arabelleğin en büyük boyutu belirtir pozitif bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="6c765-161">A positive integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="6c765-162">524288 varsayılandır</span><span class="sxs-lookup"><span data-stu-id="6c765-162">The default is 524288</span></span>|  
|<span data-ttu-id="6c765-163">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="6c765-163">maxReceivedMessageSize</span></span>|<span data-ttu-id="6c765-164">Alınabilir maksimum izin verilen ileti boyutunu belirtir pozitif bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="6c765-164">A positive integer that specifies the maximum allowable message size that can be received.</span></span> <span data-ttu-id="6c765-165">65536 varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6c765-165">The default is 65536.</span></span>|  
|<span data-ttu-id="6c765-166">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="6c765-166">proxyAddress</span></span>|<span data-ttu-id="6c765-167">HTTP proxy adresini belirtir URI.</span><span class="sxs-lookup"><span data-stu-id="6c765-167">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="6c765-168">Varsa `useSystemWebProxy` olan `true`, bu ayar olmalıdır `null`.</span><span class="sxs-lookup"><span data-stu-id="6c765-168">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="6c765-169">Varsayılan, `null` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-169">The default is `null`.</span></span>|  
|<span data-ttu-id="6c765-170">proxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="6c765-170">proxyAuthenticationScheme</span></span>|<span data-ttu-id="6c765-171">Bir HTTP proxy'si tarafından işlenen istemci isteklerinin kimlik doğrulaması için kullanılacak protokolü belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-171">Specifies the protocol used for authenticating client requests being processed by an HTTP proxy.</span></span> <span data-ttu-id="6c765-172">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c765-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c765-173">-Hiçbiri: Kimlik doğrulaması gerçekleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="6c765-173">-   None: No authentication is performed.</span></span><br /><span data-ttu-id="6c765-174">-Özeti: Özet kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-174">-   Digest: Specifies digest authentication.</span></span><br /><span data-ttu-id="6c765-175">-Anlaş: kimlik doğrulama düzenini belirlemek için istemci ile görüşür.</span><span class="sxs-lookup"><span data-stu-id="6c765-175">-   Negotiate: Negotiates with the client to determine the authentication scheme.</span></span> <span data-ttu-id="6c765-176">İstemci ve sunucu Kerberos destekliyorsa, kullanılır; Aksi halde, NTLM kullanılır.</span><span class="sxs-lookup"><span data-stu-id="6c765-176">If both client and server support Kerberos, it is used; otherwise, NTLM is used.</span></span><br /><span data-ttu-id="6c765-177">-Ntlm: NTLM kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-177">-   Ntlm: Specifies NTLM authentication.</span></span><br /><span data-ttu-id="6c765-178">-Temel: temel kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-178">-   Basic: Specifies basic authentication.</span></span><br /><span data-ttu-id="6c765-179">-Anonim: Anonim kimlik doğrulamasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-179">-   Anonymous: Specifies anonymous authentication.</span></span><br /><span data-ttu-id="6c765-180">-IntegratedWindowsAuthentication: Windows kimlik doğrulaması belirtir.</span><span class="sxs-lookup"><span data-stu-id="6c765-180">-   IntegratedWindowsAuthentication: Specifies Windows authentication.</span></span><br /><br /> <span data-ttu-id="6c765-181">Anonim varsayılandır.</span><span class="sxs-lookup"><span data-stu-id="6c765-181">The default is Anonymous.</span></span> <span data-ttu-id="6c765-182">Bu öznitelik türünde <xref:System.Net.AuthenticationSchemes>.</span><span class="sxs-lookup"><span data-stu-id="6c765-182">This attribute is of type <xref:System.Net.AuthenticationSchemes>.</span></span>|  
|<span data-ttu-id="6c765-183">Bölge</span><span class="sxs-lookup"><span data-stu-id="6c765-183">realm</span></span>|<span data-ttu-id="6c765-184">Proxy/sunucuda kullanmak için bölge belirten bir dize.</span><span class="sxs-lookup"><span data-stu-id="6c765-184">A string that specifies the realm to use on the proxy/server.</span></span> <span data-ttu-id="6c765-185">Varsayılan boş bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="6c765-185">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="6c765-186">Sunucuları, korunan kaynaklara bölümlemek için bölgeleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="6c765-186">Servers use realms to partition protected resources.</span></span> <span data-ttu-id="6c765-187">Her bölüm kendi kimlik doğrulama düzeni ve/veya yetkilendirme veritabanına sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c765-187">Each partition can have its own authentication scheme and/or authorization database.</span></span> <span data-ttu-id="6c765-188">Bölge için basic kullanılır ve Özet kimlik doğrulaması.</span><span class="sxs-lookup"><span data-stu-id="6c765-188">Realms are used only for basic and digest authentication.</span></span> <span data-ttu-id="6c765-189">Bir istemci kimliğini başarıyla doğrulayan sonra kimlik doğrulama, belirli bir bölgedeki tüm kaynaklar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="6c765-189">After a client successfully authenticates, the authentication is valid for all resources in a given realm.</span></span> <span data-ttu-id="6c765-190">Bölge ayrıntılı bir açıklaması için RFC 2617 http://www.ietf.org bakın.</span><span class="sxs-lookup"><span data-stu-id="6c765-190">For a detailed description of realms, see RFC 2617 at http://www.ietf.org.</span></span>|  
|<span data-ttu-id="6c765-191">RequireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="6c765-191">requireClientCertificate</span></span>|<span data-ttu-id="6c765-192">Sunucunun HTTPS el sıkışmasının bir parçası olarak bir istemci sertifikası sağlamak için istemcinin gerektirip gerektirmediğini belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-192">A Boolean value that specifies if the server requires the client to provide a client certificate as part of the HTTPS handshake.</span></span> <span data-ttu-id="6c765-193">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-193">The default is `false`.</span></span>|  
|<span data-ttu-id="6c765-194">transferMode</span><span class="sxs-lookup"><span data-stu-id="6c765-194">transferMode</span></span>|<span data-ttu-id="6c765-195">İletileri olup ara belleğe veya akışa veya isteği belirtir veya yanıt.</span><span class="sxs-lookup"><span data-stu-id="6c765-195">Specifies whether messages are buffered or streamed or a request or response.</span></span> <span data-ttu-id="6c765-196">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c765-196">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c765-197">-Arabelleğe: İstek ve yanıt iletilerini arabelleğe.</span><span class="sxs-lookup"><span data-stu-id="6c765-197">-   Buffered: The request and response messages are buffered.</span></span><br /><span data-ttu-id="6c765-198">-Akışı: İstek ve yanıt iletileri akışa alınır.</span><span class="sxs-lookup"><span data-stu-id="6c765-198">-   Streamed: The request and response messages are streamed.</span></span><br /><span data-ttu-id="6c765-199">-StreamedRequest: İstek iletisi akışı ve yanıt iletisi arabelleğe alındı.</span><span class="sxs-lookup"><span data-stu-id="6c765-199">-   StreamedRequest: The request message is streamed and the response message is buffered.</span></span><br /><span data-ttu-id="6c765-200">-Da StreamedResponse: İstek iletisi arabelleğe alınıp ve yanıt iletisi akışı.</span><span class="sxs-lookup"><span data-stu-id="6c765-200">-   StreamedResponse: The request message is buffered and the response message is streamed.</span></span><br /><br /> <span data-ttu-id="6c765-201">Varsayılan arabelleğe alındı.</span><span class="sxs-lookup"><span data-stu-id="6c765-201">The default is Buffered.</span></span> <span data-ttu-id="6c765-202">Bu öznitelik türünde <xref:System.ServiceModel.TransferMode>.</span><span class="sxs-lookup"><span data-stu-id="6c765-202">This attribute is of type <xref:System.ServiceModel.TransferMode>.</span></span>|  
|<span data-ttu-id="6c765-203">unsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="6c765-203">unsafeConnectionNtlmAuthentication</span></span>|<span data-ttu-id="6c765-204">Güvenli bağlantı paylaşımı sunucu üzerinde etkin olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-204">A Boolean value that specifies whether Unsafe Connection Sharing is enabled on the server.</span></span> <span data-ttu-id="6c765-205">Varsayılan, `false` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-205">The default is `false`.</span></span> <span data-ttu-id="6c765-206">Etkinleştirilirse, NTLM kimlik doğrulaması her TCP bağlantısı için bir kez gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="6c765-206">If enabled, NTLM authentication is performed once on each TCP connection.</span></span>|  
|<span data-ttu-id="6c765-207">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="6c765-207">useDefaultWebProxy</span></span>|<span data-ttu-id="6c765-208">Makine genelinde proxy ayarlarını yerine kullanıcıya özgü ayarları kullanılıp kullanılmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6c765-208">A Boolean value that specifies whether the machine-wide proxy settings are used rather than the user specific settings.</span></span> <span data-ttu-id="6c765-209">Varsayılan, `true` değeridir.</span><span class="sxs-lookup"><span data-stu-id="6c765-209">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c765-210">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c765-210">Child Elements</span></span>  
 <span data-ttu-id="6c765-211">Yok.</span><span class="sxs-lookup"><span data-stu-id="6c765-211">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c765-212">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="6c765-212">Parent Elements</span></span>  
  
|<span data-ttu-id="6c765-213">Öğe</span><span class="sxs-lookup"><span data-stu-id="6c765-213">Element</span></span>|<span data-ttu-id="6c765-214">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6c765-214">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c765-215">\<bağlama ></span><span class="sxs-lookup"><span data-stu-id="6c765-215">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6c765-216">Özel bağlama tüm bağlama özelliklerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="6c765-216">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c765-217">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6c765-217">Remarks</span></span>  
 <span data-ttu-id="6c765-218">`httpsTransport` Öğesidir başlangıç noktası için bir özel, bağlama oluşturma HTTPS aktarım protokolünü uygular.</span><span class="sxs-lookup"><span data-stu-id="6c765-218">The `httpsTransport` element is the starting point for creating a custom binding that implements the HTTPS transport protocol.</span></span> <span data-ttu-id="6c765-219">HTTPS güvenli birlikte çalışabilirlik amaçlar için kullanılan birincil Aktarım ' dir.</span><span class="sxs-lookup"><span data-stu-id="6c765-219">HTTPS is the primary transport used for secure interoperability purposes.</span></span> <span data-ttu-id="6c765-220">HTTPS tarafından desteklenen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] diğer Web ile birlikte çalışabilirlik yığınları hizmetleri sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="6c765-220">HTTPS is supported by the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to ensure interoperability with other Web services stacks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c765-221">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6c765-221">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HttpsTransportElement>  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6c765-222">Taşımalar</span><span class="sxs-lookup"><span data-stu-id="6c765-222">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="6c765-223">Taşıma seçme</span><span class="sxs-lookup"><span data-stu-id="6c765-223">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="6c765-224">Bağlamaları</span><span class="sxs-lookup"><span data-stu-id="6c765-224">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6c765-225">Bağlamaları genişletme</span><span class="sxs-lookup"><span data-stu-id="6c765-225">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6c765-226">Özel bağlamalar</span><span class="sxs-lookup"><span data-stu-id="6c765-226">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6c765-227">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6c765-227">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)