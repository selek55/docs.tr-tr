---
title: "Gelişmiş İlkesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dd941509c37618480a20530d3f5239750917e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="advanced-policy"></a><span data-ttu-id="cfb50-102">Gelişmiş İlkesi</span><span class="sxs-lookup"><span data-stu-id="cfb50-102">Advanced Policy</span></span>
<span data-ttu-id="cfb50-103">Bu örnekte basit ilke örnek genişletir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="cfb50-104">Konut indirim ve iş indirim kuralları basit ilke örneğindeki ek olarak, çeşitli yeni kurallar eklenmiştir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="cfb50-105">Yüksek değerli siparişleri büyük indirimi sağlayan bir yüksek değerli kuralı eklenir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="cfb50-106">Bir öncelik değeri verildiğinde'dan önceki iki kuralları indirim alanın üzerine ve hem konut üzerinden öncelik ve iş indirim kuralları.</span><span class="sxs-lookup"><span data-stu-id="cfb50-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="cfb50-107">Bir hesapla toplam kuralı Ayrıca, hangi indirim düzeyi temelinde toplam hesaplar eklenir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="cfb50-108">İş akışı etkinliğini tanımlanmış bir yöntem başvuru nasıl gibi başka eylemler kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="cfb50-109">Bu kural, ayrıca, olacağından davranışı zincirleme dilediğiniz zaman indirim alan değişiklikleri hesaplanan gösterir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="cfb50-110">Ayrıca, yöntemi öznitelik atanıyor RuleWriteAttribute CalculateTotal yöntemi gösterilir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="cfb50-111">Bu, etkilenen kurallar yöntemi yürütülen her yeniden değerlendirilecek (ErrorTotalRule) neden olur.</span><span class="sxs-lookup"><span data-stu-id="cfb50-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="cfb50-112">Eklenen son kural hataları (Bu durumda, toplam 0'dan) algılarsa biridir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="cfb50-113">Bu durumda, ilke yürütme işlemi durduruldu.</span><span class="sxs-lookup"><span data-stu-id="cfb50-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="cfb50-114">Son olarak, `Console.Writeline` çağrıları, kural yürütme daha fazla görünürlük sağlamak için her bir kural eylemleri olarak eklenir, mümkün olmadığını da gösterirken statik yöntemler'na erişmek için türleri başvurulan.</span><span class="sxs-lookup"><span data-stu-id="cfb50-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="cfb50-115">İzleme, yürütülen kurallara görünürlük almak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cfb50-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="cfb50-116">Bu örnekte kullanılan kurallar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="cfb50-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="cfb50-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="cfb50-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="cfb50-118">Eğer sipariş değeri olarak > 500 ve CustomerType konut =</span><span class="sxs-lookup"><span data-stu-id="cfb50-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="cfb50-119">ARDINDAN indirim = % 5</span><span class="sxs-lookup"><span data-stu-id="cfb50-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="cfb50-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="cfb50-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="cfb50-121">Eğer sipariş değeri olarak > 10000 ve CustomerType iş =</span><span class="sxs-lookup"><span data-stu-id="cfb50-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="cfb50-122">ARDINDAN indirim = % 10</span><span class="sxs-lookup"><span data-stu-id="cfb50-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="cfb50-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="cfb50-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="cfb50-124">Eğer sipariş değeri olarak > 20000</span><span class="sxs-lookup"><span data-stu-id="cfb50-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="cfb50-125">ARDINDAN indirim % 15 =</span><span class="sxs-lookup"><span data-stu-id="cfb50-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="cfb50-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="cfb50-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="cfb50-127">Eğer indirim > 0</span><span class="sxs-lookup"><span data-stu-id="cfb50-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="cfb50-128">ARDINDAN CalculateTotal (sipariş değeri olarak, indirim)</span><span class="sxs-lookup"><span data-stu-id="cfb50-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="cfb50-129">ELSE toplam sipariş değeri olarak =</span><span class="sxs-lookup"><span data-stu-id="cfb50-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="cfb50-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="cfb50-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="cfb50-131">Eğer toplam \< 0</span><span class="sxs-lookup"><span data-stu-id="cfb50-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="cfb50-132">ARDINDAN hata = "ErrorTotalRule harekete"; Durdurma</span><span class="sxs-lookup"><span data-stu-id="cfb50-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="cfb50-133">Kural değerlendirmesi ve yürütme, ayrıca izleme ve izleme görülebilir.</span><span class="sxs-lookup"><span data-stu-id="cfb50-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="cfb50-134">Örneği oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="cfb50-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="cfb50-135">Çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfb50-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cfb50-136">CTRL + SHIFT + B tuşlarına basarak çözümü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cfb50-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="cfb50-137">CTRL + F5'e basarak hata ayıklama olmadan çözümü çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="cfb50-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="cfb50-138">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="cfb50-138">To run the sample</span></span>  
  
-   <span data-ttu-id="cfb50-139">Örnek için ana klasörü altında bulunan .exe dosyasını AdvancedPolicy\bin\debug klasöründe (veya örnek Visual Basic sürümü AdvancedPolicy \bin klasörünü) SDK komut istemi penceresinde çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="cfb50-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cfb50-140">Örnekler, bilgisayarınızda yüklü.</span><span class="sxs-lookup"><span data-stu-id="cfb50-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cfb50-141">Devam etmeden önce aşağıdaki (varsayılan) dizin denetle:</span><span class="sxs-lookup"><span data-stu-id="cfb50-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cfb50-142">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="cfb50-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cfb50-143">Bu örnek aşağıdaki dizinde bulunur:</span><span class="sxs-lookup"><span data-stu-id="cfb50-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="cfb50-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cfb50-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="cfb50-145">Basit İlkesi</span><span class="sxs-lookup"><span data-stu-id="cfb50-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)