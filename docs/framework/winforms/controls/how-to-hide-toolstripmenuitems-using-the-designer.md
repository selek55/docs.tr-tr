---
title: "Nasıl yapılır: Tasarımcıyı Kullanarak ToolStripMenuItems Öğelerini Gizleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="b2157-102">Nasıl yapılır: Tasarımcıyı Kullanarak ToolStripMenuItems Öğelerini Gizleme</span><span class="sxs-lookup"><span data-stu-id="b2157-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="b2157-103">Menü öğelerini gizleme, uygulamanızın kullanıcı arabirimi (UI) denetlemek ve kullanıcı komutları kısıtlamak için bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="b2157-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="b2157-104">Genellikle, tüm menü öğeleri kullanılamaz duruma geldiğinde tüm menüyü Gizle isteyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b2157-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="b2157-105">Bu kullanıcı için daha az karışıklıkları gösterir.</span><span class="sxs-lookup"><span data-stu-id="b2157-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="b2157-106">Ayrıca, tek başına bir gizleme kullanıcı bir kısayol tuşu kullanarak menü komutu erişmesini engellemez gibi Gizle hem menüsü veya menü öğesini devre dışı bırakmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b2157-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="b2157-107">Menü öğelerini devre dışı bırakma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Toolstripmenuıtems kullanarak Tasarımcısı'nı devre dışı](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b2157-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2157-108">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="b2157-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b2157-109">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="b2157-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b2157-110">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b2157-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="b2157-111">En üst düzey menü ve onun alt menü öğelerini gizleme</span><span class="sxs-lookup"><span data-stu-id="b2157-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="b2157-112">Üst düzey menü öğesini seçin ve ayarlayın, <xref:System.Windows.Forms.ToolStripItem.Visible%2A> veya <xref:System.Windows.Forms.ToolStripItem.Available%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="b2157-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="b2157-113">Üst düzey menü öğesini gizlemek menüye içindeki tüm menü öğelerini de gizlidir.</span><span class="sxs-lookup"><span data-stu-id="b2157-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="b2157-114">Dışındaki bir üzerinde tıklatırsanız <xref:System.Windows.Forms.MenuStrip> ayarlanmasından sonra <xref:System.Windows.Forms.ToolStripItem.Visible%2A> için `false`, böylece eyleminizi çalışma zamanı etkisini gösteren formdan, tüm üst düzey menü öğesi ve kendi alt öğelerini kaybolur.</span><span class="sxs-lookup"><span data-stu-id="b2157-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="b2157-115">Tasarım zamanında gizli en üst düzey menü öğesini görüntülemek için tıklatın <xref:System.Windows.Forms.MenuStrip> içinde **bileşen**, **belge anahattı**, ya da özellik Kılavuzu üstünde.</span><span class="sxs-lookup"><span data-stu-id="b2157-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2157-116">Birden çok belge arabirimi (MDI) alt menüler birleştirme senaryosunda hariç tüm bir menü nadiren gizlenir.</span><span class="sxs-lookup"><span data-stu-id="b2157-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="b2157-117">Alt menü öğesini gizlemek için</span><span class="sxs-lookup"><span data-stu-id="b2157-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="b2157-118">Alt menü öğesini seçin ve ayarlayın, <xref:System.Windows.Forms.ToolStripItem.Visible%2A> özelliğine `false`.</span><span class="sxs-lookup"><span data-stu-id="b2157-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="b2157-119">Alt menü öğesini gizlemek, bunu kolayca için daha fazla iş seçebilmeniz tasarım zamanında formunuzda görünür kalır.</span><span class="sxs-lookup"><span data-stu-id="b2157-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="b2157-120">Çalışma zamanında gerçekten gizlenir.</span><span class="sxs-lookup"><span data-stu-id="b2157-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2157-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b2157-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="b2157-122">MenuStrip denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="b2157-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="b2157-123">Nasıl yapılır: tasarımcıyı kullanarak toolstripmenuıtems öğelerini devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="b2157-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)