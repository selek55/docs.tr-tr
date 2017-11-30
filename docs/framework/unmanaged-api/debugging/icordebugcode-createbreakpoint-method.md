---
title: "ICorDebugCode::CreateBreakpoint Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="a7031-102">ICorDebugCode::CreateBreakpoint Yöntemi</span><span class="sxs-lookup"><span data-stu-id="a7031-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="a7031-103">Bu kod kesimi belirtilen uzaklığında bir kesme noktası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a7031-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7031-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a7031-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7031-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a7031-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="a7031-106">[in] Uzaklığı kesme noktası oluşturmak.</span><span class="sxs-lookup"><span data-stu-id="a7031-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="a7031-107">[out] Kesme noktası temsil eden bir "ICorDebugFunctionBreakpoint" nesnesinin adresi için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="a7031-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7031-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a7031-108">Remarks</span></span>  
 <span data-ttu-id="a7031-109">Kesme noktası etkinleştirilmeden önce işlem nesnesine eklenmelidir.</span><span class="sxs-lookup"><span data-stu-id="a7031-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="a7031-110">Bu kodu Microsoft Ara dili (MSIL) koddur ve bir tam zamanında (JIT) yoktur-kesme kodunun derlenmiş, yerel sürümünü JIT derlenmiş kod da uygulanır.</span><span class="sxs-lookup"><span data-stu-id="a7031-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="a7031-111">(Aynı kodu daha sonra JIT derlenmiş ise geçerlidir.)</span><span class="sxs-lookup"><span data-stu-id="a7031-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7031-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a7031-112">Requirements</span></span>  
 <span data-ttu-id="a7031-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7031-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7031-114">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7031-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7031-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7031-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7031-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7031-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7031-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a7031-117">See Also</span></span>  
 