---
title: "&lt;clientCredentials&gt; Öğesi &lt;pencereleri&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc98f45d197675f8cc9618f08447cc42acdd1872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="903df-102">&lt;clientCredentials&gt; Öğesi &lt;pencereleri&gt;</span><span class="sxs-lookup"><span data-stu-id="903df-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="903df-103">İstemci temsil etmek için kullanılacak bir Windows kimlik bilgileri ayarlarını belirtir.</span><span class="sxs-lookup"><span data-stu-id="903df-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="903df-104">\<Sistem. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="903df-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="903df-105">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="903df-105">\<behaviors></span></span>  
<span data-ttu-id="903df-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="903df-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="903df-107">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="903df-107">\<behavior></span></span>  
<span data-ttu-id="903df-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="903df-108">\<clientCredentials></span></span>  
<span data-ttu-id="903df-109">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="903df-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903df-110">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="903df-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="903df-111">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="903df-111">Attributes and Elements</span></span>  
 <span data-ttu-id="903df-112">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="903df-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="903df-113">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="903df-113">Attributes</span></span>  
  
|<span data-ttu-id="903df-114">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="903df-114">Attribute</span></span>|<span data-ttu-id="903df-115">Açıklama</span><span class="sxs-lookup"><span data-stu-id="903df-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="903df-116">İstemci iletişim kuruyorsa kimliğe bürünme tercih sunucuya ayarlar.</span><span class="sxs-lookup"><span data-stu-id="903df-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="903df-117">İstemcinin kimliğe bürünme modu sunucuda zorlanmaz.</span><span class="sxs-lookup"><span data-stu-id="903df-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="903df-118">Geçerli değerler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="903df-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="903df-119">-Kimliği: Sunucunun kimliğini ve istemci ayrıcalıkların alabilir, ancak istemci alınamıyor.</span><span class="sxs-lookup"><span data-stu-id="903df-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="903df-120">-Kimliğe bürünme: Sunucu istemcinin güvenlik bağlamı yerel sistemde kimliğine bürünebilir.</span><span class="sxs-lookup"><span data-stu-id="903df-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="903df-121">-Temsilci: Sunucu istemcinin güvenlik bağlamı uzak sistemlere kimliğine bürünebilir.</span><span class="sxs-lookup"><span data-stu-id="903df-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="903df-122">-Anonim: Sunucusu taklit veya istemci kimliği.</span><span class="sxs-lookup"><span data-stu-id="903df-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="903df-123">-Hiçbiri: Kimliğe bürünme düzeyi atanmadı.</span><span class="sxs-lookup"><span data-stu-id="903df-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="903df-124">Varsayılan kimliğidir.</span><span class="sxs-lookup"><span data-stu-id="903df-124">The default is Identification.</span></span> <span data-ttu-id="903df-125">Bu öznitelik türünde <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="903df-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="903df-126">Bu özelliği ayarlamak `true` Kerberos kullanılabilir değilse, NTLM olarak düşürmek için kimlik doğrulaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="903df-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="903df-127">Bu özelliği ayarlamak `false` neden [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] NTLM kullanılırsa, bir özel durum için bir en iyi çaba yapma.</span><span class="sxs-lookup"><span data-stu-id="903df-127">Setting this property to `false` causes [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="903df-128">Bu özelliği ayarlamak Not `false` NTLM kimlik bilgileri kablo üzerinden gönderilen engelleyebilir değil.</span><span class="sxs-lookup"><span data-stu-id="903df-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="903df-129">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="903df-129">Child Elements</span></span>  
 <span data-ttu-id="903df-130">Yok.</span><span class="sxs-lookup"><span data-stu-id="903df-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="903df-131">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="903df-131">Parent Elements</span></span>  
  
|<span data-ttu-id="903df-132">Öğe</span><span class="sxs-lookup"><span data-stu-id="903df-132">Element</span></span>|<span data-ttu-id="903df-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="903df-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="903df-134">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="903df-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="903df-135">Hizmeti için istemci kimlik doğrulaması için kullanılan kimlik bilgilerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="903df-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="903df-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="903df-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="903df-137">İstemcilerinin güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="903df-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="903df-138">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="903df-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="903df-139">Hizmetler ve istemcileri güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="903df-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)