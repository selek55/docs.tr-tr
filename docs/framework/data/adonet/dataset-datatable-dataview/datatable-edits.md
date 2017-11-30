---
title: "DataTable düzenlemeler"
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d33bd8900c48222142a46ed2c5bd64412d2eaab5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-edits"></a><span data-ttu-id="11185-102">DataTable düzenlemeler</span><span class="sxs-lookup"><span data-stu-id="11185-102">DataTable Edits</span></span>
<span data-ttu-id="11185-103">Değişiklikler yaptığınızda sütun değerleri için bir <xref:System.Data.DataRow>, değişiklikleri hemen satır geçerli durumunda yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="11185-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="11185-104"><xref:System.Data.DataRowState> Sonra ayarlanır **değiştirilen**, değişiklikleri kabul veya kullanarak <xref:System.Data.DataRow.AcceptChanges%2A> veya <xref:System.Data.DataRow.RejectChanges%2A> yöntemlerinin **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="11185-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="11185-105">**DataRow** da Siz düzenlerken satır durumunu askıya almak için kullanabileceğiniz üç yöntem sunar.</span><span class="sxs-lookup"><span data-stu-id="11185-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="11185-106">Bu yöntemler <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, ve <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="11185-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="11185-107">Sütun değerleri değiştirdiğinizde bir **DataRow** doğrudan **DataRow** kullanarak sütun değerlerini yönetir **geçerli**, **varsayılan**, ve **Özgün** satır sürümleri.</span><span class="sxs-lookup"><span data-stu-id="11185-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="11185-108">Bu satır sürümleri yanı sıra **BeginEdit**, **EndEdit**, ve **CancelEdit** dördüncü bir satır sürümü yöntemleri kullanın: **önerilen**.</span><span class="sxs-lookup"><span data-stu-id="11185-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="11185-109">Satır sürümleri hakkında daha fazla bilgi için bkz: [satır durumları ve satır sürümleri](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="11185-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="11185-110">**Önerilen** satır sürümü var. çağırarak başlayan bir düzenleme işlemi sırasında **BeginEdit** ve kullanarak ya da sona **EndEdit** veya **CancelEdit,**  veya çağırarak **AcceptChanges** veya **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="11185-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="11185-111">Düzenleme işlemi sırasında doğrulama mantığını tek tek sütun değerlendirerek uygulayabilirsiniz **ProposedValue** içinde **ColumnChanged** olayı **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="11185-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="11185-112">**ColumnChanged** olay tutan **DataColumnChangeEventArgs** değiştiriyor. sütun ve için bir başvuru tutun **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="11185-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="11185-113">Önerilen değer değerlendirdikten sonra değiştirmek veya düzenlemeyi iptal etmek.</span><span class="sxs-lookup"><span data-stu-id="11185-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="11185-114">Düzen sona erdikten sonra satır dışı taşır **önerilen** durumu.</span><span class="sxs-lookup"><span data-stu-id="11185-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="11185-115">Çağırarak düzenlemeleri onaylayabilirsiniz **EndEdit**, veya bunları çağırarak iptal **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="11185-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="11185-116">Unutmayın, while **EndEdit** yaptığınız düzenlemeleri onaylamak **DataSet** gerçekten değişinceye kadar kabul etmiyorum **AcceptChanges** olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="11185-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="11185-117">Çağırırsanız ayrıca **AcceptChanges** düzenleme sona ermeden önce **EndEdit** veya **CancelEdit**, Düzen sona erdi ve **önerilen** satır değerleri için her ikisini de kabul edilir **geçerli** ve **özgün** satır sürümleri.</span><span class="sxs-lookup"><span data-stu-id="11185-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="11185-118">Aynı şekilde çağırma **RejectChanges** düzenleme sona erer ve atar **geçerli** ve **önerilen** satır sürümleri.</span><span class="sxs-lookup"><span data-stu-id="11185-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="11185-119">Çağırma **EndEdit** veya **CancelEdit** çağırdıktan sonra **AcceptChanges** veya **RejectChanges** düzenleme zaten sahip olduğu herhangi bir etkisi olmaz. sona erdi.</span><span class="sxs-lookup"><span data-stu-id="11185-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="11185-120">Aşağıdaki örnekte nasıl kullanılacağı ortaya **BeginEdit** ile **EndEdit** ve **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="11185-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="11185-121">Bu örnek ayrıca denetler **ProposedValue** içinde **ColumnChanged** olay ve düzenlemeyi iptal etmek mi karar verir.</span><span class="sxs-lookup"><span data-stu-id="11185-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="11185-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="11185-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="11185-123">Bir DataTable tablosundaki verileri düzenleme</span><span class="sxs-lookup"><span data-stu-id="11185-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="11185-124">DataTable olayları işleme</span><span class="sxs-lookup"><span data-stu-id="11185-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="11185-125">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="11185-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)