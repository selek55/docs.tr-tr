---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimi İçin Alternatif Satır Stillerini Ayarlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8d78509a7d088511096d2e02e8e6603ba5fe5c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="fc350-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimi İçin Alternatif Satır Stillerini Ayarlama</span><span class="sxs-lookup"><span data-stu-id="fc350-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="fc350-103">Tablo verisi sık sık değişen satırları farklı arka plan renklerini sahip olduğu bir defter benzeri biçiminde sunulur.</span><span class="sxs-lookup"><span data-stu-id="fc350-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="fc350-104">Bu biçim, kullanıcıların her satırda, özellikle çok sayıda sütuna sahip geniş tablolar ile hangi hücrelerin olduğunu bildirir kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="fc350-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="fc350-105">İle <xref:System.Windows.Forms.DataGridView> denetimi satırların değişerek için tam stil bilgilerini belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc350-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="fc350-106">Ön plan rengini ve arka plan rengi, ek olarak yazı tipi gibi stil özellikleri değişen satırları ayırt etmek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc350-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="fc350-107">Daha fazla bilgi için bkz: [Windows Forms DataGridView denetimindeki hücre stilleri](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fc350-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="fc350-108">Aşağıdaki yordam gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="fc350-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fc350-109">Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fc350-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc350-110">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="fc350-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fc350-111">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="fc350-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fc350-112">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fc350-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="fc350-113">Satırların değişerek stilleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="fc350-113">Define styles for alternating rows</span></span>  
  
1.  <span data-ttu-id="fc350-114">Seçin <xref:System.Windows.Forms.DataGridView> Denetim Tasarımcısı'nda.</span><span class="sxs-lookup"><span data-stu-id="fc350-114">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>  
  
2.  <span data-ttu-id="fc350-115">İçinde **özellikleri** penceresinde, üç nokta düğmesini (![VisualStudioEllipsesButton ekran](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) yanındaki <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="fc350-115">In the **Properties** window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>  
  
3.  <span data-ttu-id="fc350-116">İçinde **CellStyle Oluşturucu** iletişim kutusu, stil özellikleri ayarlayarak tanımlama ve kullanma **Önizleme** bölmesinde seçimlerinizi onaylayın.</span><span class="sxs-lookup"><span data-stu-id="fc350-116">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="fc350-117">Belirttiğiniz stilleri ile ikinci bir başlangıç denetiminde görüntülenen her satır için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="fc350-117">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>  
  
4.  <span data-ttu-id="fc350-118">Adım 2 ve 3 kullanarak yineleyin kalan satırlar için stiller tanımlamak için <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="fc350-118">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fc350-119">Hücre stilleri birden çok özelliklerinden devralınan kullanarak görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="fc350-119">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="fc350-120">Stil devralma hakkında daha fazla bilgi için bkz: [Windows Forms DataGridView denetimindeki hücre stilleri](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fc350-120">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc350-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fc350-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="fc350-122">Windows Forms DataGridView denetimindeki hücre stilleri</span><span class="sxs-lookup"><span data-stu-id="fc350-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fc350-123">Temel biçimlendirme ve stil oluşturma Windows Forms DataGridView denetimi</span><span class="sxs-lookup"><span data-stu-id="fc350-123">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fc350-124">Windows Forms DataGridView denetimi ile Tasarımcı kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc350-124">Using the Designer with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fc350-125">Nasıl yapılır: bir Windows uygulaması projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="fc350-125">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="fc350-126">Nasıl yapılır: Windows formlarına denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="fc350-126">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)