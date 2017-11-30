---
title: "Nasıl yapılır: Akış İçeriği Öğelerini Blokların Özelliği ile Düzenleme"
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
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f246b7ab5eae52b745849daf2bedadb7431d7d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a><span data-ttu-id="9eb18-102">Nasıl yapılır: Akış İçeriği Öğelerini Blokların Özelliği ile Düzenleme</span><span class="sxs-lookup"><span data-stu-id="9eb18-102">How to: Manipulate Flow Content Elements through the Blocks Property</span></span>
<span data-ttu-id="9eb18-103">Bu örneklerin üzerinden akış içerik öğelerinde gerçekleştirilen daha yaygın işlemlerin bazılarını göstermek **blokları** özelliği.</span><span class="sxs-lookup"><span data-stu-id="9eb18-103">These examples demonstrate some of the more common operations that can be performed on flow content elements through the **Blocks** property.</span></span> <span data-ttu-id="9eb18-104">Bu özellik eklemek ve öğeleri kaldırmak için kullanılan <xref:System.Windows.Documents.BlockCollection>.</span><span class="sxs-lookup"><span data-stu-id="9eb18-104">This property is used to add and remove items from <xref:System.Windows.Documents.BlockCollection>.</span></span> <span data-ttu-id="9eb18-105">Akış içerik öğeleri bu özellik bir **blokları** özellik içerir:</span><span class="sxs-lookup"><span data-stu-id="9eb18-105">Flow content elements that feature a **Blocks** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="9eb18-106">Kullanmak için bu örnekler durum <xref:System.Windows.Documents.Section> akış halinde content öğesi, ancak bu teknikler akış içerik öğe koleksiyonu barındıran tüm öğeler için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="9eb18-106">These examples happen to use <xref:System.Windows.Documents.Section> as the flow content element, but these techniques are applicable to all elements that host a flow content element collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb18-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="9eb18-107">Example</span></span>  
 <span data-ttu-id="9eb18-108">Aşağıdaki örnek yeni bir oluşturur <xref:System.Windows.Documents.Section> ve ardından **Ekle** için yeni bir paragraf ekleme yöntemi **bölüm** içeriği.</span><span class="sxs-lookup"><span data-stu-id="9eb18-108">The following example creates a new <xref:System.Windows.Documents.Section> and then uses the **Add** method to add a new Paragraph to the **Section** contents.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a><span data-ttu-id="9eb18-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="9eb18-109">Example</span></span>  
 <span data-ttu-id="9eb18-110">Aşağıdaki örnek yeni bir oluşturur <xref:System.Windows.Documents.Paragraph> öğesi ve başında ekler <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="9eb18-110">The following example creates a new <xref:System.Windows.Documents.Paragraph> element and inserts it at the beginning of the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a><span data-ttu-id="9eb18-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="9eb18-111">Example</span></span>  
 <span data-ttu-id="9eb18-112">Aşağıdaki örnek en üst düzey sayısını alır <xref:System.Windows.Documents.Block> içindeki öğe <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="9eb18-112">The following example gets the number of top-level <xref:System.Windows.Documents.Block> elements contained in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a><span data-ttu-id="9eb18-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="9eb18-113">Example</span></span>  
 <span data-ttu-id="9eb18-114">Aşağıdaki örnek, son siler <xref:System.Windows.Documents.Block> öğesinde <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="9eb18-114">The following example deletes the last <xref:System.Windows.Documents.Block> element in the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a><span data-ttu-id="9eb18-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="9eb18-115">Example</span></span>  
 <span data-ttu-id="9eb18-116">Aşağıdaki örnekte tüm içeriği siler (<xref:System.Windows.Documents.Block> öğeleri) gelen <xref:System.Windows.Documents.Section>.</span><span class="sxs-lookup"><span data-stu-id="9eb18-116">The following example clears all of the contents (<xref:System.Windows.Documents.Block> elements) from the <xref:System.Windows.Documents.Section>.</span></span>  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a><span data-ttu-id="9eb18-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9eb18-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="9eb18-118">Akış belgesi genel bakış</span><span class="sxs-lookup"><span data-stu-id="9eb18-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="9eb18-119">Tablonun satır grupları RowGroups özelliği aracılığıyla denetlemek</span><span class="sxs-lookup"><span data-stu-id="9eb18-119">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="9eb18-120">Bir tablonun sütunlar sütunlar özelliği aracılığıyla yönetmek</span><span class="sxs-lookup"><span data-stu-id="9eb18-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="9eb18-121">Tablonun satır grupları RowGroups özelliği aracılığıyla denetlemek</span><span class="sxs-lookup"><span data-stu-id="9eb18-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)