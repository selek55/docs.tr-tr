---
title: "DotNet command - .NET Core CLI yayımlama"
description: "Dotnet yayımlama komutu .NET Core projenizi bir dizine yayımlar."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d59ba8cf74a63c7d4a2234989477b5778fa0148f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-publish"></a><span data-ttu-id="ad685-103">DotNet yayımlama</span><span class="sxs-lookup"><span data-stu-id="ad685-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ad685-104">Ad</span><span class="sxs-lookup"><span data-stu-id="ad685-104">Name</span></span>

<span data-ttu-id="ad685-105">`dotnet publish`-Dağıtım barındırma sistem için bir klasöre uygulamayı ve bağımlılıklarını paketler.</span><span class="sxs-lookup"><span data-stu-id="ad685-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ad685-106">Özet</span><span class="sxs-lookup"><span data-stu-id="ad685-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ad685-107">.NET core 2.x</span><span class="sxs-lookup"><span data-stu-id="ad685-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad685-108">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad685-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ad685-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ad685-109">Description</span></span>

<span data-ttu-id="ad685-110">`dotnet publish`Uygulama derler, proje dosyasında belirtilen bağımlılıklarını aracılığıyla okur ve bir dizine dosyaları sonuç kümesini yayımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="ad685-111">Çıktı aşağıdakileri içerir:</span><span class="sxs-lookup"><span data-stu-id="ad685-111">The output will contain the following:</span></span>

* <span data-ttu-id="ad685-112">Ara dil (IL) ile bir derlemeyi kodda bir *dll* uzantısı.</span><span class="sxs-lookup"><span data-stu-id="ad685-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="ad685-113">*. deps.json* tüm proje bağımlılıklarını içeren dosya.</span><span class="sxs-lookup"><span data-stu-id="ad685-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="ad685-114">*. runtime.config.json* çalışma zamanı (örneğin, atık toplama türü) için diğer yapılandırma seçeneklerini yanı sıra uygulama bekler paylaşılan çalışma zamanı belirten dosyası.</span><span class="sxs-lookup"><span data-stu-id="ad685-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="ad685-115">Uygulama bağımlılıkları.</span><span class="sxs-lookup"><span data-stu-id="ad685-115">The application's dependencies.</span></span> <span data-ttu-id="ad685-116">Bunlar, NuGet önbellekten çıkış klasörüne kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="ad685-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="ad685-117">`dotnet publish` Komutunun çıktısını, dağıtım için bir barındırma sistemi hazır (örneğin, bir sunucu, PC, Mac, dizüstü) yürütme için ve yalnızca resmi olarak şekilde uygulama dağıtım için hazırlamak için desteklenir.</span><span class="sxs-lookup"><span data-stu-id="ad685-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="ad685-118">Projeyi belirtir. Dağıtım türü, bağlı olarak ana bilgisayar sistemi olabilir veya .NET Core üzerinde yüklü çalışma zamanı paylaşılmayan sahip.</span><span class="sxs-lookup"><span data-stu-id="ad685-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="ad685-119">Daha fazla bilgi için bkz: [.NET Core uygulama dağıtımı](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="ad685-120">Yayımlanmış bir uygulama dizin yapısı için bkz: [dizin yapısını](/aspnet/core/hosting/directory-structure).</span><span class="sxs-lookup"><span data-stu-id="ad685-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="ad685-121">Arguments</span><span class="sxs-lookup"><span data-stu-id="ad685-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ad685-122">Geçerli dizine belirtilmezse, varsayılan olarak yayımlamak için proje.</span><span class="sxs-lookup"><span data-stu-id="ad685-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="ad685-123">Seçenekler</span><span class="sxs-lookup"><span data-stu-id="ad685-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="ad685-124">.NET core 2.x</span><span class="sxs-lookup"><span data-stu-id="ad685-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ad685-125">Derleme yapılandırması tanımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-125">Defines the build configuration.</span></span> <span data-ttu-id="ad685-126">Varsayılan değer `Debug` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="ad685-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ad685-127">Uygulama için belirtilen yayımlar [hedef framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ad685-128">Proje dosyasında hedef Framework'ü belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad685-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="ad685-129">Son geri yükleme başarılı olsa bile çözümlenmesi için tüm bağımlılıkları zorlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="ad685-130">Bu silme ile eşdeğerdir *project.assets.json* dosya.</span><span class="sxs-lookup"><span data-stu-id="ad685-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="ad685-131">Komutu için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="ad685-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="ad685-132">Bir veya birkaç belirtir [hedef bildirimleri](../deploying/runtime-store.md) uygulamayla yayımlanan paket kümesini kırpma için kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="ad685-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="ad685-133">Bildirim dosyası çıkışını bir parçasıdır [ `dotnet store` komutu](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="ad685-134">Birden çok bildirimleri belirtmek için ekleyin bir `--manifest` her bildirimi için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="ad685-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="ad685-135">Bu seçenek, .NET Core 2.0 SDK'sı ile başlayarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ad685-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="ad685-136">Proje Proje başvuruları yoksayar ve yalnızca kök proje geri yükler.</span><span class="sxs-lookup"><span data-stu-id="ad685-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="ad685-137">Örtük bir geri yükleme komutu çalıştırırken gerçekleştirmez.</span><span class="sxs-lookup"><span data-stu-id="ad685-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ad685-138">Çıktı dizini yolunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad685-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="ad685-139">Belirtilmezse, varsayılan olarak *./bin/[configuration]/[framework]/* framework bağımlı dağıtım için veya *./bin/[configuration]/[framework]/[runtime]* kendi içinde bulunan bir dağıtım için.</span><span class="sxs-lookup"><span data-stu-id="ad685-139">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="ad685-140">Göreli bir yol sağlanırsa, oluşturulan çıktı dizini proje dosya konumu, geçerli çalışma dizini için görelidir.</span><span class="sxs-lookup"><span data-stu-id="ad685-140">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="ad685-141">Çalışma zamanı hedef makinede yüklü olması gerekmez için uygulamanızın ile .NET çekirdeği çalışma zamanı yayımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="ad685-142">Bir çalışma zamanı tanıtıcı belirtilirse, varsayılan değeri olduğu `true`.</span><span class="sxs-lookup"><span data-stu-id="ad685-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="ad685-143">Farklı dağıtım türleri hakkında daha fazla bilgi için bkz: [.NET Core uygulama dağıtımı](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ad685-144">Uygulama için belirli bir çalışma zamanı yayımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="ad685-145">Bu oluşturulurken kullanılan bir [müstakil dağıtım (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="ad685-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="ad685-146">Çalışma zamanı tanımlayıcıları (RID) bir listesi için bkz: [RID katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ad685-147">Varsayılan değer yayımlamak için bir [framework bağımlı dağıtım (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="ad685-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ad685-148">Komutun ayrıntı düzeyi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad685-149">İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad685-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="ad685-150">Yıldız işareti değiştirmek için Sürüm soneki tanımlar (`*`) proje dosyasının sürüm alanında.</span><span class="sxs-lookup"><span data-stu-id="ad685-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ad685-151">.NET core 1.x</span><span class="sxs-lookup"><span data-stu-id="ad685-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="ad685-152">Derleme yapılandırması tanımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-152">Defines the build configuration.</span></span> <span data-ttu-id="ad685-153">Varsayılan değer `Debug` şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="ad685-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="ad685-154">Uygulama için belirtilen yayımlar [hedef framework](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="ad685-155">Proje dosyasında hedef Framework'ü belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad685-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="ad685-156">Komutu için kısa bir Yardım yazdırır.</span><span class="sxs-lookup"><span data-stu-id="ad685-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="ad685-157">Bir veya birkaç belirtir [hedef bildirimleri](../deploying/runtime-store.md) uygulamayla yayımlanan paket kümesini kırpma için kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="ad685-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="ad685-158">Bildirim dosyası çıkışını bir parçasıdır [ `dotnet store` komutu](dotnet-store.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="ad685-159">Birden çok bildirimleri belirtmek için ekleyin bir `--manifest` her bildirimi için seçeneği.</span><span class="sxs-lookup"><span data-stu-id="ad685-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="ad685-160">Bu seçenek, .NET Core 2.0 SDK'sı ile başlayarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ad685-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ad685-161">Çıktı dizini yolunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="ad685-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="ad685-162">Belirtilmezse, varsayılan olarak *./bin/[configuration]/[framework]/* framework bağımlı dağıtım için veya *./bin/[configuration]/[framework]/[runtime]* kendi içinde bulunan bir dağıtım için.</span><span class="sxs-lookup"><span data-stu-id="ad685-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="ad685-163">Göreli bir yol sağlanırsa, oluşturulan çıktı dizini proje dosya konumu, geçerli çalışma dizini için görelidir.</span><span class="sxs-lookup"><span data-stu-id="ad685-163">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="ad685-164">Uygulama için belirli bir çalışma zamanı yayımlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="ad685-165">Bu oluşturulurken kullanılan bir [müstakil dağıtım (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="ad685-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="ad685-166">Çalışma zamanı tanımlayıcıları (RID) bir listesi için bkz: [RID katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="ad685-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="ad685-167">Varsayılan değer yayımlamak için bir [framework bağımlı dağıtım (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span><span class="sxs-lookup"><span data-stu-id="ad685-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="ad685-168">Komutun ayrıntı düzeyi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="ad685-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ad685-169">İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="ad685-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="ad685-170">Yıldız işareti değiştirmek için Sürüm soneki tanımlar (`*`) proje dosyasının sürüm alanında.</span><span class="sxs-lookup"><span data-stu-id="ad685-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ad685-171">Örnekler</span><span class="sxs-lookup"><span data-stu-id="ad685-171">Examples</span></span>

<span data-ttu-id="ad685-172">Proje geçerli dizinde yayımlayın:</span><span class="sxs-lookup"><span data-stu-id="ad685-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="ad685-173">Belirtilen proje dosyası kullanarak uygulama yayımlama:</span><span class="sxs-lookup"><span data-stu-id="ad685-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="ad685-174">Geçerli bir dizin içinde proje yayımlama `netcoreapp1.1` framework:</span><span class="sxs-lookup"><span data-stu-id="ad685-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="ad685-175">Geçerli kullanarak uygulamayı yayımlamak `netcoreapp1.1` framework ve Çalışma Zamanı Modülü `OS X 10.10` (proje dosyasında bu RID listelemeniz gerekir).</span><span class="sxs-lookup"><span data-stu-id="ad685-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="ad685-176">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="ad685-176">See also</span></span>

* [<span data-ttu-id="ad685-177">Hedef Çerçeve</span><span class="sxs-lookup"><span data-stu-id="ad685-177">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="ad685-178">Çalışma zamanı tanımlayıcı (RID) Kataloğu</span><span class="sxs-lookup"><span data-stu-id="ad685-178">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)