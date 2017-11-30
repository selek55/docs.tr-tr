---
title: "İçerik Bağlantısı"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a41c9a526895057a6c7e785abbaaa4e4cd2c490f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="the-context-connection"></a><span data-ttu-id="7c931-102">İçerik Bağlantısı</span><span class="sxs-lookup"><span data-stu-id="7c931-102">The Context Connection</span></span>
<span data-ttu-id="7c931-103">İç veri erişimi oldukça yaygın bir senaryo sorunudur.</span><span class="sxs-lookup"><span data-stu-id="7c931-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="7c931-104">Diğer bir deyişle, ortak dil çalışma zamanı (CLR) saklı yordam veya işlev yürütülürken aynı sunucuya erişmek istiyor.</span><span class="sxs-lookup"><span data-stu-id="7c931-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="7c931-105">Bir seçenektir kullanarak bir bağlantı oluşturmak için <xref:System.Data.SqlClient.SqlConnection>, yerel sunucuya işaret eden bir bağlantı dizesini belirtin ve bağlantıyı açın.</span><span class="sxs-lookup"><span data-stu-id="7c931-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="7c931-106">Bu oturum için kimlik bilgilerinin belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="7c931-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="7c931-107">Bağlantı saklı yordamı veya işlevi'den farklı veritabanı oturumunda, farklı olabilir `SET` seçenekleri, ayrı bir işlemde ise, geçici tablolarınızı görmez ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="7c931-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="7c931-108">Birisi bu sunucuya bağlı ve onu çağırmak için bir SQL deyimi, yönetilen saklı yordam veya işlev kodu SQL Server işleminde yürütüyor, demektir.</span><span class="sxs-lookup"><span data-stu-id="7c931-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="7c931-109">Saklı yordam veya işlev kendi işlem birlikte bu bağlantı bağlamında yürütmek için büyük olasılıkla istediğiniz `SET` seçenekleri ve benzeri.</span><span class="sxs-lookup"><span data-stu-id="7c931-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="7c931-110">Bu bağlamın bağlantısı çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7c931-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="7c931-111">İçerik Bağlantısı, kodunuzu başlangıçta çağrıldı bağlamda Transact-SQL deyimlerini yürütmek olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="7c931-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="7c931-112">Daha ayrıntılı bilgi için SQL Server Books Online'nın sürümü, kullanmakta olduğunuz SQL Server sürümü için bkz.</span><span class="sxs-lookup"><span data-stu-id="7c931-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="7c931-113">**SQL Server Çevrimiçi Kitapları**</span><span class="sxs-lookup"><span data-stu-id="7c931-113">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="7c931-114">İçerik Bağlantısı</span><span class="sxs-lookup"><span data-stu-id="7c931-114">The Context Connection</span></span>](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="7c931-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7c931-115">See Also</span></span>  
 [<span data-ttu-id="7c931-116">Yönetilen kodda SQL Server 2005'te nesneleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="7c931-116">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="7c931-117">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="7c931-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)