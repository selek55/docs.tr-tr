---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f2f0aad37fcd63e2345cd32a00b44412ed8c7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="1f56d-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Metodu</span><span class="sxs-lookup"><span data-stu-id="1f56d-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="1f56d-103">Aynı işlevleri [Getdebugınfo yöntemi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) yol dizesi sabit bir boyuta dize verilerini yapmak için bir sonlandırma null karakteri aşağıdaki sıfırlarla dışında `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="1f56d-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="1f56d-104">Doldurma yolu dize uzunluğu kendisi ise yalnızca verilen değerinden `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="1f56d-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="1f56d-105">Bu araçlar, fark PE dosyaları yazmak kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="1f56d-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f56d-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1f56d-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f56d-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="1f56d-107">Parameters</span></span>  
  
|<span data-ttu-id="1f56d-108">Parametre</span><span class="sxs-lookup"><span data-stu-id="1f56d-108">Parameter</span></span>|<span data-ttu-id="1f56d-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1f56d-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="1f56d-110">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="1f56d-110">Return Value</span></span>  
 <span data-ttu-id="1f56d-111">Döndürür `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1f56d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f56d-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1f56d-112">Requirements</span></span>  
 <span data-ttu-id="1f56d-113">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1f56d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f56d-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1f56d-114">See Also</span></span>  
 [<span data-ttu-id="1f56d-115">Isymunmanagedwriter4 arabirimi</span><span class="sxs-lookup"><span data-stu-id="1f56d-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)