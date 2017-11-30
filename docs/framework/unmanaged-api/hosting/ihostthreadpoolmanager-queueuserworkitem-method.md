---
title: "IHostThreadPoolManager::QueueUserWorkItem Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.QueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9948673d6988de21c83c37538fb4d7c030296e58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="51c80-102">IHostThreadPoolManager::QueueUserWorkItem Yöntemi</span><span class="sxs-lookup"><span data-stu-id="51c80-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="51c80-103">Bir işlev yürütme için sıraya koyar ve bu işlev tarafından kullanılacak verilerini içeren bir nesne belirtir.</span><span class="sxs-lookup"><span data-stu-id="51c80-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="51c80-104">Bir iş parçacığı kullanılabilir hale geldiğinde işlevi yürütür.</span><span class="sxs-lookup"><span data-stu-id="51c80-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c80-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="51c80-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51c80-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="51c80-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="51c80-107">[in] Yürütülecek işlevi temsil eden bir işlev işaretçisi.</span><span class="sxs-lookup"><span data-stu-id="51c80-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="51c80-108">[in] Tarafından kullanılacak veri içeren bir nesne `Function`.</span><span class="sxs-lookup"><span data-stu-id="51c80-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="51c80-109">[in] Bayrakları değerlerden birini, Win32 için tanımlanan `QueueUserWorkItem` yürütme denetleyen yöntemi.</span><span class="sxs-lookup"><span data-stu-id="51c80-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51c80-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="51c80-110">Return Value</span></span>  
  
|<span data-ttu-id="51c80-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51c80-111">HRESULT</span></span>|<span data-ttu-id="51c80-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="51c80-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51c80-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="51c80-113">S_OK</span></span>|<span data-ttu-id="51c80-114">`QueueUserWorkItem`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="51c80-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="51c80-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51c80-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51c80-116">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="51c80-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51c80-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51c80-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51c80-118">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="51c80-118">The call timed out.</span></span>|  
|<span data-ttu-id="51c80-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51c80-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51c80-120">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="51c80-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51c80-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51c80-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51c80-122">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="51c80-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51c80-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51c80-123">E_FAIL</span></span>|<span data-ttu-id="51c80-124">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="51c80-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51c80-125">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="51c80-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51c80-126">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="51c80-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51c80-127">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="51c80-127">Remarks</span></span>  
 <span data-ttu-id="51c80-128">`QueueUserWorkItem`iş parçacığı havuzu bir çalışan iş parçacığı için iş öğesi sıralar.</span><span class="sxs-lookup"><span data-stu-id="51c80-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="51c80-129">İmza ve parametre türlerinden olanlar aynı ada sahip karşılık gelen Win32 işlevi için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="51c80-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="51c80-130">Daha fazla bilgi için Windows platformu belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="51c80-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51c80-131">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="51c80-131">Requirements</span></span>  
 <span data-ttu-id="51c80-132">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c80-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c80-133">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51c80-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51c80-134">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="51c80-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51c80-135">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c80-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c80-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="51c80-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="51c80-137">Ihostthreadpoolmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="51c80-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)