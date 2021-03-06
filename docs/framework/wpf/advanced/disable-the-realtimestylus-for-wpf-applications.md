---
title: "WPF Uygulamaları için RealTimeStylus'u Devre Dışı Bırakma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fc4ec888419e385a57216f078387f731c0ab8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>WPF Uygulamaları için RealTimeStylus'u Devre Dışı Bırakma
Windows Presentation Foundation (WPF), Windows 7 dokunmatik girişi işlemek için destek oluşturdu. Destek tablet platformun gerçek zamanlı kalem giriş olarak üzerinden gelen <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, ve <xref:System.Windows.UIElement.OnStylusMove%2A> olaylar. Windows 7, Win32 WM_TOUCH pencere iletileri şeklinde çoklu dokunma girişi de sağlar. Bu iki API aynı HWND üzerinde karşılıklı olarak birbirini dışlar. Etkinleştirme dokunma tablet platform (WPF uygulamaları için varsayılan) aracılığıyla devre dışı bırakır WM_TOUCH iletilerini girin. Sonuç olarak, WPF penceresinden dokunma iletileri almak için WM_TOUCH kullanmak için WPF içinde yerleşik kalem desteğini devre dışı bırakmalısınız. Bu, WM_TOUCH kullanan bir bileşeni barındıran bir WPF penceresi gibi senaryolarda geçerlidir.  
  
 Kalem girişini Dinlemesini devre dışı bırakmak için WPF penceresi tarafından eklenen herhangi bir tablet desteğini kaldırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kod, yansıma kullanarak varsayılan tablet platform desteği kaldırma gösterilmektedir.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ekran Kaleminden Gelen Girişi Önleme](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
