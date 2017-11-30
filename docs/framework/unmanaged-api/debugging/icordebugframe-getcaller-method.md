---
title: ICorDebugFrame::GetCaller Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0f426823b0076a8d6bee1b39a7cdcdf618dad90
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="588cf-102">ICorDebugFrame::GetCaller Metodu</span><span class="sxs-lookup"><span data-stu-id="588cf-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="588cf-103">Bir işaretçi olarak adlandırılan bu çerçeve geçerli zincirinde Icordebugframe nesnesi alır.</span><span class="sxs-lookup"><span data-stu-id="588cf-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588cf-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="588cf-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="588cf-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="588cf-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="588cf-106">[out] Adresine bir işaretçi bir `ICorDebugFrame` arama çerçeveyi temsil eden nesne.</span><span class="sxs-lookup"><span data-stu-id="588cf-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="588cf-107">Bu değer çağrılan çerçeve geçerli zincirindeki en dıştaki çerçeve ise null şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="588cf-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="588cf-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="588cf-108">Requirements</span></span>  
 <span data-ttu-id="588cf-109">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="588cf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="588cf-110">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="588cf-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="588cf-111">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="588cf-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="588cf-112">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="588cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>