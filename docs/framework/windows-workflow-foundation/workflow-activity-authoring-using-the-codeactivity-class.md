---
title: "İş akışı etkinlik CodeActivity sınıfını kullanarak geliştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2daec260c1224cd81280c6bf699b70efc2072588
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a>İş akışı etkinlik CodeActivity sınıfını kullanarak geliştirme
İçinden devralma tarafından oluşturulan etkinlikleri <xref:System.Activities.CodeActivity> temel kesinlik temelli davranışı geçersiz kılarak uygulayabilirsiniz <xref:System.Activities.CodeActivity.Execute%2A> yöntemi.  
  
## <a name="using-codeactivitycontext"></a>CodeActivityContext kullanma  
 İş akışı çalışma zamanı özelliklerini erişilebilir içinden <xref:System.Activities.CodeActivity.Execute%2A> üyeleri kullanarak yöntemi `context` parametresinin türü <xref:System.Activities.CodeActivityContext>. Aracılığıyla kullanılabilen özelliklerin <xref:System.Activities.CodeActivityContext> şunları içerir:  
  
-   Bağımsız değişkenler ve değerleri ayarlama ve alma.  
  
-   Özel İzleme özelliklerini kullanarak <xref:System.Activities.CodeActivityContext.Track%2A>.  
  
-   Etkinliğin yürütme özelliklerini kullanarak erişimi <xref:System.Activities.CodeActivityContext.GetProperty%2A>.  
  
#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a>CodeActivity devralan bir özel etkinlik oluşturmak için  
  
1.  Açık[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Seçin **dosya**, **yeni**ve ardından **proje**. Seçin **Workflow 4.0** altında **Visual C#** içinde **proje türleri** penceresi ve select **v2010** düğümü. Seçin **etkinlik Kitaplığı** içinde **şablonları** penceresi. Yeni Proje HelloActivity olarak adlandırın.  
  
3.  Activity1.XAML HelloActivity projeye sağ tıklayıp **silmek**.  
  
4.  HelloActivity projesine sağ tıklatın ve **Ekle** ve ardından **sınıfı**. Yeni sınıf HelloActivity.cs olarak adlandırın.  
  
5.  Aşağıdaki HelloActivity.cs dosyasına ekleyin `using` yönergeleri.  
  
    ```csharp  
    using System.Activities;  
    using System.Activities.Statements;  
    ```  
  
6.  Devralınan yeni sınıf olun <xref:System.Activities.CodeActivity> bir taban sınıfı için sınıf bildirimi ekleyerek.  
  
    ```csharp  
    class HelloActivity : CodeActivity  
    ```  
  
7.  İşlevselliği sınıfa ekleyerek bir <xref:System.Activities.CodeActivity.Execute%2A> yöntemi.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
    }  
    ```  
  
8.  Kullanım <xref:System.Activities.CodeActivityContext> izleme kaydı oluşturun.  
  
    ```csharp  
    protected override void Execute(CodeActivityContext context)  
    {  
        Console.WriteLine("Hello World!");  
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");  
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));  
        context.Track(record);  
    }  
    ```
