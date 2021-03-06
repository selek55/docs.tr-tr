---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
<xref:System.Threading.AutoResetEvent> Sınıfı işaret, tek bir bekleyen iş parçacığı bırakılıyor sonra olduğunda otomatik olarak sıfırlar yerel bekleme tanıtıcısı olayı temsil eder. Bu sınıf temel sınıfı olan özel bir durum gösteren <xref:System.Threading.EventWaitHandle>. Bkz: [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) kullanım ve otomatik sıfırlama olayları özelliklerini kavramsal belgeler.  
  
 Bir <xref:System.Threading.AutoResetEvent> nesne otomatik olarak sıfırlanır çok işaret olmayan sistem tarafından tek bir bekleyen iş parçacığı serbest bırakıldıktan sonra. İş parçacığı bekleyen olay nesnenin durumu iş olarak kalır. <xref:System.Threading.AutoResetEvent>Win32 öğesine karşılık gelen `CreateEvent` çağrısı, belirtme `false` için `bManualReset` bağımsız değişkeni.  
  
 Kullanan bir örnek <xref:System.Threading.AutoResetEvent>, bkz: [İzleyici](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [İş parçacığı oluşturma](../../../docs/standard/threading/index.md)  
 [İş Parçacığı Nesneleri ve Özellikleri](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Bekleme tanıtıcıları](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
