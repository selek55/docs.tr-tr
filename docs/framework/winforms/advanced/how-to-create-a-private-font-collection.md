---
title: "Nasıl yapılır: Özel Yazı Tipi Koleksiyonu Oluşturma"
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
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3016fb9a1b1d8466137bcaddb0b885c02c399baf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="e5f3b-102">Nasıl yapılır: Özel Yazı Tipi Koleksiyonu Oluşturma</span><span class="sxs-lookup"><span data-stu-id="e5f3b-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="e5f3b-103"><xref:System.Drawing.Text.PrivateFontCollection> Sınıfının devraldığı <xref:System.Drawing.Text.FontCollection> soyut taban sınıfı.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="e5f3b-104">Kullanabileceğiniz bir <xref:System.Drawing.Text.PrivateFontCollection> uygulamanız için özellikle yazı tipleri kümesini korumak için nesne.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="e5f3b-105">Özel yazı tipi koleksiyonu yüklü yazı tipleri ve bunun yanı sıra bilgisayarda yüklü değil yazı tipleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="e5f3b-106">Özel yazı tipi koleksiyonu için bir yazı tipi dosyası eklemek için arama <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> yöntemi bir <xref:System.Drawing.Text.PrivateFontCollection> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="e5f3b-107"><xref:System.Drawing.Text.FontCollection.Families%2A> Özelliği bir <xref:System.Drawing.Text.PrivateFontCollection> nesnesini içeren bir dizi <xref:System.Drawing.FontFamily> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="e5f3b-108">Özel yazı tipi koleksiyonundaki yazı tipi aileleri sayısı mutlaka koleksiyonuna eklenen yazı tipi dosya sayısı ile aynı değil.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="e5f3b-109">Örneğin, bir koleksiyona ArialBd.tff, Times.tff ve TimesBd.tff dosyaları eklemek varsayalım.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="e5f3b-110">Olacaktır üç dosyaları ancak koleksiyonda yalnızca iki aileleri Times.tff ve TimesBd.tff aynı aileye ait olduğundan.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5f3b-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="e5f3b-111">Example</span></span>  
 <span data-ttu-id="e5f3b-112">Aşağıdaki üç yazı tipi dosyaları aşağıdaki örnek, bir <xref:System.Drawing.Text.PrivateFontCollection> nesnesi:</span><span class="sxs-lookup"><span data-stu-id="e5f3b-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="e5f3b-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, normal)</span><span class="sxs-lookup"><span data-stu-id="e5f3b-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="e5f3b-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, kalın italik)</span><span class="sxs-lookup"><span data-stu-id="e5f3b-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="e5f3b-115">C:\\*systemroot*\Fonts\TimesBd.tff (kez yeni Roma, kalın)</span><span class="sxs-lookup"><span data-stu-id="e5f3b-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="e5f3b-116">Bir dizi kodu alır <xref:System.Drawing.FontFamily> nesnelerin <xref:System.Drawing.Text.FontCollection.Families%2A> özelliği <xref:System.Drawing.Text.PrivateFontCollection> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="e5f3b-117">Her <xref:System.Drawing.FontFamily> nesne kodu çağrıları koleksiyonunun <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> yöntemi (normal, kalın, italik ve kalın italik, alt çizgi ve üstü çizili) çeşitli stiller kullanılabilir olup olmadığını belirlemek için.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="e5f3b-118">Bağımsız değişkenler geçirilen <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> yöntemi üyeleri olan <xref:System.Drawing.FontStyle> numaralandırması.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="e5f3b-119">Verilen ailesi/stil birleşimi varsa bir <xref:System.Drawing.Font> nesnesi, bu ailesi ve stili kullanılarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="e5f3b-120">Geçirilen ilk bağımsız değişken <xref:System.Drawing.Font.%23ctor%2A> Oluşturucusu yazı tipi ailesinin adı olduğu (olmayan bir <xref:System.Drawing.FontFamily> nesne diğer varyasyonları için olduğu gibi <xref:System.Drawing.Font.%23ctor%2A> Oluşturucusu).</span><span class="sxs-lookup"><span data-stu-id="e5f3b-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="e5f3b-121">Sonra <xref:System.Drawing.Font> nesne yapılandırılmıştır, için geçirilen <xref:System.Drawing.Graphics.DrawString%2A> yöntemi <xref:System.Drawing.Graphics> stil adı ile birlikte aile adı görüntülenecek sınıf.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="e5f3b-122">Aşağıdaki kod çıkışı, aşağıdaki çizimde gösterilen çıkış benzerdir.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-122">The output of the following code is similar to the output shown in the following illustration.</span></span>  
  
 <span data-ttu-id="e5f3b-123">![Yazı tipleri metin](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span><span class="sxs-lookup"><span data-stu-id="e5f3b-123">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span></span>  
  
 <span data-ttu-id="e5f3b-124">(Bu, aşağıdaki kod örneğinde özel yazı tipi koleksiyonu eklendi) Arial.tff Arial Normal stili için yazı tipi dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="e5f3b-125">Ancak, program çıktısı Arial yazı tipi ailesi için normal dışında birkaç kullanılabilir stiller gösterdiğine dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="e5f3b-126">Çünkü [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kalın, italik ve kalın italik stilleri Normal stili benzetimini yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e5f3b-127">Ayrıca alt çizgiler ve Normal stili gelen da üst çizgi üretebilir.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-127"> can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="e5f3b-128">Benzer şekilde, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kalın stil veya italik stilini kalın italik stili benzetimini yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="e5f3b-129">Program çıktısı TimesBd.tff (kez yeni Roma, kalın) yalnızca olsa bile kalın italik stili kez ailesi için kullanılabilir olduğunu gösterir kez dosyasında koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e5f3b-130">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="e5f3b-130">Compiling the Code</span></span>  
 <span data-ttu-id="e5f3b-131">Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f3b-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e5f3b-132">See Also</span></span>  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [<span data-ttu-id="e5f3b-133">Yazı tipleri ve metin kullanma</span><span class="sxs-lookup"><span data-stu-id="e5f3b-133">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)