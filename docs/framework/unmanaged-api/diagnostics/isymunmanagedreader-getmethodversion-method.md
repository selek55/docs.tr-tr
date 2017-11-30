---
title: ISymUnmanagedReader::GetMethodVersion Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b57407cb12e4315b6a144d157a201f857614d9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="344ab-102">ISymUnmanagedReader::GetMethodVersion Metodu</span><span class="sxs-lookup"><span data-stu-id="344ab-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="344ab-103">Yöntem sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="344ab-103">Gets the method version.</span></span> <span data-ttu-id="344ab-104">Yöntemi sürüm 1'den başlar ve yöntemi derlenmiştir her zaman artırılır.</span><span class="sxs-lookup"><span data-stu-id="344ab-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="344ab-105">Derleme değişiklik yapılmadan yönteme gerçekleşebilir.</span><span class="sxs-lookup"><span data-stu-id="344ab-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="344ab-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="344ab-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="344ab-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="344ab-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="344ab-108">[in] Yöntemi, bir sürüm edinmek.</span><span class="sxs-lookup"><span data-stu-id="344ab-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="344ab-109">[out] Bir işaretçi bir değişkene yöntemi sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="344ab-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="344ab-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="344ab-110">Return Value</span></span>  
 <span data-ttu-id="344ab-111">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="344ab-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="344ab-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="344ab-112">Requirements</span></span>  
 <span data-ttu-id="344ab-113">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="344ab-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344ab-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="344ab-114">See Also</span></span>  
 [<span data-ttu-id="344ab-115">Isymunmanagedreader arabirimi</span><span class="sxs-lookup"><span data-stu-id="344ab-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)