---
title: "Nasıl yapılır: Bir Görevi ve Alt Öğelerini İptal Etme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to cancel
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecccd5ddd3ff662b03ae7078aabaf58e397f7003
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-cancel-a-task-and-its-children"></a>Nasıl yapılır: Bir Görevi ve Alt Öğelerini İptal Etme
Bu örnekler, aşağıdaki görevlerin nasıl gerçekleştirildiğini gösterir:  
  
1.  İptal edilebilen bir görevi oluşturmak ve başlatmak.  
  
2.  Kullanıcı temsilcinize ve isteğe bağlı olarak görev örneğine bir iptal belirteci geçirmek.  
  
3.  Kullanıcı temsilcinizde iptal belirtecini fark etmek ve buna yanıt vermek.  
  
4.  İsteğe bağlı olarak, çağıran iş parçacığında görevin iptal edildiğini belirlemek.  
  
 Çağıran iş parçacığı görevi zorla bitirmez; yalnızca iptalin istendiğini bildirir. Görev zaten çalışıyorsa, isteği fark etmek ve uygun bir şekilde karşılık vermek kullanıcı temsilcisinin görevidir. Görev çalışmadan iptal istenirse, kullanıcı temsilcisi asla yürütülmez ve görev nesnesi Canceled durumuna geçer.  
  
## <a name="example"></a>Örnek  
 Bu örnek, bir iptal isteğine yanıt olarak bir <xref:System.Threading.Tasks.Task> öğesinin ve alt öğelerinin nasıl sonlandırıldığını gösterir. Ayrıca, kullanıcı temsilcisi bir <xref:System.Threading.Tasks.TaskCanceledException> oluşturarak sonlandırdığında, çağıran iş parçacığının, isteğe bağlı olarak, görevlerin bitmesini beklemek için <xref:System.Threading.Tasks.Task.Wait%2A> yöntemini veya <xref:System.Threading.Tasks.Task.WaitAll%2A> yöntemini kullanabileceğini de gösterir. Bu durumda, özel durumları işlemek için çağıran iş parçacığında bir `try/catch` bloğu kullanmanız gerekir.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> sınıfı, <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType> ve <xref:System.Threading.CancellationToken?displayProperty=nameWithType> türlerini temel alan iptal modeliyle tamamen tümleşiktir. Daha fazla bilgi için bkz: [yönetilen iş parçacıklarında iptal](../../../docs/standard/threading/cancellation-in-managed-threads.md) ve [görev iptali](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.CancellationTokenSource?displayProperty=nameWithType>  
 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>  
 <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>  
 [Görev Tabanlı Zaman Uyumsuz Desen](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)  
 [Eklenen ve Ayrılan Alt Görevler](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)  
 [PLINQ ve TPL'deki Lambda İfadeleri](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
