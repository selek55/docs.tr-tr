---
title: "Hizmet Uygulaması Programlama Mimarisi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e9c16f2e603a3ce9bbc59be4e01aa492239d2c63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="service-application-programming-architecture"></a><span data-ttu-id="12e22-102">Hizmet Uygulaması Programlama Mimarisi</span><span class="sxs-lookup"><span data-stu-id="12e22-102">Service Application Programming Architecture</span></span>
<span data-ttu-id="12e22-103">Windows hizmet uygulamaları öğesinden devralınan bir sınıf temel <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="12e22-103">Windows Service applications are based on a class that inherits from the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="12e22-104">Bu sınıftan yöntemleri geçersiz kılmak ve bunları hizmetinizin nasıl davranacağını belirlemek işlevsellik tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="12e22-104">You override methods from this class and define functionality for them to determine how your service behaves.</span></span>  
  
 <span data-ttu-id="12e22-105">Hizmet oluşturulmasında yer ana sınıfları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="12e22-105">The main classes involved in service creation are:</span></span>  
  
-   <span data-ttu-id="12e22-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— Yöntemleri geçersiz kılar <xref:System.ServiceProcess.ServiceBase> hizmet oluştururken, sınıf ve nasıl hizmetinizin Bu sınıf devralınan belirlemek için kod tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="12e22-106"><xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — You override methods from the <xref:System.ServiceProcess.ServiceBase> class when creating a service and define the code to determine how your service functions in this inherited class.</span></span>  
  
-   <span data-ttu-id="12e22-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>ve <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> — bu sınıfların yüklemek ve hizmetinizi kaldırmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="12e22-107"><xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> and <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> —You use these classes to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="12e22-108">Ayrıca, adlı bir sınıf <xref:System.ServiceProcess.ServiceController> hizmeti işlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="12e22-108">In addition, a class named <xref:System.ServiceProcess.ServiceController> can be used to manipulate the service itself.</span></span> <span data-ttu-id="12e22-109">Bu sınıf bir hizmet oluşturmada yer alan değildir, ancak başlatmak ve hizmetini durdurun, komutları ona geçirmek ve numaralandırmalar bir dizi dönmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="12e22-109">This class is not involved in the creation of a service, but can be used to start and stop the service, pass commands to it, and return a series of enumerations.</span></span>  
  
## <a name="defining-your-services-behavior"></a><span data-ttu-id="12e22-110">Hizmetinizin davranış tanımlama</span><span class="sxs-lookup"><span data-stu-id="12e22-110">Defining Your Service's Behavior</span></span>  
 <span data-ttu-id="12e22-111">Hizmet sınıfında, hizmetler Denetimi Yöneticisi'nde, hizmetin durumunu değiştirildiğinde ne olacağını belirleyen temel sınıf işlevleri geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="12e22-111">In your service class, you override base class functions that determine what happens when the state of your service is changed in the Services Control Manager.</span></span> <span data-ttu-id="12e22-112"><xref:System.ServiceProcess.ServiceBase> Sınıfı özel davranış eklemeyi Geçersiz kılabileceğiniz aşağıdaki yöntemleri sunar.</span><span class="sxs-lookup"><span data-stu-id="12e22-112">The <xref:System.ServiceProcess.ServiceBase> class exposes the following methods, which you can override to add custom behavior.</span></span>  
  
|<span data-ttu-id="12e22-113">Yöntem</span><span class="sxs-lookup"><span data-stu-id="12e22-113">Method</span></span>|<span data-ttu-id="12e22-114">İçin geçersiz kılın</span><span class="sxs-lookup"><span data-stu-id="12e22-114">Override to</span></span>|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|<span data-ttu-id="12e22-115">Hizmetiniz çalışmaya başladığında hangi eylemlerin gerçekleştirilmesi gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-115">Indicate what actions should be taken when your service starts running.</span></span> <span data-ttu-id="12e22-116">Hizmetinizin faydalı bir iş gerçekleştirmesi bu yordamdaki kod yazmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="12e22-116">You must write code in this procedure for your service to perform useful work.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|<span data-ttu-id="12e22-117">Hizmet duraklatıldığında ne olacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-117">Indicate what should happen when your service is paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|<span data-ttu-id="12e22-118">Hizmetiniz çalışmayı durdurduğunda ne olacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-118">Indicate what should happen when your service stops running.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|<span data-ttu-id="12e22-119">Hizmetinizi duraklatıldıktan sonra normal işlevine devam ettiğinde ne olacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-119">Indicate what should happen when your service resumes normal functioning after being paused.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|<span data-ttu-id="12e22-120">Hizmetinizi o anda çalışıyorsa, ne, kapatma, sisteminizi önce olması gerektiğini belirtin.</span><span class="sxs-lookup"><span data-stu-id="12e22-120">Indicate what should happen just prior to your system shutting down, if your service is running at that time.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|<span data-ttu-id="12e22-121">Hizmetiniz özel bir komut aldığında ne olacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-121">Indicate what should happen when your service receives a custom command.</span></span> <span data-ttu-id="12e22-122">Özel komutlar hakkında daha fazla bilgi için MSDN çevrimiçi konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="12e22-122">For more information on custom commands, see MSDN online.</span></span>|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|<span data-ttu-id="12e22-123">Düşük pil ya da askıya alınmış işlemi gibi bir güç yönetimi olayı alındığında, hizmetin nasıl tepki gösterir.</span><span class="sxs-lookup"><span data-stu-id="12e22-123">Indicate how the service should respond when a power management event is received, such as a low battery or suspended operation.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="12e22-124">Bu yöntemler ömrü aracılığıyla hizmet taşır durumları temsil eder; sonraki hizmet geçişleri bir durumdan.</span><span class="sxs-lookup"><span data-stu-id="12e22-124">These methods represent states that the service moves through in its lifetime; the service transitions from one state to the next.</span></span> <span data-ttu-id="12e22-125">Örneğin, hiçbir zaman yanıt verecek şekilde hizmet alırsınız bir <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> önce komutu <xref:System.ServiceProcess.ServiceBase.OnStart%2A> çağrıldı.</span><span class="sxs-lookup"><span data-stu-id="12e22-125">For example, you will never get the service to respond to an <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> command before <xref:System.ServiceProcess.ServiceBase.OnStart%2A> has been called.</span></span>  
  
 <span data-ttu-id="12e22-126">Diğer birçok özellik ve ilgilendiğiniz yöntemleri vardır.</span><span class="sxs-lookup"><span data-stu-id="12e22-126">There are several other properties and methods that are of interest.</span></span> <span data-ttu-id="12e22-127">Bu güncelleştirmeler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="12e22-127">These include:</span></span>  
  
-   <span data-ttu-id="12e22-128"><xref:System.ServiceProcess.ServiceBase.Run%2A> Yöntemi <xref:System.ServiceProcess.ServiceBase> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="12e22-128">The <xref:System.ServiceProcess.ServiceBase.Run%2A> method on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="12e22-129">Bu hizmet için ana giriş noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="12e22-129">This is the main entry point for the service.</span></span> <span data-ttu-id="12e22-130">Windows hizmet şablonu kullanarak bir hizmet oluşturduğunuzda, kodu uygulamanızın eklenir `Main` hizmetini çalıştırmak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="12e22-130">When you create a service using the Windows Service template, code is inserted in your application's `Main` method to run the service.</span></span> <span data-ttu-id="12e22-131">Bu kod şu şekildedir:</span><span class="sxs-lookup"><span data-stu-id="12e22-131">This code looks like this:</span></span>  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  <span data-ttu-id="12e22-132">Bu örnekleri türünde bir dizi kullanmak <xref:System.ServiceProcess.ServiceBase>hangi içine uygulamanızı içeren her bir hizmet eklenebilir ve ardından tüm hizmetlerin birlikte çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="12e22-132">These examples use an array of type <xref:System.ServiceProcess.ServiceBase>, into which each service your application contains can be added, and then all of the services can be run together.</span></span> <span data-ttu-id="12e22-133">Yalnızca tek bir hizmeti oluşturuyorsanız, ancak, dizi kullanma ve yalnızca içinden devralma yeni bir nesne bildirme tercih edebileceğiniz <xref:System.ServiceProcess.ServiceBase> ve ardından çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="12e22-133">If you are only creating a single service, however, you might choose not to use the array and simply declare a new object inheriting from <xref:System.ServiceProcess.ServiceBase> and then run it.</span></span> <span data-ttu-id="12e22-134">Bir örnek için bkz: [nasıl yapılır: Hizmetleri programlamayla yazma](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="12e22-134">For an example, see [How to: Write Services Programmatically](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).</span></span>  
  
-   <span data-ttu-id="12e22-135">Özellikleri, bir dizi <xref:System.ServiceProcess.ServiceBase> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="12e22-135">A series of properties on the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="12e22-136">Bu hizmet yöntemleri çağrılabilir belirler.</span><span class="sxs-lookup"><span data-stu-id="12e22-136">These determine what methods can be called on your service.</span></span> <span data-ttu-id="12e22-137">Örneğin, <xref:System.ServiceProcess.ServiceBase.CanStop%2A> özelliği ayarlanmış `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> hizmetinizi yöntemi çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="12e22-137">For example, when the <xref:System.ServiceProcess.ServiceBase.CanStop%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method on your service can be called.</span></span> <span data-ttu-id="12e22-138">Zaman <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> özelliği ayarlanmış `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> ve <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> yöntemleri çağrılamaz.</span><span class="sxs-lookup"><span data-stu-id="12e22-138">When the <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> property is set to `true`, the <xref:System.ServiceProcess.ServiceBase.OnPause%2A> and <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> methods can be called.</span></span> <span data-ttu-id="12e22-139">Ayarladığınızda bu özelliklerden birini `true`, daha sonra geçersiz kılma ve işleme ilişkili yöntemleri için tanımlayın.</span><span class="sxs-lookup"><span data-stu-id="12e22-139">When you set one of these properties to `true`, you should then override and define processing for the associated methods.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12e22-140">Hizmetinizi en az kılmalıdır <xref:System.ServiceProcess.ServiceBase.OnStart%2A> ve <xref:System.ServiceProcess.ServiceBase.OnStop%2A> yararlı olacak.</span><span class="sxs-lookup"><span data-stu-id="12e22-140">Your service must override at least <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> to be useful.</span></span>  
  
 <span data-ttu-id="12e22-141">Adlı bir bileşen de kullanabilirsiniz <xref:System.ServiceProcess.ServiceController> ile iletişim kurmasını ve var olan bir hizmeti davranışını denetler.</span><span class="sxs-lookup"><span data-stu-id="12e22-141">You can also use a component called the <xref:System.ServiceProcess.ServiceController> to communicate with and control the behavior of an existing service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e22-142">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="12e22-142">See Also</span></span>  
 [<span data-ttu-id="12e22-143">Windows hizmet uygulamalarına giriş</span><span class="sxs-lookup"><span data-stu-id="12e22-143">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="12e22-144">Nasıl yapılır: Windows Hizmetleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="12e22-144">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)