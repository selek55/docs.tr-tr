---
title: "&lt;SeeAlso&gt; (C# programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 088445680375e1c1805f9fb4356fe98c730178e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="b264a-102">&lt;SeeAlso&gt; (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="b264a-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b264a-103">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b264a-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b264a-104">Parametreler</span><span class="sxs-lookup"><span data-stu-id="b264a-104">Parameters</span></span>  
 <span data-ttu-id="b264a-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="b264a-105">cref = " `member`"</span></span>  
 <span data-ttu-id="b264a-106">Bir üye ya da geçerli derleme ortamından çağrılacak kullanılabilir alan başvuru.</span><span class="sxs-lookup"><span data-stu-id="b264a-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b264a-107">Verilen code öğesi var ve geçirir derleyici denetler `member` çıktı XML öğesi adı.`member`</span><span class="sxs-lookup"><span data-stu-id="b264a-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="b264a-108">çift tırnak işaretleri içinde görünmesi gerekir ("").</span><span class="sxs-lookup"><span data-stu-id="b264a-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="b264a-109">Genel bir tür cref başvuru oluşturma hakkında daha fazla bilgi için bkz: [ \<bkz >](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="b264a-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b264a-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b264a-110">Remarks</span></span>  
 <span data-ttu-id="b264a-111">\<Seealso > etiketi bir Ayrıca bkz. bölümünde görünen isteyebilirsiniz metin belirtmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="b264a-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="b264a-112">Kullanım [ \<bkz >](../../../csharp/programming-guide/xmldoc/see.md) metin içindeki bir bağlantıdan belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="b264a-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="b264a-113">İle derleme [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) bir dosyaya işlem belgesi açıklamaları için.</span><span class="sxs-lookup"><span data-stu-id="b264a-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b264a-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="b264a-114">Example</span></span>  
 <span data-ttu-id="b264a-115">Bkz: [ \<Özet >](../../../csharp/programming-guide/xmldoc/summary.md) kullanma örneği için \<seealso >.</span><span class="sxs-lookup"><span data-stu-id="b264a-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b264a-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b264a-116">See Also</span></span>  
 [<span data-ttu-id="b264a-117">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="b264a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b264a-118">Belge açıklamaları için önerilen etiketler</span><span class="sxs-lookup"><span data-stu-id="b264a-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)