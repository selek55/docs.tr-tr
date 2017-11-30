---
title: ICLRDataTarget3::GetExceptionContextRecord Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetContextRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c2e645222553f4000b300fa4f010ff81ff44d23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="95533-102">ICLRDataTarget3::GetExceptionContextRecord Metodu</span><span class="sxs-lookup"><span data-stu-id="95533-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="95533-103">Hedef işlemle ilişkili bağlam kaydı almak için ortak dil çalışma zamanı (CLR) veri erişim hizmeti tarafından çağrılır.</span><span class="sxs-lookup"><span data-stu-id="95533-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="95533-104">Örneğin, bir döküm hedef için bu aracılığıyla geçilen bağlamı kayda eşdeğer olacaktır `ExceptionParam` bağımsız değişkeni [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) işlevi Windows Kitaplığı'nda hata ayıklama yardımcı (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="95533-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95533-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="95533-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95533-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="95533-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="95533-107">[in] Giriş arabelleği bayt cinsinden boyutu.</span><span class="sxs-lookup"><span data-stu-id="95533-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="95533-108">Bu içerik kaydı uyabilecek kadar büyük olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="95533-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="95533-109">[out] Bir işaretçi bir `ULONG32` gerçekten arabelleğe yazılan bayt sayısı alan türü.</span><span class="sxs-lookup"><span data-stu-id="95533-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="95533-110">[out] İçerik kaydı kopyasını alan bir bellek arabelleği için bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="95533-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="95533-111">Özel durum kaydı olarak döndürülür bir [BAĞLAMI](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) türü.</span><span class="sxs-lookup"><span data-stu-id="95533-111">The exception record is returned as a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95533-112">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="95533-112">Return Value</span></span>  
 <span data-ttu-id="95533-113">Dönüş değeri `S_OK` başarı veya hata `HRESULT` hata kodu.</span><span class="sxs-lookup"><span data-stu-id="95533-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="95533-114">`HRESULT` Kodları içerebilir ancak aşağıdaki sınırlı değildir:</span><span class="sxs-lookup"><span data-stu-id="95533-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="95533-115">Dönüş kodu</span><span class="sxs-lookup"><span data-stu-id="95533-115">Return code</span></span>|<span data-ttu-id="95533-116">Açıklama</span><span class="sxs-lookup"><span data-stu-id="95533-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="95533-117">Yöntem başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="95533-117">Method succeeded.</span></span> <span data-ttu-id="95533-118">İçerik kaydı çıktı arabelleğine kopyalandı.</span><span class="sxs-lookup"><span data-stu-id="95533-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="95533-119">Hedefle ilişkili hiç içerik kayıttır.</span><span class="sxs-lookup"><span data-stu-id="95533-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="95533-120">Giriş arabelleği boyutu içerik kaydı uyabilecek kadar büyük değil.</span><span class="sxs-lookup"><span data-stu-id="95533-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95533-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="95533-121">Remarks</span></span>  
 <span data-ttu-id="95533-122">[BAĞLAM](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) olan Windows SDK'sı tarafından sağlanan üstbilgileri tanımlanan bir platforma özgü yapısı.</span><span class="sxs-lookup"><span data-stu-id="95533-122">[CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="95533-123">Bu yöntem, hata ayıklama uygulama yazıcı tarafından uygulanır.</span><span class="sxs-lookup"><span data-stu-id="95533-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95533-124">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="95533-124">Requirements</span></span>  
 <span data-ttu-id="95533-125">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95533-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95533-126">**Başlık:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="95533-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="95533-127">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95533-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95533-128">**.NET framework sürümleri:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95533-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95533-129">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="95533-129">See Also</span></span>  
 [<span data-ttu-id="95533-130">Iclrdatatarget3 arabirimi</span><span class="sxs-lookup"><span data-stu-id="95533-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="95533-131">GetExceptionRecord yöntemi</span><span class="sxs-lookup"><span data-stu-id="95533-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="95533-132">Getexceptionthreadıd yöntemi</span><span class="sxs-lookup"><span data-stu-id="95533-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)