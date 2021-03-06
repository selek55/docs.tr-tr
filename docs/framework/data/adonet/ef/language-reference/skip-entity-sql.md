---
title: "Atla (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0dd0754158000642dd078f00033c9ddc2f78686d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="skip-entity-sql"></a>Atla (varlık SQL)
Fiziksel disk belleği ORDER BY yan tümcesinde SKIP alt yan tümcesinin kullanarak gerçekleştirebilirsiniz. Atla ayrı olarak from ORDER BY yan tümcesi kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a>Arguments  
 `n`  
 Atlanacak öğe sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 SKIP ifadesi alt yan ORDER BY yan tümcesinde varsa, sonuçları sıralama belirtimine göre sıralanır ve sonuç kümesi satır hemen sonra SKIP ifadesi sonraki satırdan başlayarak dahil edilir. Örneğin, Atla 5 ilk beş satırını atlar ve İleri altıncı satırdaki döndürür.  
  
> [!NOTE]
>  Bir [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sorgu üst değiştirici ve SKIP alt yan tümcesinin aynı sorgu ifadesinde mevcut olup olmadığını geçerli değil. Sorgu TOP ifadesi için sınır ifade değiştirerek yazılması.  
  
> [!NOTE]
>  İçinde [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], anahtar olmayan sütunlarda ORDER BY ile Atla kullanarak hatalı sonuçlar döndürebilir. Anahtar olmayan sütun yinelenen verileri varsa satır belirtilen sayıdan daha fazla atlanabilir. Nasıl Atla için çevrilir nedeniyle budur [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]. Örneğin, aşağıdaki kodda beşten fazla satır, atlanabilir `E.NonKeyColumn` yinelenen değerleri içeriyor:  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] İçinde sorgu [bu](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) örnek bir SELECT deyiminde döndürülen nesne üzerinde kullanılan sıralama düzenini belirlemek için Atla ile ORDER BY işleci kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Nasıl yapılır: sonuçları sorgu aracılığıyla sayfası](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Disk Belleği](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
