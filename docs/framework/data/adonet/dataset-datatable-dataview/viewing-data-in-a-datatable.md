---
title: "Bir DataTable tablosundaki verileri görüntüleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 147d6fb4509913de1f0331ce2ff6c580c6e41ef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="bca58-102">Bir DataTable tablosundaki verileri görüntüleme</span><span class="sxs-lookup"><span data-stu-id="bca58-102">Viewing Data in a DataTable</span></span>
<span data-ttu-id="bca58-103">İçeriğine erişmek için bir <xref:System.Data.DataTable> kullanarak **satırları** ve **sütunları** koleksiyonları **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="bca58-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="bca58-104">Aynı zamanda <xref:System.Data.DataTable.Select%2A> veri alt kümesi döndürülecek yöntemi bir **DataTable** arama ölçütleri gibi ölçütlere göre sıralama ve satır durumu.</span><span class="sxs-lookup"><span data-stu-id="bca58-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="bca58-105">Ayrıca, kullanabileceğiniz <xref:System.Data.DataRowCollection.Find%2A> yöntemi **DataRowCollection** bir birincil anahtar değeri kullanarak belirli bir satır için arama yaparken.</span><span class="sxs-lookup"><span data-stu-id="bca58-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>  
  
 <span data-ttu-id="bca58-106">**Seçin** yöntemi **DataTable** nesnesi döndüren bir dizi <xref:System.Data.DataRow> belirtilen ölçütlerle eşleşen nesneler.</span><span class="sxs-lookup"><span data-stu-id="bca58-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="bca58-107">**Seçin** bir filtre ifadesi, sıralama ifadesi, isteğe bağlı bağımsız değişkenleri alır ve **DataViewRowState**.</span><span class="sxs-lookup"><span data-stu-id="bca58-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="bca58-108">Filtre ifadesi temel alınarak döndürülecek hangi satırların tanımlayan **DataColumn** gibi değerler `LastName = 'Smith'`.</span><span class="sxs-lookup"><span data-stu-id="bca58-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="bca58-109">Sütunları, örneğin sıralama için standart SQL kuralları sıralama ifadesi izler `LastName ASC, FirstName ASC`.</span><span class="sxs-lookup"><span data-stu-id="bca58-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="bca58-110">İfadeleri yazma hakkında daha fazla kuralları için bkz: <xref:System.Data.DataColumn.Expression%2A> özelliği **DataColumn** sınıfı.</span><span class="sxs-lookup"><span data-stu-id="bca58-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="bca58-111">Çağrı sayısı gerçekleştiriyorsanız **seçin** yöntemi bir **DataTable**, ilk oluşturarak performansı artırabilirsiniz bir <xref:System.Data.DataView> için **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="bca58-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="bca58-112">Oluşturma **DataView** tablonun satırlarını dizinler.</span><span class="sxs-lookup"><span data-stu-id="bca58-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="bca58-113">**Seçin** yöntemi sonra dizin, usees sorgu sonucu oluşturmak için gereken süre önemli ölçüde azaltır.</span><span class="sxs-lookup"><span data-stu-id="bca58-113">The **Select** method then usees that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="bca58-114">Oluşturma hakkında daha fazla bilgi için bir **DataView** için bir **DataTable**, bkz: [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="bca58-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 <span data-ttu-id="bca58-115">**Seçin** yöntemi belirler satırları görüntülemek veya değiştirmek için hangi sürümünün dayalı bir <xref:System.Data.DataViewRowState>.</span><span class="sxs-lookup"><span data-stu-id="bca58-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="bca58-116">Aşağıdaki tabloda olası açıklanmaktadır **DataViewRowState** numaralandırma değerleri.</span><span class="sxs-lookup"><span data-stu-id="bca58-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>  
  
|<span data-ttu-id="bca58-117">DataViewRowState değeri</span><span class="sxs-lookup"><span data-stu-id="bca58-117">DataViewRowState value</span></span>|<span data-ttu-id="bca58-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bca58-118">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="bca58-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="bca58-119">**CurrentRows**</span></span>|<span data-ttu-id="bca58-120">Geçerli satır değişmeden, eklenen ve değiştirilen satırları dahil olmak üzere.</span><span class="sxs-lookup"><span data-stu-id="bca58-120">Current rows including unchanged, added, and modified rows.</span></span>|  
|<span data-ttu-id="bca58-121">**Silindi**</span><span class="sxs-lookup"><span data-stu-id="bca58-121">**Deleted**</span></span>|<span data-ttu-id="bca58-122">Silinen satır.</span><span class="sxs-lookup"><span data-stu-id="bca58-122">A deleted row.</span></span>|  
|<span data-ttu-id="bca58-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="bca58-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="bca58-124">Özgün veriler değiştirilmiş bir sürümünü olan bir geçerli sürümü.</span><span class="sxs-lookup"><span data-stu-id="bca58-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="bca58-125">(Bkz **ModifiedOriginal**.)</span><span class="sxs-lookup"><span data-stu-id="bca58-125">(See **ModifiedOriginal**.)</span></span>|  
|<span data-ttu-id="bca58-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="bca58-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="bca58-127">Tüm değiştirilen satırları özgün sürümü.</span><span class="sxs-lookup"><span data-stu-id="bca58-127">The original version of all modified rows.</span></span> <span data-ttu-id="bca58-128">Geçerli sürümdür kullanılabilir kullanarak **ModifiedCurrent**.</span><span class="sxs-lookup"><span data-stu-id="bca58-128">The current version is available using **ModifiedCurrent**.</span></span>|  
|<span data-ttu-id="bca58-129">**Eklenen**</span><span class="sxs-lookup"><span data-stu-id="bca58-129">**Added**</span></span>|<span data-ttu-id="bca58-130">Yeni bir satır.</span><span class="sxs-lookup"><span data-stu-id="bca58-130">A new row.</span></span>|  
|<span data-ttu-id="bca58-131">**Yok**</span><span class="sxs-lookup"><span data-stu-id="bca58-131">**None**</span></span>|<span data-ttu-id="bca58-132">Yok.</span><span class="sxs-lookup"><span data-stu-id="bca58-132">None.</span></span>|  
|<span data-ttu-id="bca58-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="bca58-133">**OriginalRows**</span></span>|<span data-ttu-id="bca58-134">Özgün satırlar dahil olmak üzere, değiştirmeden ve silinen satır.</span><span class="sxs-lookup"><span data-stu-id="bca58-134">Original rows, including unchanged and deleted rows.</span></span>|  
|<span data-ttu-id="bca58-135">**Değişmedi**</span><span class="sxs-lookup"><span data-stu-id="bca58-135">**Unchanged**</span></span>|<span data-ttu-id="bca58-136">Değiştirilmemiş bir satır.</span><span class="sxs-lookup"><span data-stu-id="bca58-136">An unchanged row.</span></span>|  
  
 <span data-ttu-id="bca58-137">Aşağıdaki örnekte, **DataSet** böylece yalnızca satırlarla özelliği çalıştığınız nesne filtre **DataViewRowState** ayarlanır **CurrentRows**.</span><span class="sxs-lookup"><span data-stu-id="bca58-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 <span data-ttu-id="bca58-138">**Seçin** yöntemi, farklı olan satırlar döndürülecek kullanılabilir **RowState** değerleri veya alan değerleri.</span><span class="sxs-lookup"><span data-stu-id="bca58-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="bca58-139">Aşağıdaki örnek döndüren bir **DataRow** silinmiş ve başka döndüren tüm satırları başvuruda bulunan bir dizi **DataRow** tüm satırları başvuran dizi göre sıralayarak **CustLName**, burada **CustId** sütundur 5'ten büyük.</span><span class="sxs-lookup"><span data-stu-id="bca58-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="bca58-140">Bilgileri görüntüleme hakkında bilgi için **silinmiş** satır için bkz: [satır durumları ve satır sürümleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="bca58-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## <a name="see-also"></a><span data-ttu-id="bca58-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bca58-141">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [<span data-ttu-id="bca58-142">Bir DataTable tablosundaki verileri düzenleme</span><span class="sxs-lookup"><span data-stu-id="bca58-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="bca58-143">Satır durumları ve satır sürümleri</span><span class="sxs-lookup"><span data-stu-id="bca58-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [<span data-ttu-id="bca58-144">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="bca58-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)