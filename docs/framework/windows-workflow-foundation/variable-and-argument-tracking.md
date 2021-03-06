---
title: "Değişken ve bağımsız değişkeni izleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0857830b52b2f71df5d81f4bd232b62b894da63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="variable-and-argument-tracking"></a>Değişken ve bağımsız değişkeni izleme
Bir iş akışının yürütülmesini izlerken, genellikle veri ayıklamak kullanışlıdır. Bu, bir izleme kayıt post yürütme erişirken ek bağlam sağlar. İçinde [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], herhangi bir görünür değişkeni veya herhangi bir etkinlik izleme kullanarak bir iş akışı kapsamında bağımsız değişkeni ayıklayabilirsiniz. İzleme profilleri veri ayıklamak kolaylaştırır.  
  
## <a name="variables-and-arguments"></a>Değişkenleri ve bağımsız değişkenler  
 Bir etkinlik bir ActivityStateRecord yayar, değişkenler ve bağımsız değişkenler ayıklanır.  Yalnızca etkinliğin kapsamında ise bir ayıklama için kullanılabilir bir değişkendir. İçinde bir etkinlik ayıklanacak bir değişken, aşağıdaki şekilde belirlenir:  
  
-   Bir değişken değişken adıyla belirtilirse, izlenmekte olan geçerli etkinlik ve üst etkinliklerde değişkeni İzleme arar. Değişken geçerli etkinlik kapsamını ve üst kapsam aranır.  
  
-   Ayıklanacak değişkenleri adını kullanarak belirtilirse = "*", izlenmekte olan geçerli etkinliği tüm değişkenler ayıklandıktan sonra. Bu durumda değişkenleri, kapsamındaki ancak etkinlikler değil ayıklanır üst tanımlı.  
  
 Bağımsız değişkenler çıkarılırken, ayıklanan bağımsız değişkenleri etkinliğin durumuna bağlıdır. Bir etkinlik durumunu olduğunda Executing, ardından yalnızca `InArguments` ayıklama için kullanılabilir. Tüm diğer etkinlik için durumu (kapalı, Faulted, iptal edildi), tüm bağımsız değişkenler, InArguments ve OutArguments, ayıklama için kullanılabilir.  
  
 Aşağıdaki örnek, değişkenler ve bağımsız değişkenler ayıklar bir etkinlik durumu sorgu gösterir, etkinliğin `Closed` izleme kaydı yayılan. Değişkenleri ve bağımsız değişkenler ayıklanan yalnızca bir <xref:System.Activities.Tracking.ActivityStateRecord> ve bu nedenle bir izleme içinde abone olduğunuz kullanarak profil <xref:System.Activities.Tracking.ActivityStateQuery>.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="protecting-information-stored-within-variables-and-arguments"></a>Değişkenleri ve bağımsız değişkenler depolanan bilgileri koruma  
 İzlenen değişken veya değişken WF çalışma zamanı tarafından görünür hale varsayılan olarak açıktır. Bir iş akışı Geliştirici aşağıdaki adımları uygulayarak erişilmesini koruyabilir:  
  
1.  Bir değişkenin değeri olarak şifreleyin.  
  
2.  Bir değişken veya değişken ayıklama önlemek için bir izleme profili yazma denetler.  
  
3.  Özel İzleme katılımcıları WF kod emin olmak için değişkenleri veya bağımsız değişkenler depolanan hassas bilgilerin açığa çıkarmıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Server App Fabric izleme](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [App Fabric ile uygulamaları izleme](http://go.microsoft.com/fwlink/?LinkId=201275)
