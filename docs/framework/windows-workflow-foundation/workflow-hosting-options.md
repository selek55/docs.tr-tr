---
title: "İş akışı barındırma seçenekleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be885a964ad7e8d63045febfa279b23d0d85ab1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-hosting-options"></a>İş akışı barındırma seçenekleri
Çoğu [!INCLUDE[wf](../../../includes/wf-md.md)] örnekleri bir konsol uygulamasında barındırılan iş akışlarını kullanır, ancak bu gerçek iş akışları için gerçekçi bir senaryo değildir. Gerçek iş uygulamalarını iş akışlarında barındırılacağı kalıcı işlemleri bir Windows hizmeti geliştirici ya da bir sunucu uygulaması tarafından gibi yazılan- [!INCLUDE[iisver](../../../includes/iisver-md.md)] veya AppFabric. Bu yaklaşım arasındaki farklar aşağıdaki gibidir.  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>IIS Windows AppFabric ile iş akışlarında barındırma  
 IIS ile AppFabric iş akışları için tercih edilen konak kullanmaktır. IIS üzerinde tek başına HTTP üzerindeki bağımlılığı kaldırır Windows Etkinleştirme hizmeti AppFabric kullanarak da iş akışları için ana bilgisayar uygulamasıdır.  
  
## <a name="hosting-workflows-in-iis-alone"></a>IIS tek başına iş akışlarında barındırma  
 Kullanarak [!INCLUDE[iisver](../../../includes/iisver-md.md)] vardır yönetim ve izleme çalışan uygulamalar bakım kolaylaştırmak AppFabric ile kullanılabilir Araçları tek başına, önerilmez. İş akışları yalnızca barındırılan [!INCLUDE[iisver](../../../includes/iisver-md.md)] AppFabric için taşıma ile altyapı kaygılarınız varsa tek başına.  
  
> [!WARNING]
>  [!INCLUDE[iisver](../../../includes/iisver-md.md)]Uygulama havuzları çeşitli nedenlerle düzenli aralıklarla geri dönüştürür. Bir uygulama havuzu geri dönüştürüldüğünde, IIS eski havuzuna iletileri kabul etmeye durdurur ve yeni isteklerini kabul etmek için yeni bir uygulama havuzu oluşturur. Bir yanıt gönderdikten sonra bir iş akışı çalışmaya devam ederse [!INCLUDE[iisver](../../../includes/iisver-md.md)] gerçekleştirilen çalışmanın haberdar olmaz ve barındırma uygulama havuzu geri. Bu durum, iş akışı iptal edilecek ve Hizmetleri izleme kayıt bir [1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md) boş bir nedenle alan iletisiyle.  
>   
>  Kalıcılık kullanılırsa, konak açıkça son Kalıcılık noktasından durdurulan örnekleri yeniden başlatmanız gerekir.  
>   
>  AppFabric kullanılırsa, Kalıcılık kullanılırsa, iş akışı yönetimi hizmeti sonunda son başarılı Kalıcılık noktasından iş akışı devam eder. İş akışı iptal ettiğinde Kalıcılık değeri kullanılır ve iş akışı bir istek/yanıt desen dışında işlemleri gerçekleştirir, verileri kaybolur.  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Özel bir Windows hizmetinde bir iş akışı barındırma  
 İş akışı barındırmak için özel iş akışı hizmeti oluşturma out-of-box AppFabric tarafından sağlanan işlevleri çok çoğaltmak Geliştirici gerektirir, ancak daha fazla esneklik için özel işlevsellikle izin verir. AppFabric bir seçenek olmadığı durumlarda, bu seçenek yalnızca dikkate alınmalıdır.
