---
title: "Nasıl yapılır: Windows Forms DataGridView Denetiminde Yazı Tipi ve Renk Stillerini Ayarlama"
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
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb1c15be20775903a6fb7674660c552c464daab1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="efbde-102">Nasıl yapılır: Windows Forms DataGridView Denetiminde Yazı Tipi ve Renk Stillerini Ayarlama</span><span class="sxs-lookup"><span data-stu-id="efbde-102">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="efbde-103">Hücrelerde görsel görünümünü belirtebilirsiniz bir <xref:System.Windows.Forms.DataGridView> özelliklerini ayarlayarak denetim <xref:System.Windows.Forms.DataGridViewCellStyle> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="efbde-103">You can specify the visual appearance of cells within a <xref:System.Windows.Forms.DataGridView> control by setting properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="efbde-104">Bu sınıfın örnekleri, çeşitli özelliklerinden almak <xref:System.Windows.Forms.DataGridView> sınıf ve bunun yardımcı sınıfları veya örneği <xref:System.Windows.Forms.DataGridViewCellStyle> nesneleri atama için bu özellikleri.</span><span class="sxs-lookup"><span data-stu-id="efbde-104">You can retrieve instances of this class from various properties of the <xref:System.Windows.Forms.DataGridView> class and its companion classes, or you can instantiate <xref:System.Windows.Forms.DataGridViewCellStyle> objects for assignment to these properties.</span></span>  
  
 <span data-ttu-id="efbde-105">Aşağıdaki yordamlar hücre görünümünü kullanarak temel özelleştirme göstermektedir <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="efbde-105">The following procedures demonstrate basic customization of cell appearance using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="efbde-106">Her hücre denetimindeki sütun, satır veya hücre düzeyinde geçersiz kılınmadığı sürece bu özelliği üzerinden belirtilen stillerini devralır.</span><span class="sxs-lookup"><span data-stu-id="efbde-106">Every cell in the control inherits the styles specified through this property unless they are overridden at the column, row, or cell level.</span></span> <span data-ttu-id="efbde-107">Stil devralma örneği için bkz: [nasıl yapılır: ayarlama varsayılan hücre stilleri Windows Forms DataGridView denetimi için](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="efbde-107">For an example of style inheritance, see [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="efbde-108">Ek kullanımlarını hakkında bilgi için <xref:System.Windows.Forms.DataGridViewCellStyle> sınıfı, ayrıca bkz. bölümünde listelenen konulara bakın.</span><span class="sxs-lookup"><span data-stu-id="efbde-108">For information about additional uses of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="efbde-109">Visual Studio'da bu görev için kapsamlı destek yoktur.</span><span class="sxs-lookup"><span data-stu-id="efbde-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="efbde-110">Ayrıca bkz. [nasıl yapılır: varsayılan hücre stillerini ayarlama ve veri biçimleri Windows Forms DataGridView denetimi kullanan bir tasarımcı](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="efbde-110">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span></span>  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a><span data-ttu-id="efbde-111">DataGridView hücrelerinde tarafından kullanılan yazı tipini belirtmek için</span><span class="sxs-lookup"><span data-stu-id="efbde-111">To specify the font used by DataGridView cells</span></span>  
  
-   <span data-ttu-id="efbde-112">Ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> özelliği bir <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="efbde-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="efbde-113">Aşağıdaki kod örneğinde <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> tüm denetimi için yazı tipini ayarlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="efbde-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the font for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a><span data-ttu-id="efbde-114">DataGridView hücrelerinin ön ve arka plan renklerini belirtmek için</span><span class="sxs-lookup"><span data-stu-id="efbde-114">To specify the foreground and background colors of DataGridView cells</span></span>  
  
-   <span data-ttu-id="efbde-115">Ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> ve <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> özelliklerini bir <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="efbde-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="efbde-116">Aşağıdaki kod örneğinde <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> bu stiller tüm denetim için ayarlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="efbde-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a><span data-ttu-id="efbde-117">Seçili DataGridView hücrelerinin ön ve arka plan renklerini belirtmek için</span><span class="sxs-lookup"><span data-stu-id="efbde-117">To specify the foreground and background colors of selected DataGridView cells</span></span>  
  
-   <span data-ttu-id="efbde-118">Ayarlama <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> ve <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> özelliklerini bir <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="efbde-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="efbde-119">Aşağıdaki kod örneğinde <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> bu stiller tüm denetim için ayarlamak için özellik.</span><span class="sxs-lookup"><span data-stu-id="efbde-119">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a><span data-ttu-id="efbde-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="efbde-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="efbde-121">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="efbde-121">Compiling the Code</span></span>  
 <span data-ttu-id="efbde-122">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="efbde-122">This example requires:</span></span>  
  
-   <span data-ttu-id="efbde-123">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="efbde-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="efbde-124">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, ve <xref:System.Windows.Forms?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="efbde-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="efbde-125">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="efbde-125">Robust Programming</span></span>  
 <span data-ttu-id="efbde-126">En yüksek ölçeklenebilirlik için paylaşması gerekir <xref:System.Windows.Forms.DataGridViewCellStyle> birden çok satırları, sütunları veya ayrı ayrı her öğe için stil özelliklerini ayarlama yerine aynı stilleri kullanın hücreleri nesneleri.</span><span class="sxs-lookup"><span data-stu-id="efbde-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="efbde-127">Daha fazla bilgi için bkz: [Windows Forms DataGridView denetimini ölçeklendirme için en iyi yöntemler](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="efbde-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efbde-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="efbde-128">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="efbde-129">Temel biçimlendirme ve stil oluşturma Windows Forms DataGridView denetimi</span><span class="sxs-lookup"><span data-stu-id="efbde-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="efbde-130">Windows Forms DataGridView denetimindeki hücre stilleri</span><span class="sxs-lookup"><span data-stu-id="efbde-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)