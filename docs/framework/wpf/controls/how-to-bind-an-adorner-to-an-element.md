---
title: "Nasıl yapılır: Öğeye bir Donatıcı Bağlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b1da3216ce6d3507c304ff957728d33ba1b9bd9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="bf4cb-102">Nasıl yapılır: Öğeye bir Donatıcı Bağlama</span><span class="sxs-lookup"><span data-stu-id="bf4cb-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="bf4cb-103">Bu örnek bir donatıcıyı programlı olarak belirtilen bir bağlamak nasıl gösterir <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf4cb-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="bf4cb-104">Example</span></span>  
 <span data-ttu-id="bf4cb-105">Belirli bir donatıcı bağlamak için <xref:System.Windows.UIElement>, şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="bf4cb-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="bf4cb-106">Çağrı `static` yöntemi <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> almak için bir <xref:System.Windows.Documents.AdornerLayer> için nesne <xref:System.Windows.UIElement> donatılacak.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="bf4cb-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>Belirtilen başlangıç görsel ağaç anlatılmaktadır **UIElement**ve bulduğu ilk donatıcı katmanı döndürür.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="bf4cb-108">(Hiçbir donatıcı katman bulunamazsa, yöntem null değeri döndürür.)</span><span class="sxs-lookup"><span data-stu-id="bf4cb-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="bf4cb-109">Çağrı <xref:System.Windows.Documents.AdornerLayer.Add%2A> donatıcıyı hedef bağlamak için yöntemi **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="bf4cb-110">Aşağıdaki örnekte (yukarıda gösterilen) SimpleCircleAdorner bağlanır bir <xref:System.Windows.Controls.TextBox> adlı *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="bf4cb-111">Kullanarak [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] donatıcı başka bir öğeye bağlamak için şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4cb-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bf4cb-112">See Also</span></span>  
 [<span data-ttu-id="bf4cb-113">Donatıcılar genel bakış</span><span class="sxs-lookup"><span data-stu-id="bf4cb-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)