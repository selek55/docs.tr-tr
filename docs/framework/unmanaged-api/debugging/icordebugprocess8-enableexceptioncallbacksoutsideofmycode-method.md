---
title: "ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de3622498e8417a961e0d4708c53527a833ef2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a><span data-ttu-id="a02e9-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a02e9-102">ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode Method</span></span>
<span data-ttu-id="a02e9-103">[Desteklenen [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] ve sonraki sürümlerinde]</span><span class="sxs-lookup"><span data-stu-id="a02e9-103">[Supported in the [!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="a02e9-104">Etkinleştirir ya da belirli türlerdeki devre dışı bırakır [Icordebugmanagedcallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) özel durum geri aramalar.</span><span class="sxs-lookup"><span data-stu-id="a02e9-104">Enables or disables certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a02e9-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a02e9-105">Syntax</span></span>  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a02e9-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a02e9-106">Parameters</span></span>  
 `enableExceptionsOutsideOfJMC`  
 <span data-ttu-id="a02e9-107">[in]</span><span class="sxs-lookup"><span data-stu-id="a02e9-107">[in]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a02e9-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a02e9-108">Remarks</span></span>  
 <span data-ttu-id="a02e9-109">Varsa değerini `enableExceptionsOutsideOfJMC` olan `false`:</span><span class="sxs-lookup"><span data-stu-id="a02e9-109">If the value of `enableExceptionsOutsideOfJMC` is `false`:</span></span>  
  
-   <span data-ttu-id="a02e9-110">Bir DEBUG_EXCEPTION_FIRST_CHANCE özel çağırma işleminde hata ayıklayıcısı için yol açmaz.</span><span class="sxs-lookup"><span data-stu-id="a02e9-110">A DEBUG_EXCEPTION_FIRST_CHANCE exception will not result in a callback to the debugger.</span></span>  
  
-   <span data-ttu-id="a02e9-111">Özel durum hiç kullanıcı koda çıkışları DEBUG_EXCEPTION_CATCH_HANDLER_FOUND özel durum çağırma işleminde hata ayıklayıcıya neden olur değil (diğer bir deyişle, bir özel durum işleyici bir özel durum kaynaktan yoluna JustMyCode veya JMC olarak işaretlenmiş yöntemi yok).</span><span class="sxs-lookup"><span data-stu-id="a02e9-111">A DEBUG_EXCEPTION_CATCH_HANDLER_FOUND exception will not result in a callback to the debugger if the exception never escapes into user code (that is, the path from an exception origin to an exception handler has no methods marked as JustMyCode, or JMC).</span></span>  
  
 <span data-ttu-id="a02e9-112">Varsayılan değer olan `enableExceptionsOutsideOfJMC` olan `true`.</span><span class="sxs-lookup"><span data-stu-id="a02e9-112">The default value of `enableExceptionsOutsideOfJMC` is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a02e9-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a02e9-113">Requirements</span></span>  
 <span data-ttu-id="a02e9-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a02e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a02e9-115">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a02e9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a02e9-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a02e9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a02e9-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a02e9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a02e9-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a02e9-118">See Also</span></span>  
 [<span data-ttu-id="a02e9-119">Icordebugprocess8 arabirimi</span><span class="sxs-lookup"><span data-stu-id="a02e9-119">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [<span data-ttu-id="a02e9-120">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="a02e9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)