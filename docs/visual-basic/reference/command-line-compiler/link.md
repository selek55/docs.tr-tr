---
title: /link (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: effaeae48bdeb1dfd0f8cda31fedf2436e7deaca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="link-visual-basic"></a>/link (Visual Basic)
Derleyici COM türü bilgileri belirtilen derlemelerde şu anda derlediğiniz proje kullanılabilir hale getirmek neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|`fileList`|Gerekli. Derleme dosya adlarının virgülle ayrılmış listesi. Dosya adı boşluk içeriyorsa adı tırnak işaretleri içine alın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `/link` Seçeneği katıştırılmış türde bilgi içeren bir uygulama dağıtmanıza olanak sağlar. Uygulamanın gömülü tür bilgileri çalışma zamanı derlemesine başvuru gerek kalmadan uygulama çalışma zamanı derlemesi türlerinde sonra kullanabilirsiniz. Çeşitli çalışma zamanı derleme sürümleri yayımladıysanız katıştırılmış tür bilgileri içeren uygulama derlenmesi gerek kalmadan çeşitli sürümleriyle çalışabilir. Bir örnek için bkz: [izlenecek yol: yönetilen derlemelerden türler katıştırma](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 Kullanarak `/link` COM birlikte çalışma ile çalışırken seçenek özellikle yararlıdır. Böylelikle, uygulamanızın artık hedef bilgisayarda birincil birlikte çalışma derlemesi (PIA) gerektirir COM türlerini eklenebilir. `/link` Seçeneği elde edilen derlenmiş kod başvurulan birlikte çalışma derlemeye COM tür bilgilerini katıştırma derleyici bildirir. COM türü CLSID (GUID) değeri tarafından tanımlanır. Sonuç olarak, uygulamanızı aynı CLSID değerlerine sahip aynı COM türlerini yüklü olduğu bir hedef bilgisayarda çalıştırabilirsiniz. Microsoft Office'i otomatikleştiren uygulamalar iyi bir örnektir. Office gibi uygulamalar genellikle farklı sürümleri arasında aynı CLSID değeri tutmak için uygulamanız başvurulan COM türlerini uzun .NET Framework 4 veya daha sonra hedef bilgisayarda yüklü olduğundan ve yöntemler, özellikler, uygulamanızın kullandığı gibi kullanabilirsiniz veya Başvurulan COM türlerinde dahil olaylar.  
  
 `/link` Seçeneği yalnızca arabirimleri, yapılar ve temsilciler katıştırır. COM sınıfları katıştırma desteklenmiyor.  
  
> [!NOTE]
>  Kodunuzda katıştırılmış COM türünün bir örneğini oluştururken uygun arabirimi kullanarak örneği oluşturmanız gerekir. Coclass'ı kullanarak katıştırılmış COM türünün bir örneği oluşturulmaya çalışılırken bir hata neden olur.  
  
 Ayarlamak için `/link` seçeneğini [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], bir derleme başvurusu ekleyin ve ayarlayın `Embed Interop Types` özelliğine **doğru**. İçin varsayılan `Embed Interop Types` özelliği **false**.  
  
 Bir COM derlemesine (a derlemesi) bağlantısının kendisi başka bir COM derlemesine (derleme B) başvuruyor, aşağıdakilerden biri doğruysa B derlemesine bağlantı gerekir:  
  
-   Derlemesi türünden bir türden devralır veya derleme B'deki bir arabirimi uygular.  
  
-   Alan, özellik, olay veya b derlemesinden dönüş türü veya parametresi türü olan yöntemi çağrılır.  
  
 Kullanım [/Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) bir veya daha fazla derleme başvurularını bulunduğu dizini belirtmek için.  
  
 Gibi [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) derleyici seçeneği `/link` derleyici seçeneği başvuruları sık kullanılan Vbc.rsp yanıt dosyası kullanan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] derlemeler. Kullanmak [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) derleyicinin Vbc.rsp dosya kullanmasını istemiyorsanız derleyici seçeneği.  
  
 Kısa formunu `/link` olan `/l`.  
  
## <a name="generics-and-embedded-types"></a>Genel türler ve katıştırılmış türler  
 Aşağıdaki bölümlerde, genel türler birlikte çalışma türlerini katıştır uygulamalarında kullanma sınırlamaları açıklanmaktadır.  
  
### <a name="generic-interfaces"></a>Genel Arabirimler  
 Birlikte çalışma bir derlemeden katıştırılmış genel arabirimler kullanılamaz. Bu, aşağıdaki örnekte gösterilir.  
  
 [!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a>Genel Parametreler türleri  
 Türü birlikte çalışma bir derlemeden katıştırılmış genel bir parametre türleri, dış bir derlemeden tür olan kullanılamaz. Bu kısıtlama, arabirimler için geçerli değil. Örneğin, göz önünde bulundurun <xref:Microsoft.Office.Interop.Excel.Range> tanımlanan arabirimi <xref:Microsoft.Office.Interop.Excel> derleme. Birlikte çalışma türlerini kitaplık katıştırır, <xref:Microsoft.Office.Interop.Excel> derleme ve bir parametreye sahip genel bir tür, türü döndüren bir yöntem sunarsa <xref:Microsoft.Office.Interop.Excel.Range> arabirim, yöntem aşağıdaki kod örneğinde gösterildiği gibi genel bir arabirim döndürmelidir.  
  
 [!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 Aşağıdaki örnekte, istemci kodu döndürür yöntemini çağırabilir <xref:System.Collections.IList> hatasız genel arabirim.  
  
 [!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod kaynak dosyasını derler `OfficeApp.vb` ve başvuru derlemelerden `COMData1.dll` ve `COMData2.dll` üretmek için `OfficeApp.exe`.  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [İzlenecek yol: Yönetilen derlemelerden türler katıştırma](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [/ Libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)  
 [Örnek derleme komut satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [COM birlikte çalışma giriş](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
