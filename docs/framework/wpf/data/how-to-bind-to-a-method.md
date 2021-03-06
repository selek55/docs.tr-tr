---
title: "Nasıl yapılır: Bir Yönteme Bağlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45f2a141b09c52085c13803b8d338fdc9eebf135
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-to-a-method"></a>Nasıl yapılır: Bir Yönteme Bağlama
Aşağıdaki örnek, bir yöntemi kullanarak bağlamak gösterilmiştir <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, `TemperatureScale` bir yönteme sahip bir sınıf `ConvertTemp`, iki parametreyi alır (birini `double` ve aşağıdakilerden birini `enum` türü `TempType)` ve verilen değer bir sıcaklık ölçeğinden diğerine dönüştürür. Aşağıdaki örnekte, bir <xref:System.Windows.Data.ObjectDataProvider> örneği oluşturmak için kullanılan `TemperatureScale` nesnesi. `ConvertTemp` Yöntemi iki belirtilen parametrelerle çağrılır.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Bir kaynak olarak kullanılabilir bir yöntemdir, sonuçlarını bağlayabilirsiniz. Aşağıdaki örnekte, <xref:System.Windows.Controls.TextBox.Text%2A> özelliği <xref:System.Windows.Controls.TextBox> ve <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> , <xref:System.Windows.Controls.ComboBox> yöntemi iki parametre için bağlıdır. Bu, dönüştürmek için sıcaklık belirtmek için kullanıcıları ve dönüştürmek için sıcaklık ölçek sağlar. Unutmayın <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> ayarlanır `true` bağlama biz çünkü <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> özelliği <xref:System.Windows.Data.ObjectDataProvider> örneği ve özellikleri tarafından Sarmalanan nesnesinin <xref:System.Windows.Data.ObjectDataProvider> ( `TemperatureScale` nesnesi).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> Son <xref:System.Windows.Controls.Label> güncelleştirmeleri kullanıcı içeriğini değiştirdiğinde <xref:System.Windows.Controls.TextBox> ya da seçimini <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Dönüştürücü `DoubleToString` double alır ve içindeki bir dizeye dönüştürür <xref:System.Windows.Data.IValueConverter.Convert%2A> yönünü (bağlama hedefi bağlama kaynağından olduğu <xref:System.Windows.Controls.TextBox.Text%2A> özelliği) ve dönüştüren bir `string` için bir `double` içinde <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> yönü.  
  
 `InvalidationCharacterRule` Olan bir <xref:System.Windows.Controls.ValidationRule> geçersiz karakterler için denetler. Kırmızı bir sınır olan varsayılan hata şablonu çevresinde <xref:System.Windows.Controls.TextBox>, giriş değeri double değeri olmadığında kullanıcıları bilgilendirmek için görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl Yapılır Konuları](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Sabit Listesine Bağlama](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
