---
title: "ICorDebug::CanLaunchOrAttach Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CanLaunchOrAttach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5bd657c73dfaf7643405b4b657edeffa6e33cd68
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="5ef27-102">ICorDebug::CanLaunchOrAttach Yöntemi</span><span class="sxs-lookup"><span data-stu-id="5ef27-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="5ef27-103">Yeni bir işlem başlatılıyor veya belirtilen varolan işlemine iliştirme geçerli makine ve çalışma zamanı yapılandırma bağlamında mümkün olup olmadığını belirten bir HRESULT döndürür.</span><span class="sxs-lookup"><span data-stu-id="5ef27-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef27-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5ef27-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ef27-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="5ef27-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="5ef27-106">[in] Varolan bir işlemin kimliği.</span><span class="sxs-lookup"><span data-stu-id="5ef27-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="5ef27-107">[in] Geçirin `true` , Win32 hata ayıklama etkin durumdayken başlatmak plan veya etkin; tersi durumda, Win32 hata ayıklamaya eklemek için geçmesi durumunda `false`.</span><span class="sxs-lookup"><span data-stu-id="5ef27-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef27-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="5ef27-108">Return Value</span></span>  
 <span data-ttu-id="5ef27-109">Hata Ayıklama Hizmetleri yeni bir işlem başlatılıyor veya verilen işlemine iliştirme karar verirseniz S_OK geçerli makine ve çalışma zamanı yapılandırma hakkında bilgi verilir, mümkündür.</span><span class="sxs-lookup"><span data-stu-id="5ef27-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="5ef27-110">Olası HRESULT değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="5ef27-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="5ef27-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ef27-111">S_OK</span></span>  
  
-   <span data-ttu-id="5ef27-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="5ef27-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="5ef27-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="5ef27-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="5ef27-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="5ef27-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ef27-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5ef27-115">Remarks</span></span>  
 <span data-ttu-id="5ef27-116">Bu yöntem yalnızca bilgilendirme amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="5ef27-116">This method is purely informational.</span></span> <span data-ttu-id="5ef27-117">Arabirim, başlatmasını durdurmaz veya tarafından döndürülen değer bağımsız olarak bir işlem ekleme `CanLaunchOrAttach`.</span><span class="sxs-lookup"><span data-stu-id="5ef27-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="5ef27-118">Win32 hata ayıklama etkin durumdayken başlatın veya Win32 hata ayıklama etkin durumdayken bağlayın, geçirmek, düşünüyorsanız, `true` için `win32DebuggingEnabled`.</span><span class="sxs-lookup"><span data-stu-id="5ef27-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="5ef27-119">Tarafından döndürülen HRESULT `CanLaunchOrAttach` bu seçeneği kullanırsanız, farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="5ef27-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef27-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="5ef27-120">Requirements</span></span>  
 <span data-ttu-id="5ef27-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ef27-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef27-122">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ef27-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ef27-123">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ef27-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ef27-124">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef27-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef27-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5ef27-125">See Also</span></span>  
 [<span data-ttu-id="5ef27-126">Icordebug arabirimi</span><span class="sxs-lookup"><span data-stu-id="5ef27-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)