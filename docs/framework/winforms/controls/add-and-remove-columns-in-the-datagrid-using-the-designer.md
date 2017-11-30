---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimine Sütunlar Ekleme ve Kaldırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71b02124dd68299552737df35163e3b766d4df73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="6cf0e-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGridView Denetimine Sütunlar Ekleme ve Kaldırma</span><span class="sxs-lookup"><span data-stu-id="6cf0e-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="6cf0e-103">Windows Forms <xref:System.Windows.Forms.DataGridView> denetim verileri görüntülemek için sütunları içermelidir.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="6cf0e-104">Denetimi el ile doldurmak planlıyorsanız, kendiniz sütunları eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="6cf0e-105">Alternatif olarak, denetim oluşturur ve sütunları otomatik olarak dolduran bir veri kaynağına bağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="6cf0e-106">Veri kaynağını görüntülemek istediğiniz daha fazla sütun içeriyorsa, istenmeyen sütunları kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="6cf0e-107">Aşağıdaki yordamlar gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.DataGridView> denetim.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6cf0e-108">Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6cf0e-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cf0e-109">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6cf0e-110">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6cf0e-111">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="6cf0e-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="6cf0e-112">Tasarımcı kullanarak bir sütun eklemek için</span><span class="sxs-lookup"><span data-stu-id="6cf0e-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="6cf0e-113">Akıllı etiket karakteri tıklayın (![akıllı etiket karakteri](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) sağ üst köşesindeki <xref:System.Windows.Forms.DataGridView> denetlemek ve ardından **Sütun Ekle**.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="6cf0e-114">İçinde **Sütun Ekle** iletişim kutusunda, seçin **veriye bağlı sütun** seçeneği ve veri kaynağından bir sütun seçin ya da seçin **bağlantısız sütun** seçeneği ve sütun tanımlayın Sağlanan alanları kullanma.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="6cf0e-115">Tıklatın **Ekle** varolan sütunlar denetim görüntüleme alanı zaten doldurmuyorsa Tasarımcısı'nda görüntülenmesine neden sütun eklemek için düğmesi.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6cf0e-116">Sütun özelliklerinde değişiklik yapabilirsiniz **Edit Columns** iletişim kutusu, denetimin akıllı etiketten erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="6cf0e-117">Tasarımcı kullanarak bir sütunu kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="6cf0e-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="6cf0e-118">Seçin **Edit Columns** denetimin akıllı etiket gelen.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="6cf0e-119">Bir sütun seçin **seçili sütun** listesi.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="6cf0e-120">Tıklatın **kaldırmak** Tasarımcısı'ndan kayboluyor kendisine neden sütunu silmek için düğmesi.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cf0e-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6cf0e-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="6cf0e-122">Nasıl yapılır: bir Windows uygulaması projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="6cf0e-122">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="6cf0e-123">Nasıl yapılır: Windows formlarına denetimler ekleme</span><span class="sxs-lookup"><span data-stu-id="6cf0e-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)