---
title: "Nasıl yapılır: Yüklü Yazı Tiplerini Numaralandırma"
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905b5ecbda58d2f7edb7fc30d5505eec63a64c2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a>Nasıl yapılır: Yüklü Yazı Tiplerini Numaralandırma
<xref:System.Drawing.Text.InstalledFontCollection> Sınıfının devraldığı <xref:System.Drawing.Text.FontCollection> soyut taban sınıfı. Kullanabileceğiniz bir <xref:System.Drawing.Text.InstalledFontCollection> bilgisayarda yüklü yazı tiplerini numaralandırma nesnesi. <xref:System.Drawing.Text.FontCollection.Families%2A> Özelliği bir <xref:System.Drawing.Text.InstalledFontCollection> nesnesi olan bir dizi <xref:System.Drawing.FontFamily> nesneleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bilgisayarda yüklü tüm yazı tipi aileleri adlarını listeler. Kodu alır <xref:System.Drawing.FontFamily.Name%2A> her özellik <xref:System.Drawing.FontFamily> nesnesi tarafından döndürülen dizideki <xref:System.Drawing.Text.FontCollection.Families%2A> özelliği. Aile adları alınır gibi bunlar için form virgülle ayrılmış listesini birleşir. Ardından <xref:System.Drawing.Graphics.DrawString%2A> yöntemi <xref:System.Drawing.Graphics> dikdörtgene sınıfı çizer virgülle ayrılmış listesi.  
  
 Kod örneği çalıştırırsanız, çıktı aşağıdaki çizimde gösterilen benzer olacaktır.  
  
 ![Yazı tipleri yüklü](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.PaintEventHandler>. Ayrıca, almalısınız <xref:System.Drawing.Text> ad alanı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazı Tipleri ve Metin Kullanma](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
