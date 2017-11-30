---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 104810fc24cfe7c4c6ddf7ee5ece9f16a345c80c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="b114e-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b114e-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="b114e-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b114e-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b114e-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="b114e-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b114e-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="b114e-105">Methods</span></span>  
 <span data-ttu-id="b114e-106">AsymmetricSecurityBindingElement sınıfı herhangi bir yöntem tanımlamıyor.</span><span class="sxs-lookup"><span data-stu-id="b114e-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b114e-107">Özellikler</span><span class="sxs-lookup"><span data-stu-id="b114e-107">Properties</span></span>  
 <span data-ttu-id="b114e-108">AsymmetricSecurityBindingElement sınıfı aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="b114e-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="b114e-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="b114e-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="b114e-110">Veri türü: dize</span><span class="sxs-lookup"><span data-stu-id="b114e-110">Data type: string</span></span>  
  
 <span data-ttu-id="b114e-111">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="b114e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b114e-112">İleti şifreleme ve bu bağlama için imzalama sırası.</span><span class="sxs-lookup"><span data-stu-id="b114e-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="b114e-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="b114e-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="b114e-114">Veri türü: boolean</span><span class="sxs-lookup"><span data-stu-id="b114e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b114e-115">Erişim türüne: salt okunur</span><span class="sxs-lookup"><span data-stu-id="b114e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b114e-116">Olup bağlama imza onayı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b114e-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b114e-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="b114e-117">Requirements</span></span>  
  
|<span data-ttu-id="b114e-118">MOF</span><span class="sxs-lookup"><span data-stu-id="b114e-118">MOF</span></span>|<span data-ttu-id="b114e-119">Bildirilen Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b114e-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b114e-120">Ad Alanı</span><span class="sxs-lookup"><span data-stu-id="b114e-120">Namespace</span></span>|<span data-ttu-id="b114e-121">İçinde tanımlanan root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b114e-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b114e-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b114e-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>