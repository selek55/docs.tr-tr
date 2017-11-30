---
title: "Nasıl yapılır: İstemci Kimlik Bilgileri Değerlerini Belirtme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee08f226492d7cb2327ac49ba57ac8bf24a57a07
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="cdcbd-102">Nasıl yapılır: İstemci Kimlik Bilgileri Değerlerini Belirtme</span><span class="sxs-lookup"><span data-stu-id="cdcbd-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="cdcbd-103">Kullanarak [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], hizmet istemci hizmete kimlik doğrulamasının nasıl belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-103">Using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="cdcbd-104">Örneğin, bir hizmeti bir sertifikayla istemcinin kimliğinin doğrulanmasını koşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="cdcbd-105">İstemci kimlik bilgisi türü belirlemek için</span><span class="sxs-lookup"><span data-stu-id="cdcbd-105">To determine the client credential type</span></span>  
  
1.  <span data-ttu-id="cdcbd-106">Meta veri hizmetin meta veri uç noktasından alır.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="cdcbd-107">Meta verileri genellikle iki dosyadan oluşur: programlama dili (varsayılan olarak Visual C#), istemci kodu ve bir XML yapılandırma dosyası.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="cdcbd-108">Meta Veri almanın bir yolu istemci kodu ve istemci yapılandırması geri dönmek için Svcutil.exe aracını kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="cdcbd-109">Daha fazla bilgi için bkz: [meta verileri alma](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) ve [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cdcbd-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2.  <span data-ttu-id="cdcbd-110">XML yapılandırma dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-110">Open the XML configuration file.</span></span> <span data-ttu-id="cdcbd-111">Svcutil.exe aracı kullanırsanız, varsayılan dosya Output.config adıdır.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3.  <span data-ttu-id="cdcbd-112">Bul  **\<Güvenlik >** öğeyle **modu** özniteliği (**< güvenlik modu =** `MessageOrTransport`  **>**  burada `MessageOrTransport` güvenlik modlarından birine ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4.  <span data-ttu-id="cdcbd-113">Mod değeri ile eşleşen alt öğesi bulunamıyor.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="cdcbd-114">Örneğin modu ayarlamak, **ileti**, bulma  **\<ileti >** öğesi içinde yer alan  **\<Güvenlik >** öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5.  <span data-ttu-id="cdcbd-115">Atanan değer Not **clientCredentialType** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="cdcbd-116">Hangi modun kullanılacağı üzerinde gerçek değer bağlıdır taşıma veya ileti.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="cdcbd-117">Aşağıdaki XML kodunu istemci kimlik doğrulaması ileti güvenliği kullanan ve bir sertifika gerektiren bir istemci için yapılandırmasını gösterir.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="cdcbd-118">Örnek: TCP taşıma modu istemci kimlik bilgileri olarak sertifikayla</span><span class="sxs-lookup"><span data-stu-id="cdcbd-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="cdcbd-119">Bu örnek güvenlik modunu aktarım modu için ayarlar ve istemci bir X.509 sertifikası kimlik bilgisi değeri ayarlar.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="cdcbd-120">Aşağıdaki yordamlar, istemci kodu ve yapılandırma içinde bulunan istemciye kimlik bilgisi değeri ayarlamak nasıl ekleyebileceğiniz gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="cdcbd-121">Bu, kullandığınız varsayar [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) meta veriler (kod ve yapılandırma) hizmetinden dönün.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="cdcbd-122">[Nasıl yapılır: bir istemci oluşturmak](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="cdcbd-122"> [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="cdcbd-123">Kod içinde bulunan istemciye istemci kimlik bilgisi değeri belirtmek için</span><span class="sxs-lookup"><span data-stu-id="cdcbd-123">To specify the client credential value on the client in code</span></span>  
  
1.  <span data-ttu-id="cdcbd-124">Kullanım [ServiceModel meta veri yardımcı Programracı (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) kod ve Yapılandırma hizmeti oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2.  <span data-ttu-id="cdcbd-125">Bir örneğini oluşturmak [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] istemci kullanılarak oluşturulan kod.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-125">Create an instance of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client using the generated code.</span></span>  
  
3.  <span data-ttu-id="cdcbd-126">Set istemci sınıfı üzerinde <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> özelliği <xref:System.ServiceModel.ClientBase%601> uygun bir değere sınıfı.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="cdcbd-127">Bu örnek, bir X.509 sertifikası kullanarak özelliği ayarlar <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> yöntemi <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="cdcbd-128">Numaralandırmalar birini kullanabilirsiniz <xref:System.Security.Cryptography.X509Certificates.X509FindType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="cdcbd-129">Konu adı, sertifika (sona erme tarihi nedeniyle) değiştiği durumda burada kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="cdcbd-130">Konu adı kullanarak sertifikayı yeniden bulmak için altyapı sağlar.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="cdcbd-131">Yapılandırma içinde bulunan istemciye istemci kimlik bilgisi değeri belirtmek için</span><span class="sxs-lookup"><span data-stu-id="cdcbd-131">To specify the client credential value on the client in configuration</span></span>  
  
1.  <span data-ttu-id="cdcbd-132">Ekleme bir [ \<davranışı >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) öğesine [ \<davranışları >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2.  <span data-ttu-id="cdcbd-133">Ekleme bir [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) öğesine [ \<davranışları >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="cdcbd-134">Gerekli ayarladığınızdan emin olun `name` öznitelik için uygun bir değer.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="cdcbd-135">Ekleme bir [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) öğesine [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4.  <span data-ttu-id="cdcbd-136">Aşağıdaki öznitelikler uygun değerlere ayarlayın: `storeLocation`, `storeName`, `x509FindType`, ve `findValue`aşağıdaki kodda gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="cdcbd-137">Sertifikalar, [sertifikalarla çalışma](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="cdcbd-137"> certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  <span data-ttu-id="cdcbd-138">İstemci yapılandırırken ayarlayarak davranışı belirtin `behaviorConfiguration` özniteliği `<endpoint>` aşağıdaki kodda gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="cdcbd-139">Uç nokta öğesi bir alt öğesi değil [ \<istemci >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="cdcbd-140">Ayrıca, ayarlayarak bağlama yapılandırması adını belirtin `bindingConfiguration` istemci için bağlama özniteliği.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="cdcbd-141">Oluşturulan yapılandırma dosyası kullanıyorsanız, bağlamanın adı otomatik olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="cdcbd-142">Bu örnekte, addır `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cdcbd-143">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cdcbd-143">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="cdcbd-144">WCF güvenliğini programlama</span><span class="sxs-lookup"><span data-stu-id="cdcbd-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="cdcbd-145">Bir kimlik bilgisi türü seçme</span><span class="sxs-lookup"><span data-stu-id="cdcbd-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="cdcbd-146">ServiceModel meta veri yardımcı Programracı (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="cdcbd-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="cdcbd-147">Sertifikalar ile çalışma</span><span class="sxs-lookup"><span data-stu-id="cdcbd-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="cdcbd-148">Nasıl yapılır: bir istemci oluşturma</span><span class="sxs-lookup"><span data-stu-id="cdcbd-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="cdcbd-149">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [<span data-ttu-id="cdcbd-150">\<Güvenlik ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [<span data-ttu-id="cdcbd-151">\<İleti ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [<span data-ttu-id="cdcbd-152">\<davranışı ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [<span data-ttu-id="cdcbd-153">\<davranışları ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [<span data-ttu-id="cdcbd-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [<span data-ttu-id="cdcbd-155">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="cdcbd-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)