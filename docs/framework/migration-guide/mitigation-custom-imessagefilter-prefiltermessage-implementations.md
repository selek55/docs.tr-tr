---
title: "Azaltma: Özel IMessageFilter.PreFilterMessage uygulamaları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13b8fffdbab44d3bbbce8f1ed9ce0250dd892f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="3a166-102">Azaltma: Özel IMessageFilter.PreFilterMessage uygulamaları</span><span class="sxs-lookup"><span data-stu-id="3a166-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>
<span data-ttu-id="3a166-103">.NET Framework başlayarak sürümlerini hedefleyen Windows Forms uygulamalarında [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], özel bir <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> uygulaması için güvenli bir şekilde filtre iletileri <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> varsa yöntemi çağrıldığında <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> uygulama:</span><span class="sxs-lookup"><span data-stu-id="3a166-103">In Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>  
  
-   <span data-ttu-id="3a166-104">Birini veya her ikisini aşağıdakileri yapar:</span><span class="sxs-lookup"><span data-stu-id="3a166-104">Does one or both of the following:</span></span>  
  
    -   <span data-ttu-id="3a166-105">Bir ileti filtresi çağırarak ekler <xref:System.Windows.Forms.Application.AddMessageFilter%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3a166-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>  
  
    -   <span data-ttu-id="3a166-106">Bir ileti filtresi çağırarak kaldırır <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3a166-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="3a166-107">yöntem.</span><span class="sxs-lookup"><span data-stu-id="3a166-107">method.</span></span>  
  
-   <span data-ttu-id="3a166-108">**Ve** Pompalar iletileri çağırarak <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="3a166-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3a166-109">Etki</span><span class="sxs-lookup"><span data-stu-id="3a166-109">Impact</span></span>  
 <span data-ttu-id="3a166-110">Bu değişiklik, yalnızca .NET Framework başlayarak sürümlerini hedefleyen Windows Forms uygulamaları etkiler [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a166-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="3a166-111">.NET Framework'ün önceki sürümlerini hedefleyen Windows Forms uygulamaları için bazı durumlarda bu tür uygulamalar throw bir <xref:System.IndexOutOfRangeException> özel durumu zaman <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> yöntemi çağrılır</span><span class="sxs-lookup"><span data-stu-id="3a166-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="3a166-112">Azaltma</span><span class="sxs-lookup"><span data-stu-id="3a166-112">Mitigation</span></span>  
 <span data-ttu-id="3a166-113">Bu değişiklik istenmeyen ise, uygulamalar, hedef [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] veya sonraki bir sürümünü şu yapılandırma ayarı ekleyerek onu dışında tercih edebilirsiniz [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) uygulamanın yapılandırma dosyasının:</span><span class="sxs-lookup"><span data-stu-id="3a166-113">If this change is undesirable, apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 <span data-ttu-id="3a166-114">Buna ek olarak, .NET Framework'ün önceki sürümlerini hedefleyen ancak altında çalışan uygulamalar [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] veya sonraki bir sürümünü de bu davranış için şu yapılandırma ayarı ekleyerek seçebilirsiniz [ \<çalışma zamanı >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)uygulamanın yapılandırma dosyasının:</span><span class="sxs-lookup"><span data-stu-id="3a166-114">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a166-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3a166-115">See Also</span></span>  
 [<span data-ttu-id="3a166-116">Yeniden hedefleme değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="3a166-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)