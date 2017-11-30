---
title: failedQI MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 87fe67e1e64d69912095e1d9587d277805a3eb80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="failedqi-mda"></a><span data-ttu-id="d874e-102">failedQI MDA</span><span class="sxs-lookup"><span data-stu-id="d874e-102">failedQI MDA</span></span>
<span data-ttu-id="d874e-103">`failedQI` Yönetilen hata ayıklama Yardımcısı (MDA) çalışma zamanı çağırdığında etkinleştirilirse `QueryInterface` bir çalışma zamanı aranabilir sarmalayıcısı (RCW) adına COM arabirimi işaretçisi üzerinde ve `QueryInterface` çağrısı başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="d874e-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d874e-104">Belirtiler</span><span class="sxs-lookup"><span data-stu-id="d874e-104">Symptoms</span></span>  
 <span data-ttu-id="d874e-105">Bir RCW üzerinde bir dönüştürme başarısız veya bir çağrısından com bir RCW beklenmedik şekilde başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="d874e-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d874e-106">Sebep</span><span class="sxs-lookup"><span data-stu-id="d874e-106">Cause</span></span>  
  
-   <span data-ttu-id="d874e-107">Yanlış bağlamdan çağrı yapılır.</span><span class="sxs-lookup"><span data-stu-id="d874e-107">The call is made from the wrong context.</span></span>  
  
-   <span data-ttu-id="d874e-108">Kayıtlı proxy başarısız `QueryInterface` çağrısı yanlış bağlamda yapıldığı için çağırın.</span><span class="sxs-lookup"><span data-stu-id="d874e-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
-   <span data-ttu-id="d874e-109">OLE ait proxy HRESULT hata döndürdü.</span><span class="sxs-lookup"><span data-stu-id="d874e-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d874e-110">Çözüm</span><span class="sxs-lookup"><span data-stu-id="d874e-110">Resolution</span></span>  
 <span data-ttu-id="d874e-111">COM kurallarında MSDN belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="d874e-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d874e-112">Çalışma zamanı etkisi</span><span class="sxs-lookup"><span data-stu-id="d874e-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="d874e-113">Varsa bir `QueryInterface` çağrısı başarısız oldu, bağlam geçti ve `QueryInterface` çağrı denemesi yeniden hatalı bir bağlam hatalı olup olmadığını görmek için.</span><span class="sxs-lookup"><span data-stu-id="d874e-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d874e-114">Çıkış</span><span class="sxs-lookup"><span data-stu-id="d874e-114">Output</span></span>  
 <span data-ttu-id="d874e-115">Arabirimin arabirimi GUID ve HRESULT hata yönetilen adı.</span><span class="sxs-lookup"><span data-stu-id="d874e-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d874e-116">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="d874e-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d874e-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d874e-117">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="d874e-118">Yönetilen hata ayıklama Yardımcıları ile hataları tanılama</span><span class="sxs-lookup"><span data-stu-id="d874e-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="d874e-119">Birlikte çalışma hazırlama</span><span class="sxs-lookup"><span data-stu-id="d874e-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)