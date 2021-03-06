---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1eafe8d7ccd6f2c71b754dadc343518948e7146
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nowarn"></a>/nowarn
Derleyicinin uyarıları oluşturma yeteneği gizler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|`numberList`|İsteğe bağlı. Derleyici bastırmak uyarı kimliği numaralarını virgülle ayrılmış listesi. Uyarı kimlikleri belirtilmezse, tüm uyarıları görüntülenmez.|  
  
## <a name="remarks"></a>Açıklamalar  
 `/nowarn` Seçeneği neden olan derleyici uyarıları oluşturma değil. Tek bir uyarıyı gizlemek için uyarı kimliği tedarik `/nowarn` izleyen iki nokta üst üste seçeneği. Birden çok uyarı numaralarını virgülle ayırın.  
  
 Uyarı tanımlayıcı yalnızca sayısal parçasını belirtmeniz gerekir. Örneğin, BC42024, kullanılmayan yerel değişkenler için uyarıyı gizlemek istiyorsanız belirtin `/nowarn:42024`.  
  
 Uyarı Kimliği numaralarını hakkında daha fazla bilgi için bkz: [yapılandırma uyarılarını Visual Basic'te](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Tümleşik geliştirme ortamı/nowarn Visual Studio'da ayarlamak için|  
|---|  
|1.  Seçili bir projeyi **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**. <br />2.  Tıklatın **derleme** sekmesi.<br />3.  Seçin **tüm uyarıları devre dışı bırakmak** tüm uyarıları devre dışı bırakmak için onay kutusunu.<br />     - veya -<br />     Belirli bir uyarı devre dışı bırakmak için **hiçbiri** uyarı bitişik aşağı açılan listeden.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlerken `T2.vb` ve tüm uyarılar görüntülemez.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod derlerken `T2.vb` ve kullanılmayan yerel değişkenler (42024) için uyarıları göstermez.  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Visual Basic'teki Uyarıları Yapılandırma](/visualstudio/ide/configuring-warnings-in-visual-basic)
