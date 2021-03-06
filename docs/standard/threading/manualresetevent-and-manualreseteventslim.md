---
title: ManualResetEvent ve ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b90a84cf87c6c64d48d89840e2213d83b2e39d44
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a>ManualResetEvent ve ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> Sınıfı işareti verilen sonra el ile sıfırlamanız gerekir bir yerel bekleme tanıtıcısı olayını temsil eder. Bu sınıf temel sınıfı olan özel bir durum gösteren <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>. Bkz: [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) el ile özelliklerini ve kullanmak için kavramsal belgeler sıfırlama olaylar.  
  
 A <xref:System.Threading.ManualResetEvent> nesne kadar iş kalır, <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> yöntemi çağrılır. Nesnenin durumu işaret ederken iş parçacığı veya işaret edilene sonra olayı bekle iş parçacığı bekleniyor, herhangi bir sayı serbest bırakılabilir. <xref:System.Threading.ManualResetEvent>Win32 öğesine karşılık gelen `CreateEvent` çağrısı, belirtme `true` için `bManualReset` bağımsız değişkeni.  
  
 İçinde [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], kullanabileceğiniz <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> bekleme süresini çok kısa olması beklenen ve olay işlem sınır arası değil zamanı daha iyi performans için sınıf. <xref:System.Threading.ManualResetEventSlim>Olay işaret hale beklerken kısa bir süre dönmesini meşgul kullanır. Bekleme süresini kısa, dönen bekleme tanıtıcıları kullanarak bekleme daha çok daha ucuz olabilir. Ancak, olay belirli bir zaman döneminde sinyal hale değil, <xref:System.Threading.ManualResetEventSlim> resorts normal olay işleyici bekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş parçacığı oluşturma](../../../docs/standard/threading/index.md)  
 [İş Parçacığı Nesneleri ve Özellikleri](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Bekleme tanıtıcıları](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Semaphore ve SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
