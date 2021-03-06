---
title: "Bir Entity Framework veri sağlayıcısı yazma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 80f425f6e2a9d583ec221b91ae9bb2cd2604ff54
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="writing-an-entity-framework-data-provider"></a>Bir Entity Framework veri sağlayıcısı yazma
Bu bölümde nasıl yazılacağından bir [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] dışında bir veri kaynağı desteklemek için sağlayıcı [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Destekleyen bir sağlayıcı içerir [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Entity Framework sağlayıcı modeline giriş  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Veritabanı bağımsızdır ve farklı veri kaynakları kümesine bağlanmak için ADO.NET sağlayıcısı modeli kullanarak bir sağlayıcı yazabilirsiniz.  
  
 Entity Framework veri sağlayıcısı (ADO.NET veri sağlayıcı modeli kullanılarak oluşturulan) aşağıdaki işlevleri gerçekleştirir:  
  
-   Varlık veri modeli (EDM) ilkel türler sağlayıcısı türleri ile eşleştirir.  
  
-   Sağlayıcıya özgü işlevleri kullanıma sunar.  
  
-   Sağlayıcıya özgü komutlar desteklemek belirli bir DbQueryCommandTree için oluşturur [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] sorgular.  
  
-   Sağlayıcıya özgü güncelleştirme komutları aracılığıyla güncelleştirmeleri desteklemek belirli bir DbModificationCommandTree için oluşturur [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
-   Bir veritabanını temel alan bir model oluşturulmasını desteklemek için depolama şema tanımı için dosyaları eşleme açığa çıkarır.  
  
-   Meta verileri (tablolar ve görünümler, örneğin) yoluyla kavramsal model kullanıma sunar.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Örnek  
 Bkz: [Entity Framework örnek sağlayıcısı](http://go.microsoft.com/fwlink/?LinkId=180616) örneği için bir [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] dışında bir veri kaynağı destekleyen sağlayıcı [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [SQL Üretimi](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [Değişiklik SQL Oluşturma](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Sağlayıcı Bildirimi Belirtimi](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Sağlayıcılarıyla Çalışma](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
