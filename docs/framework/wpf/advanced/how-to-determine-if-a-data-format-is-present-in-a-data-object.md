---
title: "Nasıl yapılır: Veri Nesnesinde Veri Biçiminin Olup Olmadığını Belirleme"
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
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e5eaad64e18ff955340a8e91bfe8bd0e09dd8d7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="af08d-102">Nasıl yapılır: Veri Nesnesinde Veri Biçiminin Olup Olmadığını Belirleme</span><span class="sxs-lookup"><span data-stu-id="af08d-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="af08d-103">Aşağıdaki örnekler çeşitli kullanmayı <xref:System.Windows.DataObject.GetDataPresent%2A> yöntemi aşırı yüklemeleri için sorgu belirli veri biçimi veri nesnesinde var olup olmadığını.</span><span class="sxs-lookup"><span data-stu-id="af08d-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af08d-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="af08d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af08d-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af08d-105">Description</span></span>  
 <span data-ttu-id="af08d-106">Aşağıdaki kod örneği kullanan <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> aşırı sorgulamak için belirli veri biçimi tanımlayıcısı dizesi tarafından varlığı.</span><span class="sxs-lookup"><span data-stu-id="af08d-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af08d-107">Kod</span><span class="sxs-lookup"><span data-stu-id="af08d-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="af08d-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="af08d-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af08d-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af08d-109">Description</span></span>  
 <span data-ttu-id="af08d-110">Aşağıdaki kod örneği kullanan <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> aşırı yüklemesine türüne göre belirli veri biçimi varlığı için sorgu.</span><span class="sxs-lookup"><span data-stu-id="af08d-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af08d-111">Kod</span><span class="sxs-lookup"><span data-stu-id="af08d-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="af08d-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="af08d-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af08d-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="af08d-113">Description</span></span>  
 <span data-ttu-id="af08d-114">Aşağıdaki kod örneği kullanan <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> tanımlayıcısı dizesi tarafından aşırı sorgulamak için veri ve otomatik dönüştürülebilir veri biçimleri işlemek nasıl belirtme.</span><span class="sxs-lookup"><span data-stu-id="af08d-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af08d-115">Kod</span><span class="sxs-lookup"><span data-stu-id="af08d-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="af08d-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="af08d-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>