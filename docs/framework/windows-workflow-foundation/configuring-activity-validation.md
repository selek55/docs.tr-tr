---
title: "Etkinlik doğrulama yapılandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d75f03a9af5caa5569cbfd4d1d09cda8936f6562
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-activity-validation"></a>Etkinlik doğrulama yapılandırma
Etkinlik yazarlar ve kullanıcıları tanımlamak ve hataları yürütülmesinin önce bir etkinliğin yapılandırmasında raporlar etkinlik doğrulamayı etkinleştirir. [!INCLUDE[wf](../../../includes/wf-md.md)]Etkinlik doğrulama aşağıdaki üç türlerini sağlar:  
  
-   `RequiredArgument`ve `OverloadGroup` öznitelikleri.  
  
-   Kesinlik temelli kod tabanlı doğrulama.  
  
-   Bildirim temelli kısıtlamaları.  
  
 `RequiredArgument`ve `OverloadGroup` öznitelikleri gösteren bir etkinlikte bazı bağımsız değişkenler zorunludur. Kesinlik temelli kod tabanlı doğrulama kendisi hakkında doğrulama sağlamak bir etkinlik için basit bir yol sağlar ve doğrulama ve etkinliğini içeren iş akışı ile ilişkisini hakkında bildirim temelli kısıtlamalarını etkinleştirin. Bir etkinlik doğrulama gereksinimlerine göre düzgün şekilde yapılandırılmazsa, doğrulama hataları ve Uyarıları döndürülür. İş Akışı Tasarımcısı'nı kullanarak içeren iş akışı oluşturduysanız, doğrulama hataları ve Uyarıları Tasarımcısı'nda görüntülenir. İş akışını iş akışı Tasarımcısı dışında oluşturulursa, iş akışı çalıştırıldığında herhangi bir doğrulama hatası döndürülür. İş akışının nasıl oluşturulduğuna bakılmaksızın, doğrulama hataları içeren bir iş akışının asla yürütmek için izin verilmez. Bu bölümde, bu tür etkinlik doğrulama ve etkinlik doğrulama nasıl çağrıldığını genel bakış sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Gerekli Bağımsız Değişkenler ve Aşırı Yüklenmiş Gruplar](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 Nasıl kullanılacağını açıklar `RequiredArgument` ve `OverloadGroup` doğrulama sağlamak için öznitelikler.  
  
 [Kesin Kod Temelli Doğrulama](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 Kod tabanlı doğrulama için kullanılacak açıklar <xref:System.Activities.CodeActivity> ve <xref:System.Activities.NativeActivity> etkinlikleri tabanlı.  
  
 [Bildirim Temelli Kısıtlamalar](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 Bildirim temelli kısıtlamaları karmaşık etkinlik doğrulama sağlamak için nasıl kullanılacağını açıklar.  
  
 [Etkinlik Doğrulamayı Çağırma](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 Etkinlik doğrulama otomatik olarak ne zaman çağrılır ve açıkça doğrulamayı çağırmak nasıl anlatılmaktadır.  
  
## <a name="reference"></a>Başvuru  
  
## <a name="related-sections"></a>İlgili Bölümler
