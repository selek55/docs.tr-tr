---
title: "Nasıl yapılır: StackPanel Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226ac10e4f221cc381b7c59179b2667e20aa757
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-stackpanel"></a>Nasıl yapılır: StackPanel Oluşturma
Bu örnek nasıl oluşturulacağını gösterir bir <xref:System.Windows.Controls.StackPanel>.  
  
## <a name="example"></a>Örnek  
 A <xref:System.Windows.Controls.StackPanel> , belirtilen yönde öğeleri yığın olanak sağlar. Üzerinde tanımlanan özellikleri kullanarak <xref:System.Windows.Controls.StackPanel>, içerik akış her ikisi de dikey olarak, varsayılan ayar olan ya da yatay olarak.  
  
 Aşağıdaki örnek dikey olarak beş yığınlar <xref:System.Windows.Controls.TextBlock> denetimleri, her biri farklı bir <xref:System.Windows.Controls.Border> ve <xref:System.Windows.Controls.Border.Background%2A>, kullanarak <xref:System.Windows.Controls.StackPanel>. Belirtilen en alt öğeleri <xref:System.Windows.FrameworkElement.Width%2A> ana pencereyi doldurmak için yayılır; ancak, alt öğeleri olan bir belirtilen <xref:System.Windows.FrameworkElement.Width%2A>, pencere içinde ortalanır.  
  
 Varsayılan yığın yönü bir <xref:System.Windows.Controls.StackPanel> dikeydir. İçindeki içerik akışını denetlemek için bir <xref:System.Windows.Controls.StackPanel>, kullanın <xref:System.Windows.Controls.StackPanel.Orientation%2A> özelliği. Yatay hizalama kullanarak denetleyebilirsiniz <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> özelliği.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Controls.StackPanel>  
 [Panellere Genel Bakış](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/controls/stackpanel-how-to-topics.md)
