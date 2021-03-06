---
title: "Sunucu özel bileşik tasarımcıları - iş akışı öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b529d1c150f686fb4a39f968001c9ac03c7c1dc0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Sunucu özel bileşik tasarımcıları - iş akışı öğesi
<xref:System.Activities.Presentation.WorkflowItemPresenter> "Nerede rasgele bir etkinlik yerleştirilebilen bırakma bölgesi" oluşturulmasında verir WF Tasarımcı programlama modeli anahtar türü. Bu örnek bir etkinlik Tasarımcısı bu yüzeyleri böyle bir "bırakma bölgesi." nasıl oluşturulacağını gösterir  
  
 Bu örnek gösterilmektedir:  
  
## <a name="demonstrates"></a>Gösteriler  
  
-   Özel Etkinlik Tasarımcısı ile oluşturma bir <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
-   Meta veri deposu kullanarak özel Tasarımcısı kaydediliyor.  
  
-   Rehosted araç programlama bildirimli olarak ve imperatively.  
  
## <a name="sample-details"></a>Örnek Ayrıntıları  
 Bu örnek kodu gösterilir:  
  
-   Özel Etkinlik Tasarımcısı için yerleşik `SimpleNativeActivity` sınıfı.  
  
-   Özel Etkinlik Tasarımcısı ile oluşturma bir <xref:System.Activities.Presentation.WorkflowItemPresenter>.  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
    <sap:ActivityDesigner.Resources>  
        <DataTemplate x:Key="Collapsed">  
            <StackPanel>  
                <TextBlock>This is the collapsed view</TextBlock>  
            </StackPanel>  
        </DataTemplate>  
        <DataTemplate x:Key="Expanded">  
            <StackPanel>  
                <TextBlock>Custom Text</TextBlock>  
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                        HintText="Please drop an activity here" />  
            </StackPanel>  
        </DataTemplate>  
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
            <Style.Triggers>  
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                </DataTrigger>  
            </Style.Triggers>  
        </Style>  
    </sap:ActivityDesigner.Resources>  
    <Grid>  
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
    </Grid>  
</sap:ActivityDesigner>  
```  
  
 WPF veri bağlama bağlamak için kullanımına dikkat edin `ModelItem.Body`. `ModelItem`özelliği açıktır <xref:System.Activities.Presentation.ActivityDesigner> Tasarımcı kullanılıyor olduğu için bu durumda, temel alınan nesnesine başvuruyor **SimpleNativeActivity**.  
  
#### <a name="to-setup-build-and-run-the-sample"></a>Kurulum, yapı ve örneği çalıştırmak için  
  
1.  Çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Uygulamasını derlemek ve çalıştırmak için F5 tuşuna basın.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [İş Akışı Tasarımcısı ile Uygulama Geliştirme](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
