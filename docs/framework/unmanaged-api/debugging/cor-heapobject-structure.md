---
title: "COR_HEAPOBJECT Yapısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPOBJECT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPOBJECT
helpviewer_keywords: COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bcd971853707349bf0d60459cb46b0fea1e8a97b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="corheapobject-structure"></a><span data-ttu-id="219ac-102">COR_HEAPOBJECT Yapısı</span><span class="sxs-lookup"><span data-stu-id="219ac-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="219ac-103">Yönetilen yığında bir nesne hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="219ac-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219ac-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="219ac-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="219ac-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="219ac-105">Members</span></span>  
  
|<span data-ttu-id="219ac-106">Üye</span><span class="sxs-lookup"><span data-stu-id="219ac-106">Member</span></span>|<span data-ttu-id="219ac-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="219ac-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="219ac-108">Bellekteki nesne adresi.</span><span class="sxs-lookup"><span data-stu-id="219ac-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="219ac-109">Nesnesinin bayt olarak toplam boyutu.</span><span class="sxs-lookup"><span data-stu-id="219ac-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="219ac-110">A [cor_typeıd](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) nesne türünü temsil eden belirteci.</span><span class="sxs-lookup"><span data-stu-id="219ac-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="219ac-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="219ac-111">Remarks</span></span>  
 <span data-ttu-id="219ac-112">`COR_HEAPOBJECT`örnekleri numaralandırılırken tarafından alınabilir bir [Icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) çağırarak doldurulur arabirimi nesnesi [Icordebugprocess5::enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="219ac-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="219ac-113">A `COR_HEAPOBJECT` örneği yönetilen yığında canlı bir nesneyle ilgili ya da herhangi bir nesne tarafından kökü değil, ancak henüz atık toplayıcısı tarafından toplanan değil bir nesne hakkında bilgi sağlar.</span><span class="sxs-lookup"><span data-stu-id="219ac-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="219ac-114">Daha iyi performans için `COR_HEAPOBJECT.address` alan bir `CORDB_ADDRESS` Icordebugvalue yerine değeri arabirimi hata ayıklama API'si çoğunu kullanılan değer.</span><span class="sxs-lookup"><span data-stu-id="219ac-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="219ac-115">Verilen nesne adresi için bir Icordebugvalue nesnesi edinmek için iletebilirsiniz `CORDB_ADDRESS` değeri [Icordebugprocess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="219ac-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="219ac-116">Daha iyi performans için `COR_HEAPOBJECT.type` alan bir `COR_TYPEID` Icordebugtype yerine değeri arabirimi hata ayıklama API'si çoğunu kullanılan değer.</span><span class="sxs-lookup"><span data-stu-id="219ac-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="219ac-117">Icordebugtype nesne için belirtilen tür kimliği edinmek için iletebilirsiniz `COR_TYPEID` değeri [Icordebugprocess5::gettypefortypeıd](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="219ac-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="219ac-118">`COR_HEAPOBJECT` Yapısı başvuruları sayılan COM arabirimi içerir.</span><span class="sxs-lookup"><span data-stu-id="219ac-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="219ac-119">Aldığınız varsa bir `COR_HEAPOBJECT` çağırarak numaralandırıcı örneğinden [Icordebugheapenum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) yöntemi, daha sonra başvuru serbest bırakmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="219ac-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219ac-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="219ac-120">Requirements</span></span>  
 <span data-ttu-id="219ac-121">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="219ac-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219ac-122">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="219ac-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="219ac-123">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="219ac-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="219ac-124">**.NET framework sürümleri:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="219ac-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219ac-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="219ac-125">See Also</span></span>  
 [<span data-ttu-id="219ac-126">Hata ayıklama yapıları</span><span class="sxs-lookup"><span data-stu-id="219ac-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="219ac-127">Hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="219ac-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)