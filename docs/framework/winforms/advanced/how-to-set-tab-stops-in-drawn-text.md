---
title: "Nasıl yapılır: Çizilmiş Metinde Sekme Durakları Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2acc46a9a3fa2c84138cd9a168113f88ab08e4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Nasıl yapılır: Çizilmiş Metinde Sekme Durakları Ayarlama
Çağrılarak metin için sekme durakları ayarlayabilirsiniz <xref:System.Drawing.StringFormat.SetTabStops%2A> yöntemi bir <xref:System.Drawing.StringFormat> nesne ve, geçirme <xref:System.Drawing.StringFormat> nesnesini <xref:System.Drawing.Graphics.DrawString%2A> yöntemi <xref:System.Drawing.Graphics> sınıfı.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Sekmesini durdurur çizilmiş metni varolan sekmesini genişletebilirsiniz rağmen ekleme desteklemediğinden durdurur kullanarak mu <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> bayrağı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, 150, 250 ve 350 sekme durakları ayarlar. Ardından, kod adları ve test puanları sekmeli listesini görüntüler.  
  
 Aşağıdaki çizimde sekmeli metni gösterir.  
  
 ![Yazı tipleri metin](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Aşağıdaki kod iki bağımsız değişken geçirir <xref:System.Drawing.StringFormat.SetTabStops%2A> yöntemi. İkinci bağımsız değişkeni sekmesini uzaklıkları içeren bir dizidir. Geçirilen ilk bağımsız değişken <xref:System.Drawing.StringFormat.SetTabStops%2A> dizideki ilk uzaklığı konumundan 0, sınırlayıcı dikdörtgenini sol kenarı ölçülür gösteren 0 ' dır.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazı Tipleri ve Metin Kullanma](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Nasıl yapılır: GDI ile Metin Çizme](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
