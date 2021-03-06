---
title: ICorDebugChain::GetStackRange Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37a9be7924a6d9c1f1d78bd10f9642fff22036bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange Metodu
Yığın kesiminin adres aralığı için bu zincirini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStart`  
 [out] Bir işaretçi bir `CORDB_ADDRESS` yığın kesiminin başlangıç adresi değer.  
  
 `pEnd`  
 [out] Bir işaretçi bir `CORDB_ADDRESS` yığın kesiminin bitiş adresi değer.  
  
## <a name="remarks"></a>Açıklamalar  
 Sayısal aralığın yalnızca yığın çerçeve konumları bir karşılaştırması için anlamlıdır. Yığında gerçekte depolanan hakkında varsayımlar yapamazsınız.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
