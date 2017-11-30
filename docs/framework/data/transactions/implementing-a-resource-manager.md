---
title: "Kaynak Yöneticisi uygulama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5c153f6-4419-49e3-a5f1-a50ae4c81bf3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b72b1bf68fa445a188c327098295d76815a80b16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-resource-manager"></a><span data-ttu-id="202be-102">Kaynak Yöneticisi uygulama</span><span class="sxs-lookup"><span data-stu-id="202be-102">Implementing a Resource Manager</span></span>
<span data-ttu-id="202be-103">Bir işlem içinde kullanılan her bir kaynağın eylemlerini bir işlem yöneticisi tarafından düzenlenir kaynak yöneticisi tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="202be-103">Each resource used in a transaction is managed by a resource manager, whose actions are coordinated by a transaction manager.</span></span> <span data-ttu-id="202be-104">Kaynak yöneticileri uygulama kararlılık ve yalıtım garantisi ile sağlamak için işlem yöneticisi işbirliği içinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="202be-104">Resource managers work in cooperation with the transaction manager to provide the application with a guarantee of atomicity and isolation.</span></span> <span data-ttu-id="202be-105">Microsoft SQL Server, kalıcı ileti sıraları, bellek içi karma tabloları kaynak yöneticilerinin tüm örnekleri mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="202be-105">Microsoft SQL Server, durable message queues, in-memory hash tables are all examples of resource managers.</span></span>  
  
 <span data-ttu-id="202be-106">Kalıcı veya geçici Veri Kaynağı Yöneticisi yönetir.</span><span class="sxs-lookup"><span data-stu-id="202be-106">A resource manager manages either durable or volatile data.</span></span> <span data-ttu-id="202be-107">Süreklilik (veya tersine volatility) kaynak yöneticisi kaynak yöneticisi hatası kurtarma destekleyip başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="202be-107">The durability (or conversely the volatility) of a resource manager refers to whether the resource manager supports failure recovery.</span></span> <span data-ttu-id="202be-108">Kaynak Yöneticisi hatadan kurtarma destekliyorsa, aşama 1 sırasında verileri dayanıklı depolama devam (hazırlama) sağlayacak şekilde Kaynak Yöneticisi'ni kullanılamaz hale gelirse, Kurtarma sırasında işlemdeki yeniden listeleme ve bildirimlerini göre uygun eylemleri gerçekleştirin İşlem Yöneticisi'nden aldı.</span><span class="sxs-lookup"><span data-stu-id="202be-108">If a resource manager supports failure recovery, it persists data to durable storage during Phase1 (prepare) such that if the resource manager goes down, it can re-enlist in the transaction upon recovery and perform the proper actions based on the notifications received from the transaction manager.</span></span> <span data-ttu-id="202be-109">Genel olarak, geçici kaynak yöneticileri bir bellek içi veri yapısı (örneğin, bir bellek içi işlem yapılan işlem-hashtable) gibi volatile kaynakları yönetme ve dayanıklı kaynak yöneticileri yönetme daha kalıcı bir yedekleme deposu kaynakları (örneğin, bir Veritabanı), yedekleme deposu disktir.</span><span class="sxs-lookup"><span data-stu-id="202be-109">In general, volatile resource managers manage volatile resources such as an in-memory data structure (for example, an in-memory transacted-hashtable), and durable resource managers manage resources that have a more persistent backing store (for example, a database whose backing store is disk).</span></span>  
  
 <span data-ttu-id="202be-110">Bir işlemde bir kaynak için sırayla işlem listesine gerekir.</span><span class="sxs-lookup"><span data-stu-id="202be-110">In order for a resource to participate in a transaction, it must enlist in the transaction.</span></span> <span data-ttu-id="202be-111"><xref:System.Transactions.Transaction> Sınıfı tanımlayan bir dizi yöntem ile başlar, adları **Enlist** bu işlevsellik sağlar.</span><span class="sxs-lookup"><span data-stu-id="202be-111">The <xref:System.Transactions.Transaction> class defines a set of methods whose names begin with **Enlist** that provide this functionality.</span></span> <span data-ttu-id="202be-112">Farklı **Enlist** yöntemleri karşılık gelen bir Kaynak Yöneticisi'ni olabilir kaydı farklı türleri için.</span><span class="sxs-lookup"><span data-stu-id="202be-112">The different **Enlist** methods correspond to the different types of enlistment that a resource manager may have.</span></span> <span data-ttu-id="202be-113">Özellikle, kullandığınız <xref:System.Transactions.Transaction.EnlistVolatile%2A> geçici kaynaklar için yöntemleri ve <xref:System.Transactions.Transaction.EnlistDurable%2A> kalıcı kaynaklar için yöntem.</span><span class="sxs-lookup"><span data-stu-id="202be-113">Specifically, you use the <xref:System.Transactions.Transaction.EnlistVolatile%2A> methods for volatile resources, and the <xref:System.Transactions.Transaction.EnlistDurable%2A> method for durable resources.</span></span> <span data-ttu-id="202be-114">Kullanılacak karar sonra kolaylık <xref:System.Transactions.Transaction.EnlistDurable%2A> veya <xref:System.Transactions.Transaction.EnlistVolatile%2A> , kaynağın süreklilik desteğini tabanlı yöntemi, iki aşaması yürütme içinde (2PC) uygulayarak katılmak için kaynak listeleme <xref:System.Transactions.IEnlistmentNotification> , kaynak yöneticisi için arabirim.</span><span class="sxs-lookup"><span data-stu-id="202be-114">For simplicity, after deciding whether to use the <xref:System.Transactions.Transaction.EnlistDurable%2A> or <xref:System.Transactions.Transaction.EnlistVolatile%2A> method based on your resource's durability support, you should enlist your resource to participate in Two Phase Commit (2PC) by implementing the <xref:System.Transactions.IEnlistmentNotification> interface for your resource manager.</span></span> <span data-ttu-id="202be-115">2PC hakkında daha fazla bilgi için bkz: [tek aşamalı ve çok aşama işlemde yürüten](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md).</span><span class="sxs-lookup"><span data-stu-id="202be-115">For more information on 2PC, see [Committing a Transaction in Single-Phase and Multi-Phase](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md).</span></span>  
  
 <span data-ttu-id="202be-116">Kaydetme tarafından işlem tamamlandığında veya iptal edildiğinde, İşlem Yöneticisi'nden geri aramalar alır, Kaynak Yöneticisi'ni sağlar.</span><span class="sxs-lookup"><span data-stu-id="202be-116">By enlisting, the resource manager ensures that it gets callbacks from the transaction manager when the transaction commits or aborts.</span></span> <span data-ttu-id="202be-117">Bir örneği yok <xref:System.Transactions.IEnlistmentNotification> başına liste.</span><span class="sxs-lookup"><span data-stu-id="202be-117">There is one instance of <xref:System.Transactions.IEnlistmentNotification> per enlistment.</span></span> <span data-ttu-id="202be-118">Genellikle, işlem başına bir kaydı yoktur, ancak aynı işlemde birden çok kez listeleme bir Kaynak Yöneticisi'ni seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="202be-118">Typically, there is one enlistment per transaction, but a resource manager can choose to enlist multiple times in the same transaction.</span></span>  
  
 <span data-ttu-id="202be-119">Kaydı sonra Kaynak Yöneticisi'ni işlemdeki isteklerine yanıt verir.</span><span class="sxs-lookup"><span data-stu-id="202be-119">After enlistment, the resource manager responds to the transaction's requests.</span></span> <span data-ttu-id="202be-120">Sağlam Kaynak Yöneticisi yönettiği geri almak veya işlemdeki iş kaynaklarına Yinele izin vermek için yeterli bilgi depolar.</span><span class="sxs-lookup"><span data-stu-id="202be-120">A durable resource manager stores enough information to allow it to either undo or redo the transaction's work on resources it manages.</span></span> <span data-ttu-id="202be-121">Bunu yapmak için birçok yolu vardır; Veri sürümlerini saklama veya değişiklikleri bir günlük tutma iki ortak teknikler mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="202be-121">There are many ways to do this; keeping versions of data or keeping a log of the changes are two common techniques.</span></span>  
  
 <span data-ttu-id="202be-122">Uygulamanın işlem onayladığında, işlem yöneticisi iki aşamalı yürütme Protokolü başlatır.</span><span class="sxs-lookup"><span data-stu-id="202be-122">When the application commits the transaction, the transaction manager initiates the two-phase commit protocol.</span></span> <span data-ttu-id="202be-123">İşlem yöneticisi hareketi için hazırlanan varsa her kayıtlı Kaynak Yöneticisi'ni ilk sorar.</span><span class="sxs-lookup"><span data-stu-id="202be-123">The transaction manager first asks each enlisted resource manager if it is prepared to commit the transaction.</span></span> <span data-ttu-id="202be-124">Kaynak Yöneticisi'ni uygulamak hazırlamanız gerekir — yürütün veya işlem iptal kendisine onu hazırlar.</span><span class="sxs-lookup"><span data-stu-id="202be-124">The resource manager must prepare to commit—it readies itself to either commit or abort the transaction.</span></span>  
  
 <span data-ttu-id="202be-125">Böylece sistem başarısız olsa bile Kaynak Yöneticisi, kurtarabilirsiniz hazırla aşamasında, eski ve yeni veri kalıcı Kaynak Yöneticisi tutarlı depolama kaydeder.</span><span class="sxs-lookup"><span data-stu-id="202be-125">During the prepare phase, the durable resource manager records the old and new data in stable storage so that the resource manager can recover it even if the system fails.</span></span> <span data-ttu-id="202be-126">Kaynak Yöneticisi'ni hazırlayabilirsiniz, işlem yöneticisi, oylama mi tamamlanmaya veya işlem iptal bildirir.</span><span class="sxs-lookup"><span data-stu-id="202be-126">If the resource manager can prepare, it informs the transaction manager its vote on whether to commit or abort the transaction.</span></span> <span data-ttu-id="202be-127">Herhangi bir kaynak yöneticisi hazırlama hatası bildirirse, işlem yöneticisi her kaynak yöneticisi için bir geri alma komutu gönderir ve uygulamaya yürütme başarısızlığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="202be-127">If any resource manager reports a failure to prepare, the transaction manager sends a rollback command to each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="202be-128">Hazırlanan sonra kaynak yöneticisi bir yürütme ulaşana kadar bekleyin veya Aşama 2 geri çağırma İşlem Yöneticisi'nden iptal gerekir.</span><span class="sxs-lookup"><span data-stu-id="202be-128">Once prepared, a resource manager must wait until it gets a commit or abort callback from the transaction manager in phase 2.</span></span> <span data-ttu-id="202be-129">Genel olarak, bir saniyenin tüm hazırla ve yürütme protokol tamamlar.</span><span class="sxs-lookup"><span data-stu-id="202be-129">Typically, the entire prepare and commit protocol completes in a fraction of a second.</span></span> <span data-ttu-id="202be-130">Sistem veya iletişim hatası yoksa, tamamlama veya iptal bildirimi dakika veya saat için gelebilir değil.</span><span class="sxs-lookup"><span data-stu-id="202be-130">If there are system or communication failures, the commit or abort notification may not arrive for minutes or hours.</span></span> <span data-ttu-id="202be-131">Bu dönemde kaynak işlemin sonucuyla ilgili şüpheli yöneticisidir.</span><span class="sxs-lookup"><span data-stu-id="202be-131">During this period, the resource manager is in doubt about the outcome of the transaction.</span></span> <span data-ttu-id="202be-132">İşlem yürütülmemiş veya durdurulmamış bilmez.</span><span class="sxs-lookup"><span data-stu-id="202be-132">It does not know whether the transaction committed or aborted.</span></span> <span data-ttu-id="202be-133">Kaynak Yöneticisi'ni şüpheli bir işlem hakkında olsa da, böylece diğer işlemler bu değişikliklerden yalıtarak kilitli, işlem tutarak değiştirilen veriler tutar.</span><span class="sxs-lookup"><span data-stu-id="202be-133">While the resource manager is in doubt about a transaction, it keeps the data modified by keeping the transaction locked, thereby isolating these changes from any other transactions.</span></span>  
  
 <span data-ttu-id="202be-134">Kaynak Yöneticisi başarısız olduğunda, tüm kayıtlı hareketlerini hazırlanmış ya da hatasından önce kaydedilmiş dışında iptal edilir.</span><span class="sxs-lookup"><span data-stu-id="202be-134">When a resource manager fails, all of its enlisted transactions are aborted except for those that are prepared or committed prior to the failure.</span></span> <span data-ttu-id="202be-135">Sağlam Kaynak Yöneticisi yeniden başlatıldığında, hazırlama aşamasında, yazılan prepare bilgileri alarak yönettiği kaynaklar kaydedilmiş durumunu yeniden yapılandırılacağını ve tamamlar veya bu işlemler buna uygun olarak iptal eder.</span><span class="sxs-lookup"><span data-stu-id="202be-135">When a durable resource manager restarts, it reconstructs the committed state of the resources it manages by retrieving the prepare information written in the prepare phase, and commits or aborts these transactions accordingly.</span></span>  
  
 <span data-ttu-id="202be-136">Özet olarak, kararlı ve sürekli işlemleri yapmak için iki aşamalı yürütme protokolü ve kaynak yöneticileri birleştirin.</span><span class="sxs-lookup"><span data-stu-id="202be-136">In summary, the two-phase commit protocol and the resource managers combine to make transactions atomic and durable.</span></span>  
  
 <span data-ttu-id="202be-137"><xref:System.Transactions.Transaction> Sınıfı sağlar <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> bir Promotable tek aşaması liste'nı (PSPE) listeleme yöntemi.</span><span class="sxs-lookup"><span data-stu-id="202be-137">The <xref:System.Transactions.Transaction> class also provides the <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> method to enlist a Promotable Single Phase Enlistment (PSPE).</span></span> <span data-ttu-id="202be-138">Bu sağlam Kaynak Yöneticisi (RM barındırmak ve "gerekirse MSDTC tarafından yönetilecek daha sonra ilerletilen bir işlem kendi") sağlar.</span><span class="sxs-lookup"><span data-stu-id="202be-138">This allows a durable resource manager (RM) to host and "own" a transaction that can later be escalated to be managed by the MSDTC if necessary.</span></span> <span data-ttu-id="202be-139">Bunun hakkında daha fazla bilgi için bkz: [tek aşaması kaydetmek ve yükseltilebilir tek aşaması bildirim kullanarak en iyi duruma getirme](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="202be-139">For more information on this, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="202be-140">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="202be-140">In This Section</span></span>  
 <span data-ttu-id="202be-141">Genel olarak kaynak yöneticisi tarafından izlenen adımları aşağıdaki konulara özetlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="202be-141">The steps generally followed by a resource manager are outlined in the following topics.</span></span>  
  
 [<span data-ttu-id="202be-142">Bir işlemde katılımcı olarak kaynakları kaydetme</span><span class="sxs-lookup"><span data-stu-id="202be-142">Enlisting Resources as Participants in a Transaction</span></span>](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)  
  
 <span data-ttu-id="202be-143">Kalıcı veya geçici bir kaynak bir işlem nasıl listesine açıklar.</span><span class="sxs-lookup"><span data-stu-id="202be-143">Describes how a durable or volatile resource can enlist in a transaction.</span></span>  
  
 [<span data-ttu-id="202be-144">İşlemi tek aşamalı ve çok aşaması Tamamlanıyor</span><span class="sxs-lookup"><span data-stu-id="202be-144">Committing a Transaction in Single-Phase and Multi-Phase</span></span>](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)  
  
 <span data-ttu-id="202be-145">Bildirim Kaydet ve yürütme hazırlamak için bir kaynak yöneticisi nasıl yanıt vereceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="202be-145">Describes how a resource manager responds to commit notification and prepare the commit.</span></span>  
  
 [<span data-ttu-id="202be-146">Kurtarma gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="202be-146">Performing Recovery</span></span>](../../../../docs/framework/data/transactions/performing-recovery.md)  
  
 <span data-ttu-id="202be-147">Nasıl sürekli Kaynak Yöneticisi hata verdi kurtarır açıklar.</span><span class="sxs-lookup"><span data-stu-id="202be-147">Describes how a durable resource manager recovers from failure.</span></span>  
  
 [<span data-ttu-id="202be-148">Kaynaklara erişimde güvenlik güven düzeyleri</span><span class="sxs-lookup"><span data-stu-id="202be-148">Security Trust Levels in Accessing Resources</span></span>](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md)  
  
 <span data-ttu-id="202be-149">Nasıl güven System.Transactions için üç düzeyde kaynakları türlerine erişimi kısıtlama açıklar, <xref:System.Transactions> kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="202be-149">Describes how the three levels of trust for System.Transactions restrict access on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 [<span data-ttu-id="202be-150">Tek aşaması kaydetmek ve yükseltilebilir tek aşaması bildirim kullanarak en iyi duruma getirme</span><span class="sxs-lookup"><span data-stu-id="202be-150">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
  
 <span data-ttu-id="202be-151">Kaynak yöneticileri uygulamalar için kullanılabilir olan en iyi hale getirme yöntemleri açıklar.</span><span class="sxs-lookup"><span data-stu-id="202be-151">Describes optimization practices available to implementations of resource managers.</span></span>