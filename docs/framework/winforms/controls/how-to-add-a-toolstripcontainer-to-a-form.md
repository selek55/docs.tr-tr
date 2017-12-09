---
title: "Nasıl yapılır: Forma ToolStripContainer Ekleme"
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
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a4089bc6f8ded2c2856318d11b8277811d118c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a><span data-ttu-id="a8bda-102">Nasıl yapılır: Forma ToolStripContainer Ekleme</span><span class="sxs-lookup"><span data-stu-id="a8bda-102">How to: Add a ToolStripContainer to a Form</span></span>
<span data-ttu-id="a8bda-103">Program aracılığıyla ekleyebilirsiniz bir <xref:System.Windows.Forms.ToolStripContainer> Windows Form için ve denetimleri ile doldurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a8bda-103">You can programmatically add a <xref:System.Windows.Forms.ToolStripContainer> to a Windows Form and populate it with controls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8bda-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="a8bda-104">Example</span></span>  
 <span data-ttu-id="a8bda-105">Aşağıdaki kod örneğinde nasıl ekleneceğini gösterir bir <xref:System.Windows.Forms.ToolStripContainer> ve <xref:System.Windows.Forms.ToolStrip> bir Windows Forms için öğelerine eklemek nasıl <xref:System.Windows.Forms.ToolStrip>ve nasıl ekleneceği <xref:System.Windows.Forms.ToolStrip> için <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> , <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a8bda-105">The following code example demonstrates how to add a <xref:System.Windows.Forms.ToolStripContainer> and a <xref:System.Windows.Forms.ToolStrip> to a Windows Forms, how to add items to the <xref:System.Windows.Forms.ToolStrip>, and how to add the <xref:System.Windows.Forms.ToolStrip> to the <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8bda-106">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="a8bda-106">Compiling the Code</span></span>  
 <span data-ttu-id="a8bda-107">Bu kod örneği gerektirir:</span><span class="sxs-lookup"><span data-stu-id="a8bda-107">This code example requires:</span></span>  
  
-   <span data-ttu-id="a8bda-108">System.Drawing, System.Text ve System.Windows.Forms derlemelerine başvurular.</span><span class="sxs-lookup"><span data-stu-id="a8bda-108">References to the System.Drawing, System.Text, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a8bda-109">Bu örnek için komut satırından oluşturma hakkında bilgi için [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] veya [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], bkz: [komut satırından derleme](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) veya [komut satırı derleme ile csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a8bda-109">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a8bda-110">Bu örnek ayrıca oluşturmak [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] yeni bir proje kodunu yapıştırma tarafından.</span><span class="sxs-lookup"><span data-stu-id="a8bda-110">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="a8bda-111">Ayrıca bkz. [nasıl yapılır: derleme ve Visual Studio kullanarak tam Windows Forms kod örneği çalıştırma](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) veya [ToolStripContainer görevler iletişim kutusu](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="a8bda-111">See also [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) or [ToolStripContainer Tasks Dialog Box](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bda-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a8bda-112">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="a8bda-113">ToolStripContainer denetimi</span><span class="sxs-lookup"><span data-stu-id="a8bda-113">ToolStripContainer Control</span></span>](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [<span data-ttu-id="a8bda-114">ToolStrip denetimi</span><span class="sxs-lookup"><span data-stu-id="a8bda-114">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)