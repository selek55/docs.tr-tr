---
title: "Nasıl yapılır: Yerelleştirmeye İyi Cevap Veren Bir Windows Forms Düzeni Tasarlama"
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
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 072d0694b3e92d9bf4bd8d0cf118b2f4af024af6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Nasıl yapılır: Yerelleştirmeye İyi Cevap Veren Bir Windows Forms Düzeni Tasarlama
Olması hazırsınız formları oluşturma hızları geliştirme uluslararası pazarda için büyük ölçüde yerelleştirilmiş. Kullanabileceğiniz <xref:System.Windows.Forms.TableLayoutPanel> değişiklikleri nedeniyle denetimlerinin boyutunu değiştirme gibi düzgün bir şekilde yanıt düzenleri uygulamak için denetim kendi <xref:System.Windows.Forms.Control.Text%2A> özellik değerleri.  
  
## <a name="example"></a>Örnek  
 Bu form nasıl görüntülenen dize değerlerini diğer dillere çevirme yükleyen orantılı olarak ayarlayan bir düzen oluşturulacağını gösterir. Çevirisi, bu işlem çağrılırken *yerelleştirme*. Daha fazla bilgi için bkz: [yerelleştirme](../../../../docs/standard/globalization-localization/localization.md).  
  
 Visual Studio'da bu görev için kapsamlı destek yoktur.  Ayrıca bkz. [izlenecek yol: bir düzen oluşturma oranda yerelleştirme için ayarlar](http://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [Nasıl yapılır: TableLayoutPanel Denetiminde Bir Denetimi Hizalama ve Uzatma](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))  
  
2.  [İzlenecek yol: FlowLayoutPanel Kullanarak Windows Forms'da Denetimleri Düzenleme](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))  
  
3.  [Nasıl yapılır: Bir TableLayoutPanel Denetimindeki Satırları ve Sütunları Yayma](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))  
  
4.  [Nasıl yapılır: Bir TableLayoutPanel Denetimindeki Satırları ve Sütunları Düzenleme](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))  
  
5.  [İzlenecek yol: Windows Forms Denetimlerindeki Akıllı Etiketleri Kullanarak Ortak Görevleri Gerçekleştirme](http://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))  
  
6.  [İzlenecek yol: TableLayoutPanel Kullanarak Windows Forms'da Denetimleri Düzenleme](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))  
  
7.  [İzlenecek yol: Doldurma, Kenar Boşlukları ve AutoSize Özelliği ile Windows Forms Denetimlerini Düzenleme](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))  
  
8.  [Nasıl yapılır: AutoSize ve TableLayoutPanel denetimi kullanarak Windows Forms'ta yerelleştirme desteği](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))  
  
9. [İzlenecek yol: veri girişi için yeniden boyutlandırılabilir Windows formu oluşturma](http://msdn.microsoft.com/library/991eahec\(v=vs.110\))  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek gerektirir:  
  
-   Sistem, System.Data, System.Drawing ve System.Windows.Forms derlemelerine başvurular.  
  
 Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.  Ayrıca bkz. [nasıl yapılır: derleme ve çalıştırma bir tam Windows Forms kod örneği kullanarak Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 [Yerelleştirme](../../../../docs/standard/globalization-localization/localization.md)
