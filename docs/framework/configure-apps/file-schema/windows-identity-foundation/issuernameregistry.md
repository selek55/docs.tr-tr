---
title: '&lt;issuerNameRegistry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7c9b40fb3afb5679496c3cb0dda7821b5b6b0b41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
Belirteci işleyicisi koleksiyonundaki işleyiciler tarafından kullanılan yayınlayıcı adı kaydını yapılandırır.  
  
 \<System.IdentityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|türü|Türetilen bir tür <xref:System.IdentityModel.Tokens.IssuerNameRegistry> sınıfı. Özel bir belirtme hakkında daha fazla bilgi için `type`, [özel tür başvuruları] bakın.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Zaman `type` özniteliği, yapılandırma tabanlı yayınlayıcı adı kaydını belirtir ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> sınıfı), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) öğesi belirtilmelidir. [ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) öğesi alabilir `<add>`, `<clear>`, veya `<remove>` öğelerini alt öğe.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Güvenlik bir koleksiyon için yapılandırma belirteci işleyicileri sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm veren belirteçleri yayınlayıcı adı kaydını kullanılarak doğrulanır. Türetilen bir nesne budur <xref:System.IdentityModel.Tokens.IssuerNameRegistry> sınıfı. Yayınlayıcı adı kaydını anımsatıcı adını karşılık gelen veren tarafından üretilen belirteçleri imzaları doğrulamak için gereken şifreleme malzeme ilişkilendirmek için kullanılır. Yayınlayıcı adı kaydını bağlı olan taraf (RP) uygulaması tarafından güvenilen verenlerin bir listesini tutar. Yayınlayıcı adı kaydını türünü kullanarak belirtilen `type` özniteliği. `<issuerNameRegistry>` Öğesi, belirtilen tür için yapılandırma sağlayan bir veya daha fazla alt öğeleri olabilir. Bu alt öğeleri geçersiz kılarak işler mantığın <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> yöntemi.  
  
 WIF sağlayan tek bir veren adı kayıt defteri türü kutusunda dışında <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> sınıfı. Bu sınıf, yapılandırma dosyasında belirtilen güvenilen yayıncı sertifikaları kümesi kullanır. Bir alt yapılandırma öğesi gerektiriyor `<trustedIssuers>`, güvenilen yayıncı sertifikaları koleksiyonunu yapılandırıldığı altında. Sertifikaları ASN.1 kullanarak kodlanmış form sertifika parmak izi ve eklenir veya koleksiyondan kullanarak kaldırılır belirtilen güvenilen `<add>`, `<clear>`, veya `<remove>` öğeleri.  
  
 `<issuerNameRegistry>` Öğesi ile temsil edilir <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> sınıfı.  
  
> [!NOTE]
>  Belirtme `<issuerNameRegistry>` öğesi bir alt öğesi olarak [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) öğesi kullanım dışı bırakıldı, ancak hala geriye dönük uyumluluk için desteklenir. Ayarları `<securityTokenHandlerConfiguration>` öğesi geçersiz kılar üzerinde `<identityConfiguration>` öğesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki XML tabanlı yapılandırma veren belirtmek adı kayıt defteri gösterilmiştir.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
