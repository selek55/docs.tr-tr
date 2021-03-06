---
title: "ServiceHost Hizmet Modeli Katmanını Genişletme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c73af3b9187fa5365d7ea99474ea182d5f5ae86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>ServiceHost Hizmet Modeli Katmanını Genişletme
Temel alınan kanalları dışında gelen iletileri çekme, bunları yöntem çağrılarına uygulama kodundaki içine çevirme ve sonuçları çağırana geri göndermek için hizmet modeli katmanını sorumludur. Hizmet modeli uzantıları değiştirebilir veya yürütme veya iletişim davranışı ve istemci veya dağıtıcısı işlevi, özel davranışları, ileti ve parametre kişiler tarafından ele ve diğer genişletilebilirlik işlevleri içeren özellikler uygular.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [İstemcileri Genişletme](../../../../docs/framework/wcf/extending/extending-clients.md)  
 Kesebilen ve istemci çalışma zamanı olarak özel uzantılarınızın istemci uygulamalarında ekleyebilirsiniz sınıfları değiştirme arabirimler açıklanmaktadır. Örneğin, özel istemci ileti günlüğe kaydetme gerçekleştirmek, özel ileti serileştirme gerçekleştirmek ve benzeri.  
  
 [Dağıtıcıları Genişletme](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 Kesebilen ve hizmet çalışma zamanı olarak özel uzantılarınızın hizmet uygulamalarını ekleyebilirsiniz sınıfları değiştirme arabirimler açıklanmaktadır. Örneğin, özel hizmet günlüğü, hizmet tarafı ileti doğrulama, özel göndermeyi ve benzeri gerçekleştirebilirsiniz.  
  
 [Genişletilebilen Nesneler](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 Beş genişletilebilen nesneler açıklar ve <xref:System.ServiceModel.IExtensibleObject%601> düzeni. Genişletilebilir object deseni ya da varolan çalışma zamanı sınıflarını yeni işlevselliği ile genişletmek veya bir nesne için yeni durum eklemek için kullanılır. Genişletilebilen nesneler birine ekli uzantılar, paylaşılan durum ve bunlar erişebileceği bir ortak Genişletilebilir nesneye iliştirilmiş işlevlerine erişimini işleme çok farklı aşamalarında davranışları etkinleştirin.  
  
 [Çalışma Zamanını Davranışlarla Yapılandırma ve Genişletme](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 Ayarları değiştirmek veya uzantıları eklemeyi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] çalışma zamanı, davranışları kullanın. WCF sistem uygulanan davranış azaltma, depolamasına ve birçok diğer yönlerini Hizmetleri ve işlemleri denetleme içerir. Bu bölümde, kendi özel davranışları ve bunları her iki program aracılığıyla kullanımına nasıl ve yapılandırma dosyaları kullanılarak nasıl oluşturulacağını açıklar.  
  
 [ServiceHostFactory Kullanarak Barındırmayı Genişletme](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 Nasıl genişletileceğini açıklar <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>ve <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> ana bilgisayar ortamının özelleştirmek için sınıflar.  
  
## <a name="reference"></a>Başvuru  
  
## <a name="related-sections"></a>İlgili Bölümler
