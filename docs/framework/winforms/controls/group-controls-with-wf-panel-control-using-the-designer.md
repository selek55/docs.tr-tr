---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Panel Denetimi ile Denetimleri Gruplandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c6dd45d2070c77b34c66388b397bb784215654
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Nasıl yapılır: Tasarımcı Kullanarak Windows Formları Panel Denetimi ile Denetimleri Gruplandırma
Windows Forms <xref:System.Windows.Forms.Panel> denetimleri, diğer denetimler gruplandırmak için kullanılır. Denetimleri gruplandırma için üç nedeni vardır. Clear kullanıcı arabirimi için ilgili form öğeleri gruplandırma visual biridir; başka bir program, radyo düğmeleri örneğin gruplandırmadır; Son denetimler bir birim olarak tasarım zamanında taşımak için ' dir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-group-of-controls"></a>Denetimlerin bir grup oluşturmak için  
  
1.  Sürükleme bir <xref:System.Windows.Forms.Panel> gelen denetim **Windows Forms** forma araç sekmesinde.  
  
2.  Her içinde bölmenin çizim paneli, diğer denetimler ekleyin.  
  
     Masası'nda eklemek istediğiniz varolan denetimleri varsa, tüm denetimler seçin, select panoya Kes <xref:System.Windows.Forms.Panel> denetleyen ve bunları paneline yapıştırın. Ayrıca bunları paneline sürükleyebilirsiniz.  
  
3.  (İsteğe bağlı) Kenarlık Masası'na eklemek istiyorsanız, kendi <xref:System.Windows.Forms.BorderStyle> özelliği. Üç seçenek vardır: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, ve <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Panel Denetimi](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Nasıl yapılır: Bir Panelin Arka Planını Ayarlama](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
