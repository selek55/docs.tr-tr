---
title: "Nasıl yapılır: Firefox WPF Eklentisinin Yüklü Olup Olmadığını Algılama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e821bd95679372fd169b7880e969fd10b5d03c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>Nasıl yapılır: Firefox WPF Eklentisinin Yüklü Olup Olmadığını Algılama
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Firefox etkinleştirir eklenti [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] ve kaybetmiş Mozilla Firefox tarayıcıda çalıştırmak için XAML dosyaları. Bu konu, HTML ve yöneticilerin Firefox WPF eklentisinin yüklü olup olmadığını belirlemek için kullanabileceğiniz JavaScript yazılmış bir betik sağlar.  
  
> [!NOTE]
>  Yükleme, dağıtma ve algılama hakkında daha fazla bilgi için [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], bkz: [geliştiriciler için .NET Framework'ü yüklemek](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Örnek  
 Zaman [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] olan yüklü istemci bilgisayar Firefox WPF eklentisi ile yapılandırılır. Aşağıdaki örnek betik, Firefox WPF eklentisini denetler ve uygun durum iletisini görüntüler.  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 Firefox WPF eklentisi denetle başarılı olursa, aşağıdaki durum iletisi görüntülenir:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 Aksi takdirde, aşağıdaki durum iletisi görüntülenir:  
  
 `The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET Framework 3.0'ın Yüklü Olup Olmadığını Algılama](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)  
 [.NET Framework 3.5'in Yüklü Olup Olmadığını Algılama](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)  
 [WPF XAML Tarayıcı Uygulamalarına Genel Bakış](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)
