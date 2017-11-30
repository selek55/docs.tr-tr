---
title: Yordam etkinlikleri kullanma
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c391316959829c77d16dd87af51d9fe1915dc88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="c0d6d-102">Yordam etkinlikleri kullanma</span><span class="sxs-lookup"><span data-stu-id="c0d6d-102">Using Procedural Activities</span></span>
<span data-ttu-id="c0d6d-103">Örnek kullanır <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, ve <xref:System.Activities.Statements.WriteLine> bir tahmin uygulamak için etkinlikler oyun.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="c0d6d-104">Rastgele bir sayı tahmin eden oyun seçer ve bu sayıyı tahmin etmeye player sahiptir.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="c0d6d-105">Player yanlış tahmin gönderdiğinde, iş akışı yüksek tahmin ya da daha düşük bir ipucu sağlar.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="c0d6d-106">Player sayı değerinden 7 girişimlerinde tahminde bulunursa, bir özel Tebrikler kullanıcıya görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="c0d6d-107">Bu örnek özel etkinlikleri</span><span class="sxs-lookup"><span data-stu-id="c0d6d-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="c0d6d-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="c0d6d-108">ReadLine</span></span>  
 <span data-ttu-id="c0d6d-109">Metin satırının konsoldan okur.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-109">Reads a line of text from the console.</span></span> <span data-ttu-id="c0d6d-110">Bu etkinlik türetilen <xref:System.Activities.NativeActivity> sınıfı ve bir satır okunduğunda konsol uygulaması tarafından sürdürüldü bir yer işareti oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="c0d6d-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="c0d6d-111">PromptInt</span></span>  
 <span data-ttu-id="c0d6d-112">Kullanıcıdan bir sayı yazın ve ardından bir konsol penceresinden okur.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="c0d6d-113">Etkinlik türetilen <xref:System.Activities.Activity%601> ve kullandığı <xref:System.Activities.Statements.WriteLine> ve `ReadLine` etkinlikler.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="c0d6d-114">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="c0d6d-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="c0d6d-115">Kullanarak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], GuessingGame.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="c0d6d-116">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c0d6d-117">Çözümü çalıştırmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0d6d-118">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c0d6d-119">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c0d6d-120">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c0d6d-121">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## <a name="see-also"></a><span data-ttu-id="c0d6d-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c0d6d-122">See Also</span></span>