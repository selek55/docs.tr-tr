---
title: "Nasıl yapılır: Windows Forms DataGridView Denetiminde Veri Biçimlendirmeyi Özelleştirme"
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
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f404d7483cb4a91908b9a578c97190f11b6d0767
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a>Nasıl yapılır: Windows Forms DataGridView Denetiminde Veri Biçimlendirmeyi Özelleştirme
Aşağıdaki kod örneği için bir işleyici uygulamak gösterilmiştir <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> hücreleri kendi sütunlar ve değerler bağlı olarak nasıl görüntüleneceğini değiştiren olay.  
  
 İçinde hücreleri `Balance` negatif sayıları içeren sütun kırmızı bir arka plan verilmiştir. Bu hücreler, negatif değerler parantezler görüntülenecek para birimi olarak da biçimlendirebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Windows Forms DataGridView denetiminde veri biçimlendirme](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
 İçinde hücreleri `Priority` metinsel karşılık gelen yerine sütun ekran görüntüleri hücre değerleri. <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> Özelliği <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> metinsel hücre değerini almak ve karşılık gelen görüntü görüntüleme değeri ayarlamak için kullanılır.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem, System.Drawing ve System.Windows.Forms derlemelerine başvurular.  
  
-   <xref:System.Drawing.Bitmap>Adlandırılmış resimler `highPri.bmp`, `mediumPri.bmp`, ve `lowPri.bmp` yürütülebilir dosya ile aynı dizinde bulunan.  
  
 Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.  Ayrıca bkz. [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Drawing.Bitmap>  
 [Windows Forms DataGridView Denetiminde Verileri Görüntüleme](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Nasıl yapılır: Windows Forms DataGridView Denetiminde Verileri Biçimlendirme](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView Denetimindeki Hücre Stilleri](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Windows Forms DataGridView Denetiminde Veri Biçimlendirme](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
