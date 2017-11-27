---
title: "Güvenilir Güvenlik Profili"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 6b73565409e26456ad09067066455ef2459b2e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-secure-profile"></a><span data-ttu-id="baa69-102">Güvenilir Güvenlik Profili</span><span class="sxs-lookup"><span data-stu-id="baa69-102">Reliable Secure Profile</span></span>
<span data-ttu-id="baa69-103">Bu örnek oluşturmak nasıl gösterir [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ve [güvenilir güvenli profili](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span><span class="sxs-lookup"><span data-stu-id="baa69-103">This sample demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140) (RSP).</span></span> <span data-ttu-id="baa69-104">Bu örnek uygulama ortaya koyar bir [bağlantı yap](http://go.microsoft.com/fwlink/?LinkId=178141) güvenilir Mesajlaşma ile birlikte ve isteğe bağlı olarak oluşan kanal güvenilir güvenli bağlama oluşturmak için güvenli bir kanal tabanlı RSP belirtimi.</span><span class="sxs-lookup"><span data-stu-id="baa69-104">This sample demonstrates the implementation of a [Make Connection](http://go.microsoft.com/fwlink/?LinkId=178141) channel which can be composed together with Reliable Messaging and optionally a secure channel to create a Reliable Secure Binding based on the RSP specification.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="baa69-105">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="baa69-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="baa69-106">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="baa69-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="baa69-107">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="baa69-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="baa69-108">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="baa69-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## <a name="discussion"></a><span data-ttu-id="baa69-109">Tartışma</span><span class="sxs-lookup"><span data-stu-id="baa69-109">Discussion</span></span>  
 <span data-ttu-id="baa69-110">Bu örnek bir güvenilir zaman uyumsuz iki yönlü ileti exchange senaryo gösterir.</span><span class="sxs-lookup"><span data-stu-id="baa69-110">This sample demonstrates a reliable asynchronous two-way message exchange scenario.</span></span> <span data-ttu-id="baa69-111">Çift yönlü sözleşme hizmeti sahiptir ve çift yönlü geri çağırma sözleşme istemci uygular.</span><span class="sxs-lookup"><span data-stu-id="baa69-111">The service has a duplex contract and the client implements the duplex callback contract.</span></span> <span data-ttu-id="baa69-112">İstemci üzerinde ayrı bir bağlantı beklenen bir yanıt için bir hizmet isteğine başlatır.</span><span class="sxs-lookup"><span data-stu-id="baa69-112">The client initiates a request to a service, for which a response is expected on a separate connection.</span></span> <span data-ttu-id="baa69-113">İstek iletisi güvenilir bir şekilde gönderilir.</span><span class="sxs-lookup"><span data-stu-id="baa69-113">The request message is sent reliably.</span></span> <span data-ttu-id="baa69-114">İstemci, sonunda dinleyen bir uç noktası açmak istediğiniz değil.</span><span class="sxs-lookup"><span data-stu-id="baa69-114">The client does not want to open a listening endpoint at its end.</span></span> <span data-ttu-id="baa69-115">Bu nedenle, bu 'Bağlantı Yap' istek arka kanalda yanıtı geri gönderilecek hizmeti için 'Bağlantı Yap' isteklerin hizmetiyle yoklar.</span><span class="sxs-lookup"><span data-stu-id="baa69-115">Thus, it polls the service with ‘Make Connection’ requests for the service to send back the response on the back channel of this ‘Make Connection’ request.</span></span> <span data-ttu-id="baa69-116">Bu örnek, istemci dinleyen bir uç nokta gösterme (ve bir güvenlik duvarı özel durum oluşturulmadan) HTTP üzerinden güvenli güvenilir çift yönlü iletişim sağlamak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="baa69-116">This sample demonstrates how to have secure reliable duplex communication over HTTP without the client exposing a listening endpoint (and creating a firewall exception).</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="baa69-117">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="baa69-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="baa69-118">Açık **ReliableSecureProfile** çözümü.</span><span class="sxs-lookup"><span data-stu-id="baa69-118">Open the **ReliableSecureProfile** solution.</span></span>  
  
2.  <span data-ttu-id="baa69-119">Sağ tıklayın **hizmet** proje **Çözüm Gezgini**seçin **hata ayıklama**, **başlangıç yeni örnek** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="baa69-119">Right click the **Service** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="baa69-120">Bu hizmet ana bilgisayarını başlatır.</span><span class="sxs-lookup"><span data-stu-id="baa69-120">This starts up the service host.</span></span>  
  
3.  <span data-ttu-id="baa69-121">Sağ tıklayın **istemci** proje **Çözüm Gezgini**seçin **hata ayıklama**, **başlangıç yeni örnek** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="baa69-121">Right click the **Client** project in **Solution Explorer**, select **Debug**, **Start new instance** from the context menu.</span></span> <span data-ttu-id="baa69-122">Bu istemci başlatır.</span><span class="sxs-lookup"><span data-stu-id="baa69-122">This starts up the client.</span></span>  
  
4.  <span data-ttu-id="baa69-123">İstemci konsol penceresi satırına herhangi bir dize yazın ve ENTER tuşuna basın. Bu giriş dizesi Bu dize karmasını hesaplar hizmetine gönderir.</span><span class="sxs-lookup"><span data-stu-id="baa69-123">Type in any string in the prompt on the client console window and click ENTER.This sends the input string to the service, which computes a hash of this string.</span></span>  
  
5.  <span data-ttu-id="baa69-124">Hizmet geri istemci konsol penceresi sonucu görüntülemek için çift yönlü geri çağırma sözleşme işlemi çağırdığında sonucu windows istemcisi üzerinde görüntüleyin.</span><span class="sxs-lookup"><span data-stu-id="baa69-124">View the result on the client windows when the service calls back the duplex callback contract operation to display the result on the client console window.</span></span> <span data-ttu-id="baa69-125">Uzun süre çalışan bir veri işleme işleminin benzetimini yapmak için hizmette kasıtlı bir gecikme olur.</span><span class="sxs-lookup"><span data-stu-id="baa69-125">There is an intentional delay on the service to simulate a long running operation of processing the data.</span></span>  
  
6.  <span data-ttu-id="baa69-126">(Herhangi biri tarafından çevrimiçi ağ izleme araçları Ağ İzleyicisi, Fiddler vb. gibi) HTTP trafiğini izleme gösterir dizisi iletişimi için istemci ile hizmet arasında güvenilir güvenli profili tarafından düzenlenir ve nasıl oluşturduğunuzu istemci 'Bağlantı Yap' istekleri hizmetiyle yoklar.</span><span class="sxs-lookup"><span data-stu-id="baa69-126">Monitoring the HTTP traffic (by any of the online network monitoring tools like Network Monitor, Fiddler and so on) shows that a sequence for communication is established between the client and the service as laid down by the Reliable Secure Profile, and how the client polls the service with ‘Make Connection’ requests.</span></span> <span data-ttu-id="baa69-127">Hizmet işlenen yanıtı geri göndermek hazır aldığında, sonuçları geri göndermek için son 'Bağlantı Yap' isteğinin arka kanal kullanır.</span><span class="sxs-lookup"><span data-stu-id="baa69-127">When the service gets ready to send back the processed response, it uses the back channel of the last ‘Make Connection’ request to send back the results.</span></span>  
  
7.  <span data-ttu-id="baa69-128">Hizmet konsol penceresinde hizmeti kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="baa69-128">Press ENTER on the service console window to close the service.</span></span> <span data-ttu-id="baa69-129">İstemci konsol penceresi İstemcisi'ni kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="baa69-129">Press ENTER on the client console window to close the client.</span></span>