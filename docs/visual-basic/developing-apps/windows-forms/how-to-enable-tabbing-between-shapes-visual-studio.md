---
title: "Nasıl Yapılır: Şekiller Arasında Sekmeyle Gitmeyi Etkinleştirme (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0b1e8b0378e65becd80324491632ecd8dbffdbbf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>Nasıl Yapılır: Şekiller Arasında Sekmeyle Gitmeyi Etkinleştirme (Visual Studio)
Çizgi ve Şekil denetimleri yok `TabStop` veya `TabIndex` özellikleri, ancak hala etkinleştirebilir bunlar arasında sekmeyle gitmeyi. Aşağıdaki örnekte, CTRL ve sekme tuşlarını tuşuna basarak şekiller arasında sekmeyle; yalnızca SEKME tuşuna basarak düğmeleri arasında sekmesinde.  
  
> [!NOTE]
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="to-enable-tabbing-among-shapes"></a>Şekiller arasında sekmeyle gitmeyi etkinleştirmek için  
  
1.  Üç sürükleyin <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> denetimleri ve iki <xref:System.Windows.Forms.Button> gelen denetimleri **araç** bir forma.  
  
2.  İçinde **Kod düzenleyicisinde**, ekleme bir `Imports` veya `using` deyimini dosyanın üst Modülü:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  Bir olay yordamında aşağıdaki kodu ekleyin:  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Aşağıdaki kodu ekleyin `Button1_PreviewKeyDown` olay yordamı:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl Yapılır: OvalShape ve RectangleShape Denetimleriyle Şekil Çizme](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Nasıl Yapılır: LineShape Denetimiyle Çizgi Çizme](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Çizgi ve Şekil Denetimlerine Giriş](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
