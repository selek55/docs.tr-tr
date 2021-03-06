---
title: "OLE DB şeması koleksiyonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 33e794559abd7f619f7431683f06e59705b57d41
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="ole-db-schema-collections"></a>OLE DB şeması koleksiyonları
Bu bölümde, Microsoft SQL Server, Oracle ve Microsoft Jet için OLE DB sağlayıcıları şema koleksiyonu desteği açıklanmaktadır.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Microsoft SQL Server OLE DB sağlayıcısı  
 Microsoft SQL Server OLE DB sürücüsü ortak şeması koleksiyonları ek olarak aşağıdaki belirli şeması koleksiyonları destekler:  
  
-   tabloları  
  
-   Sütunlar  
  
-   Yordamlar  
  
-   ProcedureParameters  
  
-   Katalog  
  
-   Dizinler  
  
### <a name="tables"></a>tabloları  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|TABLE_TYPE|Dize|  
|TABLE_GUID|Guid|  
|AÇIKLAMA|Dize|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Sütunlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boole değeri|  
|COLUMN_DEFAULT|Dize|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boole değeri|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Dize|  
|CHARACTER_SET_SCHEMA|Dize|  
|CHARACTER_SET_NAME|Dize|  
|COLLATION_CATALOG|Dize|  
|COLLATION_SCHEMA|Dize|  
|COLLATION_NAME|Dize|  
|DOMAIN_CATALOG|Dize|  
|DOMAIN_SCHEMA|Dize|  
|DOMAIN_NAME|Dize|  
|AÇIKLAMA|Dize|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte]|  
|IS_COMPUTED|Boole değeri|  
  
### <a name="procedures"></a>Yordamlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Dize|  
|PROCEDURE_SCHEMA|Dize|  
|PROCEDURE_NAME|Dize|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Dize|  
|AÇIKLAMA|Dize|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|columnName|Veri türü|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Dize|  
|PROCEDURE_SCHEMA|Dize|  
|PROCEDURE_NAME|Dize|  
|PARAMETER_NAME|Dize|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boole değeri|  
|PARAMETER_DEFAULT|Dize|  
|IS_NULLABLE|Boole değeri|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|AÇIKLAMA|Dize|  
|TYPE_NAME|Dize|  
|LOCAL_TYPE_NAME|Dize|  
  
### <a name="catalog"></a>Katalog  
  
|columnName|Veri türü|  
|----------------|--------------|  
|CATALOG_NAME|Dize|  
|AÇIKLAMA|Dize|  
  
### <a name="indexes"></a>Dizinler  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|INDEX_CATALOG|Dize|  
|INDEX_SCHEMA|Dize|  
|INDEX_NAME|Dize|  
|PRIMARY_KEY|Boole değeri|  
|UNIQUE|Boole değeri|  
|CLUSTERED|Boole değeri|  
|TÜRÜ|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boole değeri|  
|AUTO_UPDATE|Boole değeri|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|HARMANLAMA|Int16|  
|ÖNEM DÜZEYİ|Ondalık|  
|SAYFALARI|Int32|  
|FILTER_CONDITION|Dize|  
|TÜMLEŞİK|Boole değeri|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Microsoft Oracle OLE DB Provider  
 Microsoft Oracle OLE DB sürücü ortak şeması koleksiyonları ek olarak aşağıdaki belirli şeması koleksiyonları destekler:  
  
-   tabloları  
  
-   Sütunlar  
  
-   Yordamlar  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Görünümler  
  
-   Dizinler  
  
### <a name="tables"></a>tabloları  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|TABLE_TYPE|Dize|  
|TABLE_GUID|Guid|  
|AÇIKLAMA|Dize|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Sütunlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boole değeri|  
|COLUMN_DEFAULT|Dize|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boole değeri|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Dize|  
|CHARACTER_SET_SCHEMA|Dize|  
|CHARACTER_SET_NAME|Dize|  
|COLLATION_CATALOG|Dize|  
|COLLATION_SCHEMA|Dize|  
|COLLATION_NAME|Dize|  
|DOMAIN_CATALOG|Dize|  
|DOMAIN_SCHEMA|Dize|  
|DOMAIN_NAME|Dize|  
|AÇIKLAMA|Dize|  
  
### <a name="procedures"></a>Yordamlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Dize|  
|PROCEDURE_SCHEMA|Dize|  
|PROCEDURE_NAME|Dize|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Dize|  
|AÇIKLAMA|Dize|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|columnName|Veri türü|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Dize|  
|PROCEDURE_SCHEMA|Dize|  
|PROCEDURE_NAME|Dize|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boole değeri|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|AÇIKLAMA|Dize|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Görünümler  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|VIEW_DEFINITION|Dize|  
|CHECK_OPTION|Boole değeri|  
|IS_UPDATABLE|Boole değeri|  
|AÇIKLAMA|Dize|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Dizinler  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|INDEX_CATALOG|Dize|  
|INDEX_SCHEMA|Dize|  
|INDEX_NAME|Dize|  
|PRIMARY_KEY|Boole değeri|  
|UNIQUE|Boole değeri|  
|CLUSTERED|Boole değeri|  
|TÜRÜ|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boole değeri|  
|AUTO_UPDATE|Boole değeri|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|HARMANLAMA|Int16|  
|ÖNEM DÜZEYİ|Ondalık|  
|SAYFALARI|Int32|  
|FILTER_CONDITION|Dize|  
|TÜMLEŞİK|Boole değeri|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Microsoft Jet OLE DB sağlayıcısı  
 Microsoft Jet OLE DB sürücü ortak şeması koleksiyonları ek olarak aşağıdaki belirli şeması koleksiyonları destekler:  
  
-   tabloları  
  
-   Sütunlar  
  
-   Yordamlar  
  
-   Görünümler  
  
-   Dizinler  
  
### <a name="tables"></a>tabloları  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|TABLE_TYPE|Dize|  
|TABLE_GUID|Guid|  
|AÇIKLAMA|Dize|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Sütunlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boole değeri|  
|COLUMN_DEFAULT|Dize|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boole değeri|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Dize|  
|CHARACTER_SET_SCHEMA|Dize|  
|CHARACTER_SET_NAME|Dize|  
|COLLATION_CATALOG|Dize|  
|COLLATION_SCHEMA|Dize|  
|COLLATION_NAME|Dize|  
|DOMAIN_CATALOG|Dize|  
|DOMAIN_SCHEMA|Dize|  
|DOMAIN_NAME|Dize|  
|AÇIKLAMA|Dize|  
  
### <a name="procedures"></a>Yordamlar  
  
|columnName|Veri türü|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Dize|  
|PROCEDURE_SCHEMA|Dize|  
|PROCEDURE_NAME|Dize|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Dize|  
|AÇIKLAMA|Dize|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Görünümler  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|VIEW_DEFINITION|Dize|  
|CHECK_OPTION|Boole değeri|  
|IS_UPDATABLE|Boole değeri|  
|AÇIKLAMA|Dize|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Dizinler  
  
|columnName|Veri türü|  
|----------------|--------------|  
|TABLE_CATALOG|Dize|  
|TABLE_SCHEMA|Dize|  
|TABLE_NAME|Dize|  
|INDEX_CATALOG|Dize|  
|INDEX_SCHEMA|Dize|  
|INDEX_NAME|Dize|  
|PRIMARY_KEY|Boole değeri|  
|UNIQUE|Boole değeri|  
|CLUSTERED|Boole değeri|  
|TÜRÜ|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boole değeri|  
|AUTO_UPDATE|Boole değeri|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Dize|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|HARMANLAMA|Int16|  
|ÖNEM DÜZEYİ|Ondalık|  
|SAYFALARI|Int32|  
|FILTER_CONDITION|Dize|  
|TÜMLEŞİK|Boole değeri|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
