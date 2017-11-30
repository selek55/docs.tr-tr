---
title: "Nasıl yapılır: Bir Şekli Bir Görüntüyle Döşeme"
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
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8f825371d3849e96ace627e660fd7c59bd290185
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="21b18-102">Nasıl yapılır: Bir Şekli Bir Görüntüyle Döşeme</span><span class="sxs-lookup"><span data-stu-id="21b18-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="21b18-103">Dikdörtgen görüntüleri yalnızca döşeme birbirinin yanına kat kapsayacak şekilde yerleştirilebilir gibi diğer yanındaki dolgu (döşeme) bir şekli yerleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="21b18-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="21b18-104">Bir şekli iç döşeme için doku fırça kullanın.</span><span class="sxs-lookup"><span data-stu-id="21b18-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="21b18-105">Oluşturduğunuzda bir <xref:System.Drawing.TextureBrush> nesne oluşturucuya geçirdiğiniz bağımsız değişkenlerden biri olan bir <xref:System.Drawing.Image> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="21b18-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="21b18-106">İç bir şekli kısmını boyamak için doku fırça kullandığınızda, şekil bu görüntüyü yinelenen kopyalarını dolu.</span><span class="sxs-lookup"><span data-stu-id="21b18-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="21b18-107">Kaydırma modu özelliğini <xref:System.Drawing.TextureBrush> nesne belirler dikdörtgen kılavuzda yinelenen nasıl görüntü yönlendirilmiş aynıdır.</span><span class="sxs-lookup"><span data-stu-id="21b18-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="21b18-108">Tüm kutucukları ızgara aynı yönü yapabilir veya sonraki bir kılavuz konumundan Çevir görüntü yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="21b18-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="21b18-109">Çevirme yatay olabilir dikey veya her ikisi de.</span><span class="sxs-lookup"><span data-stu-id="21b18-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="21b18-110">Aşağıdaki örnekler çevirme farklı türleri ile döşeme gösterir.</span><span class="sxs-lookup"><span data-stu-id="21b18-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="21b18-111">Görüntü Döşeme</span><span class="sxs-lookup"><span data-stu-id="21b18-111">To tile an image</span></span>  
  
-   <span data-ttu-id="21b18-112">Bu örnekte aşağıdaki 75 × 75 görüntü 200 × 200 dikdörtgen döşeme için kullanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="21b18-113">![Döşeme 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="21b18-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="21b18-114">Aşağıdaki çizimde görüntüyle dikdörtgeni nasıl döşendiği gösterir.</span><span class="sxs-lookup"><span data-stu-id="21b18-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="21b18-115">Tüm kutucukları aynı yönü gerektiğini unutmayın; hiçbir çevirme yoktur.</span><span class="sxs-lookup"><span data-stu-id="21b18-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="21b18-116">![Döşeme 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="21b18-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="21b18-117">Bir resmi yatay olarak döşeme sırasında döndürmek için</span><span class="sxs-lookup"><span data-stu-id="21b18-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="21b18-118">Bu örnek aynı 75 × 75 görüntü 200 × 200 dikdörtgen doldurmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="21b18-119">Kaydırma modu görüntü Yatayda ters çevirmek için ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="21b18-120">Aşağıdaki çizimde görüntüyle dikdörtgeni nasıl döşendiği gösterir.</span><span class="sxs-lookup"><span data-stu-id="21b18-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="21b18-121">Belirli bir satırda sonraki bir kutucuğu taşıdığınızda, görüntünün yatay çevrilmiş unutmayın.</span><span class="sxs-lookup"><span data-stu-id="21b18-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="21b18-122">![Döşeme 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="21b18-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="21b18-123">Bir resmi dikey döşeme sırasında döndürmek için</span><span class="sxs-lookup"><span data-stu-id="21b18-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="21b18-124">Bu örnek aynı 75 × 75 görüntü 200 × 200 dikdörtgen doldurmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="21b18-125">Kaydırma modu görüntü Dikeyde ters çevirmek için ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="21b18-126">Bir resmi yatay ve dikey olarak çalışırken döşeme döndürmek için</span><span class="sxs-lookup"><span data-stu-id="21b18-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="21b18-127">Bu örnek aynı 75 × 75 görüntü 200 × 200 dikdörtgen döşeme için kullanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="21b18-128">Kaydırma modu görüntü Yatayda ve Dikeyde ters çevirmek için ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="21b18-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="21b18-129">Aşağıdaki çizimde, görüntü tarafından dikdörtgeni nasıl döşendiği gösterir.</span><span class="sxs-lookup"><span data-stu-id="21b18-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="21b18-130">Belirli bir satırda sonraki bir kutucuğu taşıdığınızda, görüntünün yatay çevrilmiş not alın ve belirli bir sütundaki sonraki bir kutucuğu taşıdığınızda, görüntünün dikey çevrilmiş.</span><span class="sxs-lookup"><span data-stu-id="21b18-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="21b18-131">![Döşeme 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="21b18-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="21b18-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="21b18-132">See Also</span></span>  
 [<span data-ttu-id="21b18-133">Şekilleri doldurmak için fırça kullanma</span><span class="sxs-lookup"><span data-stu-id="21b18-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)