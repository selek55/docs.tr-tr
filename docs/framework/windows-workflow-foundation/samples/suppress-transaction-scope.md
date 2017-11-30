---
title: "İşlem kapsamı gösterme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e95262fc1aee6efb6fe63f06530b70c7c16f64b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="suppress-transaction-scope"></a><span data-ttu-id="15e75-102">İşlem kapsamı gösterme</span><span class="sxs-lookup"><span data-stu-id="15e75-102">Suppress Transaction Scope</span></span>
<span data-ttu-id="15e75-103">Örnek özel bir yazar gösterilmiştir `SuppressTransactionScope` ortam çalıştırma işlem varsa gizlemek için etkinlik.</span><span class="sxs-lookup"><span data-stu-id="15e75-103">The sample demonstrates how to author a custom `SuppressTransactionScope` activity to suppress the ambient run-time transaction, if present.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15e75-104">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="15e75-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="15e75-105">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="15e75-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="15e75-106">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="15e75-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15e75-107">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="15e75-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a><span data-ttu-id="15e75-108">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="15e75-108">Sample Details</span></span>  
 <span data-ttu-id="15e75-109">Özel Etkinlik işlem akışını belirli bir senaryo için istenmeyen ise çıkışı başka bir hizmete aktarılan gelen bir işlem önlemek kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="15e75-109">The custom activity is useful to prevent a transaction from being flowed out to another service if transaction flow is undesirable for the particular scenario.</span></span> <span data-ttu-id="15e75-110">İş akışı çalışma zamanı ortam işlemde gizleme için yerleşik destek sahip <xref:System.Activities.NativeActivity> için özel bir yazma işlemi gerçekleştirmek gerekli olduğu bu destek kullanabilir ancak sınıfı <xref:System.Activities.NativeActivity> Bu örnek bir gibi.</span><span class="sxs-lookup"><span data-stu-id="15e75-110">The workflow runtime has built-in support for suppressing the ambient transaction in the <xref:System.Activities.NativeActivity> class, but to use this support it is necessary to author a custom <xref:System.Activities.NativeActivity> such as the one in this sample.</span></span>  
  
 <span data-ttu-id="15e75-111">Senaryo üç bölümden oluşur.</span><span class="sxs-lookup"><span data-stu-id="15e75-111">The scenario consists of three parts.</span></span> <span data-ttu-id="15e75-112">İlk olarak, bir <xref:System.Activities.Statements.TransactionScope> ortam hale bir çalışma zamanı işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="15e75-112">First, a <xref:System.Activities.Statements.TransactionScope> creates a run-time transaction that becomes ambient.</span></span> <span data-ttu-id="15e75-113">Bu işlem yerel ve dağıtılmış tanımlayıcıların yazdırır özel bir etkinlik tarafından doğrulanır.</span><span class="sxs-lookup"><span data-stu-id="15e75-113">This is verified by a custom activity that prints the local and distributed identifiers of the transaction.</span></span> <span data-ttu-id="15e75-114">Uzak hizmet için ikinci bölümü başlamadan önce işlem sonra aktarılan.</span><span class="sxs-lookup"><span data-stu-id="15e75-114">The transaction is then flowed to a remote service before beginning the second part.</span></span> <span data-ttu-id="15e75-115">İş akışı sırasında ikinci bölümü, girer bir `SuppressTransactionScope` ve yeniden hareketi tanımlayıcıları yazdırma ve işlem akan işlemi yinelenir.</span><span class="sxs-lookup"><span data-stu-id="15e75-115">During the second part, the workflow enters a `SuppressTransactionScope` and again repeats the process of printing the transaction identifiers and flowing the transaction.</span></span> <span data-ttu-id="15e75-116">Ancak, özel etkinlik bir ortam işlem bulamaz ve ileti akışı yapılan işlem hizmeti işlem içermiyor.</span><span class="sxs-lookup"><span data-stu-id="15e75-116">However, the custom activity does not find an ambient transaction and the message flowed to the service does not contain the transaction.</span></span> <span data-ttu-id="15e75-117">Sonuç olarak, hizmet anlamına gelir istemci ve hizmet üzerinde dağıtılmış kimliği yazdırılan eşleşmeyen bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="15e75-117">As a result, the service creates a transaction, which means the distributed ID printed on the client and service do not match.</span></span> <span data-ttu-id="15e75-118">Son bölümü sonra oluşan `SuppressTransactionScope` çıkar ve yeniden çalışma zamanı işlem başka bir ileti ilk iletinin tanımlayıcısı ile eşleşen dağıtılmış bir tanımlayıcı ile hizmetine tarafından doğrulanmış ortam olur.</span><span class="sxs-lookup"><span data-stu-id="15e75-118">The final part occurs after the `SuppressTransactionScope` exits and the run-time transaction again becomes ambient as verified by another message to the service with a distributed identifier that matches the identifier of the first message.</span></span>  
  
 <span data-ttu-id="15e75-119">Etkinlik türetilen <xref:System.Activities.NativeActivity> bir alt etkinlik zamanlama gerekir ve bir yürütme özelliği eklemek için.</span><span class="sxs-lookup"><span data-stu-id="15e75-119">The activity itself derives from <xref:System.Activities.NativeActivity> because it must schedule a child activity and add an execution property.</span></span> <span data-ttu-id="15e75-120">`SuppressTransactionScope` Sahip bir <xref:System.Activities.Variable> türü <xref:System.Activities.RuntimeTransactionHandle>, hangi kullanılmalıdır türü yerine bir örnek alanındaki <xref:System.Activities.RuntimeTransactionHandle> tanıtıcı başlatılmış olduğundan.</span><span class="sxs-lookup"><span data-stu-id="15e75-120">The `SuppressTransactionScope` has a <xref:System.Activities.Variable> of type <xref:System.Activities.RuntimeTransactionHandle>, which must be used rather than an instance field of type <xref:System.Activities.RuntimeTransactionHandle> because the handle must be initialized.</span></span> <span data-ttu-id="15e75-121">`Variable<RuntimeTransactionHandle>` , Yalnızca dahili olarak kullanıldığından etkinliğe ilişkin meta verileri için bir uygulama değişkeni olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="15e75-121">The `Variable<RuntimeTransactionHandle>` is added to the activity’s metadata as an implementation variable because it is only used internally.</span></span>  
  
 <span data-ttu-id="15e75-122">Etkinlik çalıştırıldığında, önce bir gövde belirtilmiş olup olmadığını görmek için denetler ve varsa, ayarlar `SuppressTransaction` özelliği <xref:System.Activities.RuntimeTransactionHandle>.</span><span class="sxs-lookup"><span data-stu-id="15e75-122">When the activity is executed it first checks to see whether a body was specified and if so, sets the `SuppressTransaction` property on the <xref:System.Activities.RuntimeTransactionHandle>.</span></span> <span data-ttu-id="15e75-123">Özellik ayarlandıktan sonra yürütme özelliklerine eklenir ve ortam olur.</span><span class="sxs-lookup"><span data-stu-id="15e75-123">Once the property is set, it is added to the execution properties and becomes ambient.</span></span> <span data-ttu-id="15e75-124">Bir alt olan herhangi bir etkinlik buna `SuppressTransactionScope` özelliği görmeye ve bu nedenle çalışma zamanı işlem gizleme zorlar ve iç içe bir neden <xref:System.Activities.Statements.TransactionScope> bir özel durum için.</span><span class="sxs-lookup"><span data-stu-id="15e75-124">This means that any activity that is a child of the `SuppressTransactionScope` is able to see the property and therefore enforces the suppression of the run-time transaction and causes a nested <xref:System.Activities.Statements.TransactionScope> to throw an exception.</span></span> <span data-ttu-id="15e75-125">Tanıtıcı gövdesi çalışacak şekilde zamanlanır yürütme özelliklerine eklendikten sonra.</span><span class="sxs-lookup"><span data-stu-id="15e75-125">Once the handle is added to the execution properties the body is scheduled to run.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="15e75-126">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="15e75-126">To use this sample</span></span>  
  
1.  <span data-ttu-id="15e75-127">SuppressTransactionScope.sln çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15e75-127">Open the SuppressTransactionScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="15e75-128">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın veya seçin **yapı çözümü** gelen **yapı** menüsü.</span><span class="sxs-lookup"><span data-stu-id="15e75-128">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="15e75-129">Derleme başarılı olduktan sonra çözüme sağ tıklayın ve seçin **başlangıç projelerini Ayarla**.</span><span class="sxs-lookup"><span data-stu-id="15e75-129">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="15e75-130">İletişim kutusundan seçin **birden fazla başlangıç projesi** ve her iki projeleri için eylem olun **Başlat**.</span><span class="sxs-lookup"><span data-stu-id="15e75-130">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="15e75-131">F5 tuşuna basın veya seçin **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.</span><span class="sxs-lookup"><span data-stu-id="15e75-131">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="15e75-132">Alternatif olarak, CTRL + F5 tuşuna basın veya seçin **hata ayıklama olmadan Başlat** gelen **hata ayıklama** menü hata ayıklama olmadan çalıştırma.</span><span class="sxs-lookup"><span data-stu-id="15e75-132">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15e75-133">Sunucu, istemci başlatmadan önce çalışmalıdır.</span><span class="sxs-lookup"><span data-stu-id="15e75-133">The server must be running prior to starting the client.</span></span> <span data-ttu-id="15e75-134">Hizmeti barındıran konsol penceresi çıktısı ne zaman başlatıldığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="15e75-134">The output from the console window that hosts the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15e75-135">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="15e75-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="15e75-136">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="15e75-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="15e75-137">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="15e75-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15e75-138">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="15e75-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="see-also"></a><span data-ttu-id="15e75-139">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="15e75-139">See Also</span></span>