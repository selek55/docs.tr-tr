---
title: "Nasıl yapılır: TreeView'ın Performansını Artırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c13a9c89bdcb149df61f26177ea8705e502402f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Nasıl yapılır: TreeView'ın Performansını Artırma
Varsa bir <xref:System.Windows.Controls.TreeView> sayıda öğe içeriyorsa kullanıcı arabiriminde geçen yüklemek için süreyi önemli gecikmeye neden olabilir. Ayarlayarak yükleme süresini artırabilir `VirtualizingStackPanel.IsVirtualizing` özelliğine bağlı `true`.  UI Ayrıca kullanıcı kaydırdığında tepki vermek yavaş olabilir <xref:System.Windows.Controls.TreeView> fare tekerleği kullanarak veya bir kaydırma çubuğu sürükleyerek. Performansını artırabilir <xref:System.Windows.Controls.TreeView> kullanıcı ne zaman kayar ayarlayarak `VirtualizingStackPanel.VirtualizationMode` özelliğine bağlı <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Örnek  
  
## <a name="description"></a>Açıklama  
Aşağıdaki örnekte bir <xref:System.Windows.Controls.TreeView> ayarlayan `VirtualizingStackPanel.IsVirtualizing` özelliği true olarak eklenmiş ve `VirtualizingStackPanel.VirtualizationMode` özelliğine bağlı <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> performansı iyileştirmek için.  
  
## <a name="code"></a>Kod  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Aşağıdaki örnek, önceki örnekte kullandığı verileri gösterir.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimler](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
