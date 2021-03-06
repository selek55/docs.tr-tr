---
title: "COM+ ve ServiceModel İşlemlerini Karşılaştırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e3df31060a9c71e0b2868aa34373bca221fa79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>COM+ ve ServiceModel İşlemlerini Karşılaştırma
Bu konuda işlem COM + kullanarak hizmet davranışına benzetmek nasıl ele alınmıştır [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] öznitelikleri <xref:System.ServiceModel> ad alanı sağlar.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>COM + ServiceModel öznitelikleri kullanarak öykünmesini yapma  
 Aşağıdaki tabloda karşılaştırır <xref:System.EnterpriseServices.TransactionOption> numaralandırması oluşturmak için kullanılan bir `EnterpriseServices` işlem ve nasıl bunlar için bağıntısını [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] öznitelikleri <xref:System.ServiceModel> ad alanı sağlar.  
  
|COM + özniteliği|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]öznitelikleri|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute>ayarlanmış <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>olan `true`.<br /><br /> `TransactionFlow` Bağlama öğesi içinde özniteliktir `false`.|  
|Gerekli|<xref:System.ServiceModel.TransactionFlowAttribute>ayarlanmış <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>olan `true`.<br /><br /> `TransactionFlow` Bağlama öğesi içinde özniteliktir `true`.|  
|Desteklenir|Doğrudan bir eşdeğeri yoktur. İçin belirtilen davranışı genel olarak, benimsemeyi `Required` yerine.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>olan `false`.<br /><br /> `TransactionFlow` Bağlama öğesi içinde özniteliktir `false`.|  
|Devre dışı|Doğrudan bir eşdeğeri yoktur. İçin belirtilen davranışı genel olarak, benimsemeyi `NotSupported` yerine.|
