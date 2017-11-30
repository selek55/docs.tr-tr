---
title: "Nasıl yapılır: Anahatlı Şekil Çizme"
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
- cpp
f1_keywords: Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 05247d24f3db95d042cb4ac34ec6ed648ec1d997
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="0b5f5-102">Nasıl yapılır: Anahatlı Şekil Çizme</span><span class="sxs-lookup"><span data-stu-id="0b5f5-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="0b5f5-103">Bu örnek, bir form üzerinde anahatları belirlenmiş elipsler ve dikdörtgenler çizer.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b5f5-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="0b5f5-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b5f5-105">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="0b5f5-105">Compiling the Code</span></span>  
 <span data-ttu-id="0b5f5-106">Bu yöntem çağıramazsınız <xref:System.Windows.Forms.Form.Load> olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="0b5f5-107">Formu yeniden boyutlandırılmış veya başka bir form tarafından getirilmemeli çizilmiş içeriği yeniden değil.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="0b5f5-108">İçeriğinizi otomatik olarak yeniden boyamak yapmak için geçersiz kılmalıdır <xref:System.Windows.Forms.Control.OnPaint%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0b5f5-109">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="0b5f5-109">Robust Programming</span></span>  
 <span data-ttu-id="0b5f5-110">Her zaman çağırmalıdır <xref:System.IDisposable.Dispose%2A> sistem kaynakları gibi kullanabilecek tüm nesneler üzerinde <xref:System.Drawing.Pen> ve <xref:System.Drawing.Graphics> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b5f5-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>  
 [<span data-ttu-id="0b5f5-112">Grafik programlamaya Başlarken</span><span class="sxs-lookup"><span data-stu-id="0b5f5-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="0b5f5-113">Çizgiler ve şekiller çizmek için kalem kullanma</span><span class="sxs-lookup"><span data-stu-id="0b5f5-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="0b5f5-114">Grafikler ve Windows Forms'ta çizme</span><span class="sxs-lookup"><span data-stu-id="0b5f5-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)