---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7083472ff476ac359aeb27013abf1d662dede3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="corprofeunsupportedcallsequence-hresult"></a><span data-ttu-id="2b690-102">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b690-102">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>
<span data-ttu-id="2b690-103">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT .NET Framework sürüm 2.0 sunulmuştur.</span><span class="sxs-lookup"><span data-stu-id="2b690-103">The CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT was introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2b690-104">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] İki senaryoda Bu HRESULT döndürür:</span><span class="sxs-lookup"><span data-stu-id="2b690-104">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] returns this HRESULT in two scenarios:</span></span>  
  
-   <span data-ttu-id="2b690-105">Bir iş parçacığının zorla ele geçirme profil oluşturucu sıfırlandıktan sonra bağlamı iş parçacığı tutarsız bir durumda yapıları erişmeye rasgele bir zaman kaydettiğiniz.</span><span class="sxs-lookup"><span data-stu-id="2b690-105">When a hijacking profiler forcibly resets a thread's register context at an arbitrary time so that the thread tries to access structures that are in an inconsistent state.</span></span>  
  
-   <span data-ttu-id="2b690-106">Çöp toplama bir geri çağırma yönteminden tetikler bilgilendirici bir yöntemi çağırmak bir profil oluşturucu çalıştığında, atık toplama engelliyor.</span><span class="sxs-lookup"><span data-stu-id="2b690-106">When a profiler tries to call an informational method that triggers garbage collection from a callback method that forbids garbage collection.</span></span>  
  
 <span data-ttu-id="2b690-107">Bu iki senaryo aşağıdaki bölümlerde ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="2b690-107">These two scenarios are discussed in the following sections.</span></span>  
  
## <a name="hijacking-profilers"></a><span data-ttu-id="2b690-108">Profil oluşturucular ele geçirme</span><span class="sxs-lookup"><span data-stu-id="2b690-108">Hijacking Profilers</span></span>  
 <span data-ttu-id="2b690-109">(Bu senaryo vardır, ancak bu HRESULT geçirme olmayan profil oluşturucular görebileceğiniz durumlarda profil oluşturucular ele geçirme ile öncelikle bir sorundur.)</span><span class="sxs-lookup"><span data-stu-id="2b690-109">(This scenario is primarily an issue with hijacking profilers although there are cases where non-hijacking profilers can see this HRESULT.)</span></span>  
  
 <span data-ttu-id="2b690-110">İş parçacığı profil oluşturucu kodu girin veya ortak dil çalışma zamanı (CLR) yeniden girmeniz Bu senaryoda, geçirme profil oluşturucu zorla bir iş parçacığının kayıt bağlamını rastgele bir zaman aracılığıyla sıfırlar ve böylece bir [Icorprofilerınfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="2b690-110">In this scenario, a hijacking profiler forcibly resets a thread's register context at an arbitrary time so that the thread can enter profiler code or re-enter the common language runtime (CLR) through an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) method.</span></span>  
  
 <span data-ttu-id="2b690-111">Çoğu profil oluşturma API CLR veri yapılarını noktasıdır kimlikleri.</span><span class="sxs-lookup"><span data-stu-id="2b690-111">Many of the IDs that the profiling API provides point to data structures in the CLR.</span></span> <span data-ttu-id="2b690-112">Birçok `ICorProfilerInfo` çağrıları yalnızca bu veri yapıları bilgileri okuyun ve geri geçirin.</span><span class="sxs-lookup"><span data-stu-id="2b690-112">Many `ICorProfilerInfo` calls merely read information from these data structures and pass them back.</span></span> <span data-ttu-id="2b690-113">Ancak, CLR çalıştırır ve bunu yapmak için kilitler kullanabilir şey bu yapılarında değişebilir.</span><span class="sxs-lookup"><span data-stu-id="2b690-113">However, the CLR might change things in those structures as it runs, and it might use locks to do so.</span></span> <span data-ttu-id="2b690-114">CLR zaten bulunduran (veya alma girişimi varsayın) bir kilit zaman profil oluşturucu iş parçacığı sağlayarak.</span><span class="sxs-lookup"><span data-stu-id="2b690-114">Suppose the CLR was already holding (or attempting to acquire) a lock at the time the profiler hijacked the thread.</span></span> <span data-ttu-id="2b690-115">İş parçacığı CLR yeniden girer ve daha fazla kilitleri alın veya değiştirilen sürecinde olan yapıları incelemek çalışırsa, bu yapıları tutarsız bir durumda olabilir.</span><span class="sxs-lookup"><span data-stu-id="2b690-115">If the thread re-enters the CLR and tries to take more locks or inspect structures that were in the process of being modified, these structures might be in an inconsistent state.</span></span> <span data-ttu-id="2b690-116">Kilitlenmeler ve erişim ihlalleri kolayca bu gibi durumlarda oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="2b690-116">Deadlocks and access violations can easily occur in such situations.</span></span>  
  
 <span data-ttu-id="2b690-117">Genel olarak, ne zaman geçirme olmayan profil oluşturucu yürütür kod içinde bir [Icorprofilercallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) yöntemi ve çağrılar bir `ICorProfilerInfo` yöntemi geçerli parametrelerle, kilitlenme veya gerekir bir erişim ihlali alıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="2b690-117">In general, when a non-hijacking profiler executes code inside an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method and calls into an `ICorProfilerInfo` method with valid parameters, it should not deadlock or receive an access violation.</span></span> <span data-ttu-id="2b690-118">Örneğin, içinde çalışan Profil Oluşturucu kod [Icorprofilercallback::classloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) yöntemi isteyin sınıfı hakkında bilgi için çağırarak [Icorprofilerınfo2::getclassıdınfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) yöntem.</span><span class="sxs-lookup"><span data-stu-id="2b690-118">For example, profiler code that runs inside the [ICorProfilerCallback::ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) method may ask for information about the class by calling the [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) method.</span></span> <span data-ttu-id="2b690-119">Bilgi kullanılamaz olduğunu belirtmek için bir CORPROF_E_DATAINCOMPLETE HRESULT kodu alabilirsiniz; Ancak, bunu değil kilitlenme veya erişim ihlali alırsınız.</span><span class="sxs-lookup"><span data-stu-id="2b690-119">The code might receive an CORPROF_E_DATAINCOMPLETE HRESULT to indicate that information is unavailable; however, it will not deadlock or receive an access violation.</span></span> <span data-ttu-id="2b690-120">Bu çağrılar sınıfının `ICorProfilerInfo` gelen yapıldığı için zaman uyumlu olarak adlandırılan bir `ICorProfilerCallback` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="2b690-120">This class of calls into `ICorProfilerInfo` are called synchronous, because they are made from an `ICorProfilerCallback` method.</span></span>  
  
 <span data-ttu-id="2b690-121">Ancak, yönetilen bir iş parçacığı yürütmelerinin içinde değil kod bir `ICorProfilerCallback` yöntemi zaman uyumsuz bir çağrı yapmak için değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="2b690-121">However, a managed thread that executes code that is not within an `ICorProfilerCallback` method is considered to be making an asynchronous call.</span></span> <span data-ttu-id="2b690-122">.NET Framework sürüm 1'da, ne zaman uyumsuz bir çağrının gerçekleşebilir belirlemek zordur.</span><span class="sxs-lookup"><span data-stu-id="2b690-122">In the .NET Framework version 1, it was difficult to determine what might happen in an asynchronous call.</span></span> <span data-ttu-id="2b690-123">Çağrı, kilitlenme, kilitlenme veya geçersiz bir yanıt verin.</span><span class="sxs-lookup"><span data-stu-id="2b690-123">The call could deadlock, crash, or give an invalid answer.</span></span> <span data-ttu-id="2b690-124">.NET Framework sürüm 2.0, bu sorunu önlemenize yardımcı olmak üzere bazı basit denetimleri sunmuştur.</span><span class="sxs-lookup"><span data-stu-id="2b690-124">The .NET Framework version 2.0 introduced some simple checks to help you avoid this problem.</span></span> <span data-ttu-id="2b690-125">.NET Framework güvenli olmayan bir çağırırsanız 2.0, `ICorProfilerInfo` zaman uyumsuz olarak işlev, CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT ile başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="2b690-125">In the .NET Framework 2.0, if you call an unsafe `ICorProfilerInfo` function asynchronously, it fails with an CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.</span></span>  
  
 <span data-ttu-id="2b690-126">Genel olarak, zaman uyumsuz çağrılar güvenli değildir.</span><span class="sxs-lookup"><span data-stu-id="2b690-126">In general, asynchronous calls are not safe.</span></span> <span data-ttu-id="2b690-127">Ancak, aşağıdaki yöntemlerden güvenli ve özellikle zaman uyumsuz çağrılar destekler:</span><span class="sxs-lookup"><span data-stu-id="2b690-127">However, the following methods are safe and specifically support asynchronous calls:</span></span>  
  
-   [<span data-ttu-id="2b690-128">GetEventMask</span><span class="sxs-lookup"><span data-stu-id="2b690-128">GetEventMask</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [<span data-ttu-id="2b690-129">SetEventMask</span><span class="sxs-lookup"><span data-stu-id="2b690-129">SetEventMask</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [<span data-ttu-id="2b690-130">Getcurrentthreadıd</span><span class="sxs-lookup"><span data-stu-id="2b690-130">GetCurrentThreadID</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [<span data-ttu-id="2b690-131">GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="2b690-131">GetThreadContext</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [<span data-ttu-id="2b690-132">GetThreadAppDomain</span><span class="sxs-lookup"><span data-stu-id="2b690-132">GetThreadAppDomain</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [<span data-ttu-id="2b690-133">Getfunctionfromıp</span><span class="sxs-lookup"><span data-stu-id="2b690-133">GetFunctionFromIP</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [<span data-ttu-id="2b690-134">Getfunctionınfo</span><span class="sxs-lookup"><span data-stu-id="2b690-134">GetFunctionInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [<span data-ttu-id="2b690-135">Getfunctionınfo2</span><span class="sxs-lookup"><span data-stu-id="2b690-135">GetFunctionInfo2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [<span data-ttu-id="2b690-136">Getcodeınfo</span><span class="sxs-lookup"><span data-stu-id="2b690-136">GetCodeInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [<span data-ttu-id="2b690-137">Getcodeınfo2</span><span class="sxs-lookup"><span data-stu-id="2b690-137">GetCodeInfo2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [<span data-ttu-id="2b690-138">Getmoduleınfo</span><span class="sxs-lookup"><span data-stu-id="2b690-138">GetModuleInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [<span data-ttu-id="2b690-139">Getclassıdınfo</span><span class="sxs-lookup"><span data-stu-id="2b690-139">GetClassIDInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [<span data-ttu-id="2b690-140">Getclassıdınfo2</span><span class="sxs-lookup"><span data-stu-id="2b690-140">GetClassIDInfo2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [<span data-ttu-id="2b690-141">Isarrayclass</span><span class="sxs-lookup"><span data-stu-id="2b690-141">IsArrayClass</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [<span data-ttu-id="2b690-142">Setfunctionıdmapper</span><span class="sxs-lookup"><span data-stu-id="2b690-142">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [<span data-ttu-id="2b690-143">DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="2b690-143">DoStackSnapshot</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 <span data-ttu-id="2b690-144">Ek bilgi için bkz: Giriş [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE sahibiz neden](http://go.microsoft.com/fwlink/?LinkId=169156) CLR Profil oluşturma API Web günlüğündeki.</span><span class="sxs-lookup"><span data-stu-id="2b690-144">For additional information, see the entry [Why we have CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](http://go.microsoft.com/fwlink/?LinkId=169156) in the CLR Profiling API blog.</span></span>  
  
## <a name="triggering-garbage-collections"></a><span data-ttu-id="2b690-145">Tetikleyici çöp koleksiyonları</span><span class="sxs-lookup"><span data-stu-id="2b690-145">Triggering Garbage Collections</span></span>  
 <span data-ttu-id="2b690-146">Bu senaryo bir geri çağırma yöntemi içinde çalışan bir profil oluşturucu içerir (örneğin, aşağıdakilerden birini `ICorProfilerCallback` yöntemleri) çöp toplama engelliyor.</span><span class="sxs-lookup"><span data-stu-id="2b690-146">This scenario involves a profiler that is running inside a callback method (for example, one of the `ICorProfilerCallback` methods) that forbids garbage collection.</span></span> <span data-ttu-id="2b690-147">Profil Oluşturucu bilgilendirici bir yöntemi çağırmak çalışırsa (örneğin, bir yöntem `ICorProfilerInfo` arabirimi) çöp toplama tetikleyin, bilgilendirici yöntem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="2b690-147">If the profiler tries to call an informational method (for example, a method on the `ICorProfilerInfo` interface) that might trigger a garbage collection, the informational method fails with a CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.</span></span>  
  
 <span data-ttu-id="2b690-148">Aşağıdaki tabloda çöp koleksiyonları yasaklamaz geri arama yöntemleri ve çöp koleksiyonları tetikleyebilir bilgilendirme yöntemleri görüntüler.</span><span class="sxs-lookup"><span data-stu-id="2b690-148">The following table displays the callback methods that forbid garbage collections, and informational methods that may trigger garbage collections.</span></span> <span data-ttu-id="2b690-149">Profil Oluşturucu listelenen geri çağırma yöntemlerden birini içinde yürütür ve listelenen bilgilendirme yöntemlerden birini çağırır bilgilendirme yöntem CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="2b690-149">If the profiler executes inside one of the listed callback methods and calls one of the listed informational methods, that informational method fails with a CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.</span></span>  
  
|<span data-ttu-id="2b690-150">Çöp koleksiyonlarının yasaklamaz geri arama yöntemleri</span><span class="sxs-lookup"><span data-stu-id="2b690-150">Callback methods that forbid garbage collections</span></span>|<span data-ttu-id="2b690-151">Çöp koleksiyonlarının tetiklemek bilgilendirme yöntemleri</span><span class="sxs-lookup"><span data-stu-id="2b690-151">Informational methods that trigger garbage collections</span></span>|  
|------------------------------------------------------|------------------------------------------------------------|  
|[<span data-ttu-id="2b690-152">ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="2b690-152">ThreadAssignedToOSThread</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [<span data-ttu-id="2b690-153">ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="2b690-153">ExceptionUnwindFunctionEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [<span data-ttu-id="2b690-154">ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="2b690-154">ExceptionUnwindFunctionLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [<span data-ttu-id="2b690-155">ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="2b690-155">ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [<span data-ttu-id="2b690-156">ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="2b690-156">ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [<span data-ttu-id="2b690-157">ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="2b690-157">ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [<span data-ttu-id="2b690-158">RuntimeSuspendStarted</span><span class="sxs-lookup"><span data-stu-id="2b690-158">RuntimeSuspendStarted</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [<span data-ttu-id="2b690-159">RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="2b690-159">RuntimeSuspendFinished</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [<span data-ttu-id="2b690-160">RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="2b690-160">RuntimeSuspendAborted</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [<span data-ttu-id="2b690-161">RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="2b690-161">RuntimeThreadSuspended</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [<span data-ttu-id="2b690-162">RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="2b690-162">RuntimeThreadResumed</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [<span data-ttu-id="2b690-163">MovedReferences</span><span class="sxs-lookup"><span data-stu-id="2b690-163">MovedReferences</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [<span data-ttu-id="2b690-164">ObjectReferences</span><span class="sxs-lookup"><span data-stu-id="2b690-164">ObjectReferences</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [<span data-ttu-id="2b690-165">ObjectsAllocatedByClass</span><span class="sxs-lookup"><span data-stu-id="2b690-165">ObjectsAllocatedByClass</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [<span data-ttu-id="2b690-166">RootReferences2</span><span class="sxs-lookup"><span data-stu-id="2b690-166">RootReferences2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [<span data-ttu-id="2b690-167">HandleCreated</span><span class="sxs-lookup"><span data-stu-id="2b690-167">HandleCreated</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [<span data-ttu-id="2b690-168">HandleDestroyed</span><span class="sxs-lookup"><span data-stu-id="2b690-168">HandleDestroyed</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [<span data-ttu-id="2b690-169">GarbageCollectionStarted</span><span class="sxs-lookup"><span data-stu-id="2b690-169">GarbageCollectionStarted</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [<span data-ttu-id="2b690-170">GarbageCollectionFinished</span><span class="sxs-lookup"><span data-stu-id="2b690-170">GarbageCollectionFinished</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[<span data-ttu-id="2b690-171">Getılfunctionbodyallocator</span><span class="sxs-lookup"><span data-stu-id="2b690-171">GetILFunctionBodyAllocator</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [<span data-ttu-id="2b690-172">Setılfunctionbody</span><span class="sxs-lookup"><span data-stu-id="2b690-172">SetILFunctionBody</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [<span data-ttu-id="2b690-173">Setılınstrumentedcodemap</span><span class="sxs-lookup"><span data-stu-id="2b690-173">SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [<span data-ttu-id="2b690-174">ForceGC</span><span class="sxs-lookup"><span data-stu-id="2b690-174">ForceGC</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [<span data-ttu-id="2b690-175">GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="2b690-175">GetClassFromToken</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [<span data-ttu-id="2b690-176">GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="2b690-176">GetClassFromTokenAndTypeArgs</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [<span data-ttu-id="2b690-177">GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="2b690-177">GetFunctionFromTokenAndTypeArgs</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [<span data-ttu-id="2b690-178">Getappdomainınfo</span><span class="sxs-lookup"><span data-stu-id="2b690-178">GetAppDomainInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [<span data-ttu-id="2b690-179">EnumModules</span><span class="sxs-lookup"><span data-stu-id="2b690-179">EnumModules</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [<span data-ttu-id="2b690-180">RequestProfilerDetach</span><span class="sxs-lookup"><span data-stu-id="2b690-180">RequestProfilerDetach</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [<span data-ttu-id="2b690-181">GetAppDomainsContainingModule</span><span class="sxs-lookup"><span data-stu-id="2b690-181">GetAppDomainsContainingModule</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a><span data-ttu-id="2b690-182">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2b690-182">See Also</span></span>  
 [<span data-ttu-id="2b690-183">Icorprofilercallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-183">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="2b690-184">Icorprofilercallback2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-184">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="2b690-185">Icorprofilercallback3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-185">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [<span data-ttu-id="2b690-186">Icorprofilerınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-186">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2b690-187">Icorprofilerınfo2 arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-187">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="2b690-188">Icorprofilerınfo3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="2b690-188">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="2b690-189">Profil oluşturma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="2b690-189">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="2b690-190">Profil oluşturma</span><span class="sxs-lookup"><span data-stu-id="2b690-190">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)