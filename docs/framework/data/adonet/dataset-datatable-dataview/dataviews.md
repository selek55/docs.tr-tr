---
title: DataViews
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a>DataViews
A <xref:System.Data.DataView> depolanan verilerin farklı görünümlerini oluşturmanızı sağlayan bir <xref:System.Data.DataTable>, veri bağlama uygulamalarında sık kullanılan bir özellik. Kullanarak bir **DataView**farklı sıralamalar olan bir tabloda veri getirebilir ve veri satırı durum ya da bir filtre ifadesi göre göre filtre uygulayabilirsiniz.  
  
 A **DataView** temel veri dinamik bir görünümünü sunan **DataTable**: Bunlar ortaya çıktığında içerik, sıralama ve üyelik değişiklikleri yansıtacak. Bu davranış farklı **seçin** yöntemi **DataTable**, döndüren bir <xref:System.Data.DataRow> bir tablo diziden dayalı üzerinde belirli bir filtre ve/veya sıralama düzeni: thiscontent değişiklikleri yansıtır Tablo, ancak üyeliğini temel ve sıralama statik kalır. Dinamik özelliklerini **DataView** veri bağlama uygulamaları için ideal olun.  
  
 A **DataView** için uygulayabileceğiniz farklı sıralama ve filtreleme ölçütlerini çok bir veritabanı görünüm gibi verileri tek bir dizi dinamik bir görünümünü sağlar. Ancak, bir veritabanı görünümü aksine bir **DataView** tablo olarak kabul edilemiyor ve birleştirilmiş tablolar görünümünü sağlayamaz. Ayrıca kaynak tablo mevcut sütunları dışlanamaz veya kaynak tabloda bulunmayan hesaplama sütunlar gibi sütunları ekleyebilirsiniz.  
  
 Kullanabileceğiniz bir <xref:System.Data.DataView.DataViewManager%2A> tüm tablolarda görünüm ayarlarını yönetmek için bir **DataSet**. **DataViewManager** her tablo için varsayılan görünüm ayarlarını yönetmek için kolay bir yol sağlar. Bir denetim birden fazla tabloya bağlanırken bir **DataSet**, bağlayıcı için bir **DataViewManager** ideal bir seçimdir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [DataView Oluşturma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Nasıl oluşturulacağını açıklar bir **DataView** için bir **DataTable**.  
  
 [Verileri Sıralama ve Filtreleme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Özelliklerini ayarlamak açıklar bir **DataView** veri satır kümelerine belirli filtre ölçütlere geri dönmek için veya belirli bir sıralama düzeni içinde verileri döndürmek için.  
  
 [DataRows ve DataRowViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Tarafından sunulan veri erişim açıklar **DataView**.  
  
 [Satırları Bulma](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Belirli bir satır bulmak açıklar bir **DataView**.  
  
 [ChildViews ve İlişkileri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Veri görünümleri kullanarak bir üst-alt ilişkisi oluşturmayı açıklar bir **DataView**.  
  
 [DataView Değiştirme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Temel veri değiştirmeyi açıklar **DataTable** aracılığıyla **DataView**etkinleştirerek veya devre dışı güncelleştirmeler dahil olmak üzere.  
  
 [DataView Olaylarını İşleme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Nasıl kullanılacağını açıklar **ListChanged** bildirim almak için olay olduğunda içeriği veya sırasını bir **DataView** güncelleştiriliyor.  
  
 [DataView Yönetme](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Nasıl kullanılacağını açıklar bir **DataViewManager** yönetmek için **DataView** ayarları her tablo için bir **DataSet**.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ASP.NET Web uygulamaları](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 ASP.NET uygulamaları, Web formları ve Web hizmetleri oluşturmak için genel bakışlar ve ayrıntılı, adım adım yordamlar sağlar.  
  
 [Windows uygulamaları](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Windows Forms ve konsol uygulamaları ile çalışma hakkında ayrıntılı bilgi sağlar.  
  
 [DataSets, DataTables ve DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Açıklar **DataSet** nesne ve uygulama verilerini yönetmek için nasıl kullanabilirsiniz.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Açıklar **DataTable** nesne ve tek başına ya da bir parçası olarak uygulama verilerini yönetmek için nasıl kullanabileceğiniz bir **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 ADO.NET açıklar mimarisi ve bileşenleri ve ADO.NET mevcut veri kaynaklarına erişmek ve uygulama verilerini yönetmek için nasıl kullanılacağını.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
