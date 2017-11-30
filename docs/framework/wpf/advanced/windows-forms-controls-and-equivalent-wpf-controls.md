---
title: "Windows Forms Denetimleri ve Eşdeğer WPF Denetimleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fae33ee8744936f3152ef991715853028063066
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="3d52c-102">Windows Forms Denetimleri ve Eşdeğer WPF Denetimleri</span><span class="sxs-lookup"><span data-stu-id="3d52c-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="3d52c-103">Birçok [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleriniz eşdeğer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denetimleri, ancak bazı [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri olmayan eşdeğerleri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d52c-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="3d52c-104">Bu konu iki teknoloji tarafından sağlanan denetim türlerini karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="3d52c-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="3d52c-105">Birlikte çalışabilirlik barındırmak için her zaman kullanabilirsiniz [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] eşdeğerleri olmayan denetimler, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-tabanlı uygulamaları.</span><span class="sxs-lookup"><span data-stu-id="3d52c-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="3d52c-106">Aşağıdaki tabloda gösterir [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denetimleri ve bileşenleri sahip eşdeğer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denetim işlevi.</span><span class="sxs-lookup"><span data-stu-id="3d52c-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="3d52c-107">Windows Forms denetimi</span><span class="sxs-lookup"><span data-stu-id="3d52c-107">Windows Forms control</span></span>|<span data-ttu-id="3d52c-108">WPF eşdeğer denetimi</span><span class="sxs-lookup"><span data-stu-id="3d52c-108">WPF equivalent control</span></span>|<span data-ttu-id="3d52c-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3d52c-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="3d52c-110">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="3d52c-111"><xref:System.Windows.Controls.ListBox>ile oluşturma.</span><span class="sxs-lookup"><span data-stu-id="3d52c-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="3d52c-112">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="3d52c-113"><xref:System.Windows.Controls.ComboBox>Otomatik Tamamlama desteklemez.</span><span class="sxs-lookup"><span data-stu-id="3d52c-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="3d52c-114"><xref:System.Windows.Controls.TextBox>ve iki <xref:System.Windows.Controls.Primitives.RepeatButton> denetimleri.</span><span class="sxs-lookup"><span data-stu-id="3d52c-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="3d52c-115">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="3d52c-116"><xref:System.Windows.Controls.WrapPanel>veya<xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="3d52c-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="3d52c-117">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="3d52c-118">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="3d52c-119"><xref:System.Windows.Window>alt öğe pencerelerini desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="3d52c-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="3d52c-120">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-120">No equivalent control.</span></span>|<span data-ttu-id="3d52c-121">F1 Yardımı yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-121">No F1 Help.</span></span> <span data-ttu-id="3d52c-122">"Bu nedir" Yardım araç ipuçları tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="3d52c-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="3d52c-123">Kaydırma kapsayıcı denetimlere yerleşik olarak bulunur.</span><span class="sxs-lookup"><span data-stu-id="3d52c-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="3d52c-124">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="3d52c-125">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-125">No equivalent control.</span></span>|<span data-ttu-id="3d52c-126">Kullanabileceğiniz <xref:System.Windows.Documents.Hyperlink> köprüler akış içeriği barındırmanıza sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3d52c-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="3d52c-127"><xref:System.Windows.Controls.ListView> Denetimi salt okunur Ayrıntılar görünümü sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d52c-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="3d52c-128">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="3d52c-129"><xref:System.Windows.Controls.Menu>denetim stil yaklaşık davranış ve görünümünü <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="3d52c-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="3d52c-130">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="3d52c-131"><xref:System.Windows.Controls.TextBox>ve iki <xref:System.Windows.Controls.Primitives.RepeatButton> denetimleri.</span><span class="sxs-lookup"><span data-stu-id="3d52c-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="3d52c-132"><xref:Microsoft.Win32.OpenFileDialog> Sınıfı bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] çevresinde sarmalayıcı [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] denetim.</span><span class="sxs-lookup"><span data-stu-id="3d52c-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="3d52c-133">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="3d52c-134">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="3d52c-135">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="3d52c-136">Eşdeğer denetimi yok.</span><span class="sxs-lookup"><span data-stu-id="3d52c-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="3d52c-137"><xref:Microsoft.Win32.SaveFileDialog> Sınıfı bir [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] çevresinde sarmalayıcı [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] denetim.</span><span class="sxs-lookup"><span data-stu-id="3d52c-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="3d52c-138"><xref:System.Windows.Controls.ToolBar>ile oluşturma.</span><span class="sxs-lookup"><span data-stu-id="3d52c-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="3d52c-139"><xref:System.Windows.Controls.ToolBar>ile oluşturma.</span><span class="sxs-lookup"><span data-stu-id="3d52c-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="3d52c-140"><xref:System.Windows.Controls.ToolBar>ile oluşturma.</span><span class="sxs-lookup"><span data-stu-id="3d52c-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="3d52c-141"><xref:System.Windows.Controls.ToolBar>ile oluşturma.</span><span class="sxs-lookup"><span data-stu-id="3d52c-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="3d52c-142">Kaydırma kapsayıcı denetimlere yerleşik olarak bulunur.</span><span class="sxs-lookup"><span data-stu-id="3d52c-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="3d52c-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3d52c-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="3d52c-144"><xref:System.Windows.Controls.Frame> Denetimi HTML sayfalarını barındırabilir.</span><span class="sxs-lookup"><span data-stu-id="3d52c-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="3d52c-145">İtibariyle [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> denetim HTML sayfaları ve de geri barındırabilir <xref:System.Windows.Controls.Frame> denetim.</span><span class="sxs-lookup"><span data-stu-id="3d52c-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d52c-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3d52c-146">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="3d52c-147">Windows için WPF Tasarımcısı geliştiriciler formlar</span><span class="sxs-lookup"><span data-stu-id="3d52c-147">WPF Designer for Windows Forms Developers</span></span>](http://msdn.microsoft.com/en-us/47ad0909-e89b-4996-b4ac-874d929f94ca)  
 [<span data-ttu-id="3d52c-148">İzlenecek yol: WPF bir Windows Forms denetimi barındırma</span><span class="sxs-lookup"><span data-stu-id="3d52c-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="3d52c-149">İzlenecek yol: Windows Forms içerisinde WPF bileşik denetimi barındırma</span><span class="sxs-lookup"><span data-stu-id="3d52c-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="3d52c-150">Geçiş ve birlikte çalışabilirlik</span><span class="sxs-lookup"><span data-stu-id="3d52c-150">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)