---
title: CustomChannelsTester
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d915d567a5918060ab5e7592d4cd49384249ab9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="customchannelstester"></a><span data-ttu-id="d8112-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="d8112-102">CustomChannelsTester</span></span>
<span data-ttu-id="d8112-103">`CustomChannelsTester` Bir dizi önceden tanımlanmış hizmet sözleşmelerini, özel kanal uygulamaları test etmek için kullanabileceğiniz bir araçtır.</span><span class="sxs-lookup"><span data-stu-id="d8112-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="d8112-104">Hizmet sözleşmelerini kümeyi seçin ve bir XML dosyası kullanarak aracı geçirin.</span><span class="sxs-lookup"><span data-stu-id="d8112-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="d8112-105">Araç ardından, özel kanal uygulamaları ileti alışverişi sırasında uygular istemci ve hizmet oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d8112-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="d8112-106">Aracı yapılandırmak için</span><span class="sxs-lookup"><span data-stu-id="d8112-106">To build the tool</span></span>  
  
1.  <span data-ttu-id="d8112-107">Çözümü derlemek için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d8112-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="d8112-108">Çözümü derledikten üç dosyaları oluşturur: CustomChannelsTester.exe, TestSpec.xml ve SampleRun.cmd.</span><span class="sxs-lookup"><span data-stu-id="d8112-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="d8112-109">Test etmek için bu aracı kullanmak nasıl oluşturulduğunu gösteren örnek komut satırı dosya SampleRun.cmd sahip [taşıma: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="d8112-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="d8112-110">Aracı çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="d8112-110">To run the tool</span></span>  
  
-   <span data-ttu-id="d8112-111">Komut isteminde aşağıdaki komutu yazın:</span><span class="sxs-lookup"><span data-stu-id="d8112-111">At the command prompt type the following command:</span></span>  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="d8112-112">Kullanarak `/binding` seçeneği gereklidir.</span><span class="sxs-lookup"><span data-stu-id="d8112-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="d8112-113">`/dll`"bağlama" tarafından sağlanan sistem tarafından sağlanan bir bağlamayı değilse gereklidir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d8112-113">`/dll` is required if "binding" is not a system-provided binding provided by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
     <span data-ttu-id="d8112-114">`/testspec`isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="d8112-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="d8112-115">Bu, sunucu ve istemcileri test belirtimleri ve bağlama göre oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d8112-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="d8112-116">İstemci ve sunucu çalıştırır ve sonuçları döndürür.</span><span class="sxs-lookup"><span data-stu-id="d8112-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="d8112-117">Test belirtimleri (testspec.xml) açıklaması için XML örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="d8112-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8112-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d8112-118">See Also</span></span>