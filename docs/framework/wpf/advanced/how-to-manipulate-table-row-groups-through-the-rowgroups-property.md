---
title: "Nasıl yapılır: bir tablo &#39; işlemek RowGroups özelliği aracılığıyla s satır grupları"
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
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14226a549aaef8ea4c5a98fa6bc6249db824b35a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-a-table39s-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="f4de3-102">Nasıl yapılır: bir tablo &#39; işlemek RowGroups özelliği aracılığıyla s satır grupları</span><span class="sxs-lookup"><span data-stu-id="f4de3-102">How to: Manipulate a Table&#39;s Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="f4de3-103">Bu örnek bir tablonun satır grupları üzerinde gerçekleştirilen daha yaygın işlemlerin bazılarını göstermektedir <xref:System.Windows.Documents.Table.RowGroups%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="f4de3-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4de3-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-104">Example</span></span>  
 <span data-ttu-id="f4de3-105">Aşağıdaki örnek yeni bir tablo oluşturur ve ardından <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> tablonun sütunlar ekleme yöntemi <xref:System.Windows.Documents.Table.RowGroups%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="f4de3-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-106">Example</span></span>  
 <span data-ttu-id="f4de3-107">Aşağıdaki örnek yeni bir ekler <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="f4de3-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="f4de3-108">Yeni bir sütun yeni ilk satır kolaylaştırarak dizin konumunda 0, eklenen tablo grubu.</span><span class="sxs-lookup"><span data-stu-id="f4de3-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4de3-109"><xref:System.Windows.Documents.TableRowGroupCollection> Koleksiyonu kullanan standart sıfır tabanlı dizin.</span><span class="sxs-lookup"><span data-stu-id="f4de3-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-110">Example</span></span>  
 <span data-ttu-id="f4de3-111">Aşağıdaki örnek, belirli bir birkaç satır ekler <xref:System.Windows.Documents.TableRowGroup> (dizin tarafından belirtilen) tablosundaki.</span><span class="sxs-lookup"><span data-stu-id="f4de3-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-112">Example</span></span>  
 <span data-ttu-id="f4de3-113">Aşağıdaki örnek ilk satır grubu tablosundaki satır üzerinde bazı rasgele özelliklere erişir.</span><span class="sxs-lookup"><span data-stu-id="f4de3-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-114">Example</span></span>  
 <span data-ttu-id="f4de3-115">Aşağıdaki örnek, belirli bir birçok hücre ekler <xref:System.Windows.Documents.TableRow> (dizin tarafından belirtilen) tablosundaki.</span><span class="sxs-lookup"><span data-stu-id="f4de3-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-116">Example</span></span>  
 <span data-ttu-id="f4de3-117">Aşağıdaki örnek, bazı rastgele yöntemleri ve özellikleri ilk satır grubundaki ilk satırda hücrelerde erişin.</span><span class="sxs-lookup"><span data-stu-id="f4de3-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-118">Example</span></span>  
 <span data-ttu-id="f4de3-119">Aşağıdaki örnek sayısını döndürür <xref:System.Windows.Documents.TableRowGroup> tablo tarafından barındırılan öğeleri.</span><span class="sxs-lookup"><span data-stu-id="f4de3-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-120">Example</span></span>  
 <span data-ttu-id="f4de3-121">Aşağıdaki örnek, belirli bir satır grubu başvuruya göre kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f4de3-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-122">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-122">Example</span></span>  
 <span data-ttu-id="f4de3-123">Aşağıdaki örnek, belirli bir satır grubu dizini tarafından kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f4de3-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="f4de3-124">Örnek</span><span class="sxs-lookup"><span data-stu-id="f4de3-124">Example</span></span>  
 <span data-ttu-id="f4de3-125">Aşağıdaki örnekte tüm satır gruplarını tablonun satır grupları koleksiyonundan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="f4de3-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="f4de3-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f4de3-126">See Also</span></span>  
 [<span data-ttu-id="f4de3-127">Nasıl yapılır: Akış içeriği öğeleri Inlines özelliği aracılığıyla düzenleme</span><span class="sxs-lookup"><span data-stu-id="f4de3-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="f4de3-128">Blokların özelliği aracılığıyla FlowDocument işlemek</span><span class="sxs-lookup"><span data-stu-id="f4de3-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="f4de3-129">Bir tablonun sütunlar sütunlar özelliği aracılığıyla yönetmek</span><span class="sxs-lookup"><span data-stu-id="f4de3-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)