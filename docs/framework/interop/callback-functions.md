---
title: "Geri Çağırma İşlevleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4f39160e817ce04c5c15fb8299852a052d36c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions"></a>Geri Çağırma İşlevleri
Bir geri çağırma işlevini bir görevi tamamlamak yönetilmeyen DLL işlev yardımcı olan yönetilen bir uygulama içinde kodudur. Bir geri çağırma işlevi çağrıları dolaylı bir DLL işlevi aracılığıyla yönetilen bir uygulama geçirmek ve yönetilen uygulama geri. Bazı platformuyla adlı birçok DLL işlevleri çağırma düzgün çalışması için yönetilen kodda bir geri çağırma işlevini gerektirir.  
  
 Yönetilen koddan çoğu DLL işlevleri çağırmak için işlevinin yönetilen tanımı oluşturun ve onu çağırın. Basit bir işlemdir.  
  
 Bir geri çağırma işlevini gerektiren DLL işlevini kullanarak, bazı ek adımlar vardır. İlk olarak, işlev belgelerine bakarak işlevi bir geri çağırma gerekip gerekmediğini belirlemeniz gerekir. Ardından, geri çağırma işlevi, yönetilen bir uygulamada oluşturmanız gerekir. Son olarak, bir işaretçi geri çağırma işlevi bağımsız değişken olarak geçirme DLL işlevini çağırın. Aşağıdaki çizim, bu adımları özetlemektedir.  
  
 ![Platform çağırma geri çağırma](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
Geri çağırma işlevini ve uygulama  
  
 Geri arama işlevleri, bir görev art arda gerçekleştirilen durumlarda kullanmak için idealdir. Başka bir yaygın kullanım numaralandırma işlevleri ile olduğu gibi **EnumFontFamilies**, **EnumPrinters**, ve **EnumWindows** Win32 API içinde. **EnumWindows** işlevi numaralandırır her penceresinde bir görevi gerçekleştirmek için geri çağırma işlevini çağırarak bilgisayarınızdaki tüm var olan windows aracılığıyla. Yönergeler ve bir örnek için bkz: [nasıl yapılır: uygulama geri arama işlevleri](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Geri Çağırma İşlevlerini Uygulama](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [DLL İşlevini Çağırma](../../../docs/framework/interop/calling-a-dll-function.md)
