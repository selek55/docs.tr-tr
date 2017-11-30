---
title: "Bir süre sonu öykünen etkinliği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4417f4225200f01f23d753f6b7aa52ebc69cab4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="4cb2b-102">Bir süre sonu öykünen etkinliği</span><span class="sxs-lookup"><span data-stu-id="4cb2b-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="4cb2b-103">Bu örnek, aşağıdaki etkinliklerin döngü mekanizması ayırmak gösterilmiştir: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, ve <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="4cb2b-104">Bu yararlıdır çünkü [!INCLUDE[wf](../../../../includes/wf-md.md)] bu döngüler yürütülmesi ayırmak için herhangi bir etkinlik içermez.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-104">This is useful because [!INCLUDE[wf](../../../../includes/wf-md.md)] does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="4cb2b-105">Senaryo</span><span class="sxs-lookup"><span data-stu-id="4cb2b-105">Scenario</span></span>  
 <span data-ttu-id="4cb2b-106">Örnek satıcılarının listesini ilk güvenilir satıcıdan bulur (örneklerini `Vendor` sınıfı).</span><span class="sxs-lookup"><span data-stu-id="4cb2b-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="4cb2b-107">Her satıcının bulunan bir `ID`, `Name` ve nasıl güvenilir satıcı mi belirleyen sayısal güvenilirlik değer.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="4cb2b-108">Örnek olarak adlandırılan özel bir etkinlik oluşturur `FindReliableVendor` , iki giriş parametreleri (Satıcılar ve en düşük güvenilirlik değer listesi) alır ve sağlanan ölçütlerle eşleşen listedeki ilk satıcısına döndürür.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="4cb2b-109">Döngü kesiliyor</span><span class="sxs-lookup"><span data-stu-id="4cb2b-109">Breaking a Loop</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="4cb2b-110">döngü ayırmak için bir etkinlik içermez.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-110"> does not include an activity to break a loop.</span></span> <span data-ttu-id="4cb2b-111">Kod örneği kullanarak bir döngü çiğnemekten gerçekleştirir bir <xref:System.Activities.Statements.If> etkinliği ve çeşitli değişkenler.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="4cb2b-112">Örnekte, <xref:System.Activities.Statements.While> etkinlik bozulur kez `reliableVendor` değişkeni atanan değer dışında `null`.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="4cb2b-113">Aşağıdaki kod örneğinde nasıl örnek biraz keser gösterilmektedir döngü.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4cb2b-114">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="4cb2b-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="4cb2b-115">Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], EmulatingBreakInWhile.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4cb2b-116">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4cb2b-117">Çözümü çalıştırmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4cb2b-118">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4cb2b-119">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4cb2b-120">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4cb2b-121">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`  
  
## <a name="see-also"></a><span data-ttu-id="4cb2b-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4cb2b-122">See Also</span></span>