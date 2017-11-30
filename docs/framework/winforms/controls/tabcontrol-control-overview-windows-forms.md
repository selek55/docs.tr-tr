---
title: "TabControl Denetimine Genel Bakış (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 707fb08e487acc8a585e9fe9a246e7485d5e2749
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="a043c-102">TabControl Denetimine Genel Bakış (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a043c-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="a043c-103">Windows Forms <xref:System.Windows.Forms.TabControl> etiketler, bir dosya dolabı klasörlerde kümesi ya da bir not defteri Bölücü gibi birden fazla sekme görüntüler.</span><span class="sxs-lookup"><span data-stu-id="a043c-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="a043c-104">Sekmeleri resimleri ve diğer denetimlerin içerebilir.</span><span class="sxs-lookup"><span data-stu-id="a043c-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="a043c-105">Tür bir Windows işletim sisteminde, Denetim Masası görüntü özellikleri gibi birçok yerde görünür birden çok sayfa iletişim kutusu üretmek için sekme denetimi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a043c-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="a043c-106">Ayrıca, <xref:System.Windows.Forms.TabControl> bir grup ilgili özellik ayarlamak için kullanılan özellik sayfaları oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="a043c-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="a043c-107">TabControl ile çalışma</span><span class="sxs-lookup"><span data-stu-id="a043c-107">Working with TabControl</span></span>  
 <span data-ttu-id="a043c-108">En önemli özelliği, <xref:System.Windows.Forms.TabControl> olan <xref:System.Windows.Forms.TabControl.TabPages%2A>, tek tek sekmeleri içerir.</span><span class="sxs-lookup"><span data-stu-id="a043c-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="a043c-109">Tek tek her sekme bir <xref:System.Windows.Forms.TabPage> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="a043c-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="a043c-110">Sekme tıklatıldığında başlatır <xref:System.Windows.Forms.Control.Click> söz konusu olay <xref:System.Windows.Forms.TabPage> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="a043c-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a043c-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a043c-111">See Also</span></span>  
 <xref:System.Windows.Forms.TabControl>  
 [<span data-ttu-id="a043c-112">TabControl denetimi</span><span class="sxs-lookup"><span data-stu-id="a043c-112">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="a043c-113">Nasıl yapılır: Windows Forms Tabcontrol'nin görünüşünü değiştirme</span><span class="sxs-lookup"><span data-stu-id="a043c-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="a043c-114">Nasıl yapılır: sekme sayfasına denetim ekleme</span><span class="sxs-lookup"><span data-stu-id="a043c-114">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="a043c-115">Nasıl yapılır: Windows Forms TabControl ile sekme ekleme ve kaldırma</span><span class="sxs-lookup"><span data-stu-id="a043c-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="a043c-116">Nasıl yapılır: sekme sayfalarını devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="a043c-116">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="a043c-117">Windows Forms'ta iletişim kutuları</span><span class="sxs-lookup"><span data-stu-id="a043c-117">Dialog Boxes in Windows Forms</span></span>](../../../../docs/framework/winforms/dialog-boxes-in-windows-forms.md)