---
title: '&lt;hizmeti&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 689dfae90baffa3e9895258d1635c7840d8df6b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicegt"></a>&lt;hizmeti&gt;
`service` Öğesi bir Windows Communication Foundation (WCF) hizmet ayarlarını içerir. Ayrıca, hizmeti kullanıma uç noktaları içerir.  
  
 \<Sistem. ServiceModel >  
\<Hizmetleri >  
\<Hizmet >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|behaviorConfiguration|Hizmet örneği oluşturmak için kullanılacak davranış davranışı adını içeren dize. Davranış adı Hizmet tanımlı bir noktada kapsamında olması gerekir. Varsayılan değer boş bir dizedir.|  
|name|Örneğinin oluşturulması için hizmet türünü belirten dize özniteliği gerekli. Bu ayar için geçerli bir tür eşitlemek gerekir. Biçiminde olmalıdır`Namespace.Class.`|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<uç noktası >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Bir koleksiyonu `endpoint` bu hizmeti kullanıma öğeleri.|  
|[\<ana bilgisayar >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Bu hizmet örneği ana belirtir. Bu öğe türünde <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<Hizmetleri >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Tüm WCF yapılandırma öğelerinin kök öğesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Hizmetleri tanımlanmış `services` yapılandırma dosyasının. Bir derlemeyi Hizmetleri herhangi bir sayıda içerebilir. Her hizmetin kendi vardır `service` yapılandırma bölümü. Bu bölümde ve içeriğini hizmet sözleşmesini, davranış ve belirli bir hizmet uç noktalarına tanımlayın.  
  
 `behaviorConfiguration` Öğesidir Ayrıca isteğe bağlı. Hizmet davranışını tanımlayan kullanır. Bu öznitelikte belirtilen davranışı aynı yapılandırma dosyası kapsamındaki bir davranış bağlanmanız gerekir.  
  
 Her hizmet bir veya daha fazla uç noktalar, kendi adres ve bağlama olan kullanıma sunar. Yapılandırma dosyasının içinde kullanılan tüm bağlamaları dosya kapsamında tanımlanmış olması gerekir. Bağlama uç noktaları özniteliklerini birleşimi yoluyla bağlı `name` ve `bindingConfiguration`. `name` Özniteliğini bağlama tanımlanmış bölüm açıklar. `bindingConfiguration` Öznitelik tanımlar bağlama bölüm içindeki hangi yapılandırma kullanılır. Bir bağlama bölümü birkaç yapılandırmaları tanımlayabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Bu, bir hizmet yapılandırması örneğidir.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [Hizmetleri Yapılandırma](../../../../../docs/framework/wcf/configuring-services.md)
