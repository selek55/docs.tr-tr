---
title: "Uçtan Uca İzleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b4cdbc12f57c733d8e8ba3753ce5a2f29ab28ffd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="3d16a-102">Uçtan Uca İzleme</span><span class="sxs-lookup"><span data-stu-id="3d16a-102">End-to-End Tracing</span></span>
<span data-ttu-id="3d16a-103">Uçtan uca kodun yürütülmesini izlemek geliştiricilere (e2e) izleme sağlar [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] bir kod yolu neden başarısız oldu araştırmak veya kapasite planlama ve performans analizi için ayrıntılı izleme sağlamak için altyapı.</span><span class="sxs-lookup"><span data-stu-id="3d16a-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="3d16a-104">bir hatanın nedenini tanılamaya yardımcı olmak için üç bağıntı mekanizmalar sağlar: etkinlikleri, aktarımları ve yayma.</span><span class="sxs-lookup"><span data-stu-id="3d16a-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="3d16a-105">Bkz: [uçtan uca izleme senaryoları](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) uçtan uca izleme senaryoları ve bunların ilgili etkinliği ve tasarım izleme listesi.</span><span class="sxs-lookup"><span data-stu-id="3d16a-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d16a-106">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="3d16a-106">In This Section</span></span>  
 <span data-ttu-id="3d16a-107">[Etkinlik](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): etkinlik izlemeleri açıklar [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] izleme modeli.</span><span class="sxs-lookup"><span data-stu-id="3d16a-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="3d16a-108">[Aktarım](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): aktarımı açıklar [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modeli izleme ve uç noktaları'nda etkinlikler ilişkilendirmek için Aktarım kullanma.</span><span class="sxs-lookup"><span data-stu-id="3d16a-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="3d16a-109">[Yayma](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): Etkinlik yayma açıklar [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modeli izleme ve yayma uç noktalar arasında etkinliklerini ilişkilendirmek için kullanma.</span><span class="sxs-lookup"><span data-stu-id="3d16a-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="3d16a-110">İzleme türü özeti</span><span class="sxs-lookup"><span data-stu-id="3d16a-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="3d16a-111">İzleme türleri tüm etkinliklerin bir özetini sunar</span><span class="sxs-lookup"><span data-stu-id="3d16a-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d16a-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3d16a-112">See Also</span></span>  
 [<span data-ttu-id="3d16a-113">İzlemeyi Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3d16a-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="3d16a-114">İzlemeleri görüntüleme bağıntılı için hizmet izleme görüntüleyicisini kullanma ve sorun giderme</span><span class="sxs-lookup"><span data-stu-id="3d16a-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="3d16a-115">Uçtan uca izleme senaryoları</span><span class="sxs-lookup"><span data-stu-id="3d16a-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="3d16a-116">Hizmet izleme Görüntüleyicisi aracı (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3d16a-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)