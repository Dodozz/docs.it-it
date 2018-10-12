---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 396c4ddf09854fa4582226bdb1422f8c929e459b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208633"
---
# <a name="dotnet-new"></a><span data-ttu-id="fbfdc-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fbfdc-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fbfdc-104">nome</span><span class="sxs-lookup"><span data-stu-id="fbfdc-104">Name</span></span>

<span data-ttu-id="fbfdc-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fbfdc-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="fbfdc-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fbfdc-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fbfdc-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fbfdc-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fbfdc-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fbfdc-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fbfdc-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="fbfdc-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbfdc-110">Description</span></span>

<span data-ttu-id="fbfdc-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="fbfdc-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="fbfdc-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fbfdc-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="fbfdc-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="fbfdc-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="fbfdc-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fbfdc-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fbfdc-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="fbfdc-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-118">The command contains a default list of templates.</span></span> <span data-ttu-id="fbfdc-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="fbfdc-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="fbfdc-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="fbfdc-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-122">Template description</span></span>                          | <span data-ttu-id="fbfdc-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-123">Template name</span></span>   | <span data-ttu-id="fbfdc-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="fbfdc-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="fbfdc-125">Console application</span></span>                          | `console`       | <span data-ttu-id="fbfdc-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="fbfdc-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="fbfdc-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="fbfdc-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-133">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="fbfdc-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="fbfdc-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-134">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="fbfdc-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="fbfdc-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-136">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="fbfdc-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="fbfdc-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-138">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-139">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="fbfdc-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="fbfdc-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-140">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-141">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="fbfdc-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="fbfdc-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-142">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="fbfdc-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-144">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="fbfdc-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="fbfdc-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-146">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="fbfdc-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="fbfdc-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-148">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-149">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="fbfdc-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="fbfdc-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-150">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-151">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="fbfdc-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-152">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-153">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="fbfdc-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="fbfdc-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-154">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-155">File global.json</span><span class="sxs-lookup"><span data-stu-id="fbfdc-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="fbfdc-156">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="fbfdc-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="fbfdc-157">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="fbfdc-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="fbfdc-158">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="fbfdc-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fbfdc-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fbfdc-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="fbfdc-160">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-160">The command contains a default list of templates.</span></span> <span data-ttu-id="fbfdc-161">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="fbfdc-162">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="fbfdc-163">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="fbfdc-164">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-164">Template description</span></span>                          | <span data-ttu-id="fbfdc-165">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-165">Template name</span></span> | <span data-ttu-id="fbfdc-166">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="fbfdc-167">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="fbfdc-167">Console application</span></span>                          | `console`     | <span data-ttu-id="fbfdc-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-169">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="fbfdc-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-171">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="fbfdc-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-173">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="fbfdc-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fbfdc-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="fbfdc-175">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="fbfdc-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="fbfdc-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-176">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-177">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="fbfdc-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="fbfdc-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-178">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-179">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="fbfdc-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-180">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="fbfdc-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="fbfdc-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-182">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="fbfdc-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="fbfdc-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-184">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-185">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="fbfdc-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="fbfdc-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-186">[C#]</span></span>          |
| <span data-ttu-id="fbfdc-187">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="fbfdc-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-188">[C#], F#</span></span>      |
| <span data-ttu-id="fbfdc-189">File global.json</span><span class="sxs-lookup"><span data-stu-id="fbfdc-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="fbfdc-190">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="fbfdc-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="fbfdc-191">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="fbfdc-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="fbfdc-192">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="fbfdc-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="fbfdc-193">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="fbfdc-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="fbfdc-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="fbfdc-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="fbfdc-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="fbfdc-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fbfdc-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fbfdc-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="fbfdc-197">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-197">The command contains a default list of templates.</span></span> <span data-ttu-id="fbfdc-198">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="fbfdc-199">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="fbfdc-200">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="fbfdc-201">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-201">Template description</span></span>  | <span data-ttu-id="fbfdc-202">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-202">Template name</span></span> | <span data-ttu-id="fbfdc-203">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="fbfdc-204">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="fbfdc-204">Console application</span></span>  | `console`     | <span data-ttu-id="fbfdc-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-205">[C#], F#</span></span>  |
| <span data-ttu-id="fbfdc-206">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="fbfdc-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-207">[C#], F#</span></span>  |
| <span data-ttu-id="fbfdc-208">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="fbfdc-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-209">[C#], F#</span></span>  |
| <span data-ttu-id="fbfdc-210">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="fbfdc-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="fbfdc-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-211">[C#], F#</span></span>  |
| <span data-ttu-id="fbfdc-212">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="fbfdc-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="fbfdc-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-213">[C#]</span></span>      |
| <span data-ttu-id="fbfdc-214">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="fbfdc-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fbfdc-215">[C#], F#</span></span>  |
| <span data-ttu-id="fbfdc-216">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fbfdc-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="fbfdc-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="fbfdc-217">[C#]</span></span>      |
| <span data-ttu-id="fbfdc-218">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="fbfdc-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="fbfdc-219">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="fbfdc-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="fbfdc-220">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="fbfdc-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="fbfdc-221">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fbfdc-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fbfdc-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fbfdc-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="fbfdc-223">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="fbfdc-224">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="fbfdc-225">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-225">Prints out help for the command.</span></span> <span data-ttu-id="fbfdc-226">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="fbfdc-227">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fbfdc-228">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="fbfdc-229">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="fbfdc-230">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="fbfdc-231">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="fbfdc-232">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="fbfdc-233">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="fbfdc-234">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="fbfdc-235">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-235">The language of the template to create.</span></span> <span data-ttu-id="fbfdc-236">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="fbfdc-237">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="fbfdc-238">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="fbfdc-239">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="fbfdc-240">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-240">The name for the created output.</span></span> <span data-ttu-id="fbfdc-241">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="fbfdc-242">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="fbfdc-243">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-243">Location to place the generated output.</span></span> <span data-ttu-id="fbfdc-244">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="fbfdc-245">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-245">Filters templates based on available types.</span></span> <span data-ttu-id="fbfdc-246">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="fbfdc-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="fbfdc-247">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="fbfdc-248">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="fbfdc-249">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="fbfdc-250">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fbfdc-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fbfdc-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="fbfdc-252">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="fbfdc-253">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="fbfdc-254">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-254">Prints out help for the command.</span></span> <span data-ttu-id="fbfdc-255">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="fbfdc-256">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fbfdc-257">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="fbfdc-258">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="fbfdc-259">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="fbfdc-260">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="fbfdc-261">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="fbfdc-262">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="fbfdc-263">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="fbfdc-264">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-264">The language of the template to create.</span></span> <span data-ttu-id="fbfdc-265">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="fbfdc-266">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="fbfdc-267">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="fbfdc-268">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="fbfdc-269">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-269">The name for the created output.</span></span> <span data-ttu-id="fbfdc-270">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="fbfdc-271">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-271">Location to place the generated output.</span></span> <span data-ttu-id="fbfdc-272">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="fbfdc-273">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-273">Filters templates based on available types.</span></span> <span data-ttu-id="fbfdc-274">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="fbfdc-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="fbfdc-275">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="fbfdc-276">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-276">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="fbfdc-277">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="fbfdc-278">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="fbfdc-279">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-279">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fbfdc-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fbfdc-280">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="fbfdc-281">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-281">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="fbfdc-282">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-282">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="fbfdc-283">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-283">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="fbfdc-284">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-284">Prints out help for the command.</span></span> <span data-ttu-id="fbfdc-285">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-285">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="fbfdc-286">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-286">Lists templates containing the specified name.</span></span> <span data-ttu-id="fbfdc-287">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-287">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="fbfdc-288">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-288">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="fbfdc-289">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-289">The language of the template to create.</span></span> <span data-ttu-id="fbfdc-290">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-290">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="fbfdc-291">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-291">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="fbfdc-292">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-292">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="fbfdc-293">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-293">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="fbfdc-294">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-294">The name for the created output.</span></span> <span data-ttu-id="fbfdc-295">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-295">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="fbfdc-296">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-296">Location to place the generated output.</span></span> <span data-ttu-id="fbfdc-297">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-297">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="fbfdc-298">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="fbfdc-298">Template options</span></span>

<span data-ttu-id="fbfdc-299">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-299">Each project template may have additional options available.</span></span> <span data-ttu-id="fbfdc-300">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-300">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="fbfdc-301">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="fbfdc-301">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="fbfdc-302">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-302">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="fbfdc-303">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-303">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-304">**classlib**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-304">**classlib**</span></span>

<span data-ttu-id="fbfdc-305">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-305">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fbfdc-306">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-306">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="fbfdc-307">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-307">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="fbfdc-308">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-308">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-309">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-309">**mstest, xunit**</span></span>

<span data-ttu-id="fbfdc-310">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-310">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="fbfdc-311">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-312">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-312">**globaljson**</span></span>

<span data-ttu-id="fbfdc-313">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-313">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="fbfdc-314">**web**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-314">**web**</span></span>

<span data-ttu-id="fbfdc-315">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-315">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="fbfdc-316">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-316">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-317">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-317">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="fbfdc-318">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-318">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="fbfdc-319">**webapi**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-319">**webapi**</span></span>

<span data-ttu-id="fbfdc-320">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-320">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="fbfdc-321">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-321">The possible values are:</span></span>

- <span data-ttu-id="fbfdc-322">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-322">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="fbfdc-323">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-323">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="fbfdc-324">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-324">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="fbfdc-325">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-325">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="fbfdc-326">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-326">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fbfdc-327">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-327">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-328">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-328">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="fbfdc-329">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-329">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fbfdc-330">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-330">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-331">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-331">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fbfdc-332">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-333">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-333">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="fbfdc-334">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-334">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="fbfdc-335">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-335">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-336">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-336">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="fbfdc-337">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-337">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="fbfdc-338">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-338">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-339">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-339">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="fbfdc-340">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-340">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fbfdc-341">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-341">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-342">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-342">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="fbfdc-343">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-343">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="fbfdc-344">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-344">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="fbfdc-345">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-345">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="fbfdc-346">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-346">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fbfdc-347">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-347">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-348">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-348">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-349">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-349">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="fbfdc-350">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-350">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="fbfdc-351">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-351">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="fbfdc-352">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-352">**mvc, razor**</span></span>

<span data-ttu-id="fbfdc-353">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-353">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="fbfdc-354">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-354">The possible values are:</span></span>

- <span data-ttu-id="fbfdc-355">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-355">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="fbfdc-356">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-356">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="fbfdc-357">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-357">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="fbfdc-358">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-358">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="fbfdc-359">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-359">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="fbfdc-360">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-360">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="fbfdc-361">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-361">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fbfdc-362">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-362">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-363">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-363">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="fbfdc-364">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-364">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fbfdc-365">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-365">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-366">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-366">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="fbfdc-367">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-367">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-368">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-368">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="fbfdc-369">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-369">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-370">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-370">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fbfdc-371">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-371">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fbfdc-372">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-372">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="fbfdc-373">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-373">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="fbfdc-374">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-374">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fbfdc-375">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-375">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="fbfdc-376">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-376">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="fbfdc-377">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-378">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-378">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="fbfdc-379">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-379">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fbfdc-380">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-380">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-381">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-381">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="fbfdc-382">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-382">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fbfdc-383">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-383">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-384">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-384">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="fbfdc-385">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-385">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="fbfdc-386">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-386">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="fbfdc-387">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-387">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="fbfdc-388">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-388">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="fbfdc-389">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-389">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fbfdc-390">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-390">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-391">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-391">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-392">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-392">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="fbfdc-393">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-393">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="fbfdc-394">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-394">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="fbfdc-395">**page**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-395">**page**</span></span>

<span data-ttu-id="fbfdc-396">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-396">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="fbfdc-397">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-397">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="fbfdc-398">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-398">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="fbfdc-399">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-399">**viewimports**</span></span>

<span data-ttu-id="fbfdc-400">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-400">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="fbfdc-401">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-401">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="fbfdc-402">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="fbfdc-402">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="fbfdc-403">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-403">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="fbfdc-404">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-404">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-405">**classlib**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-405">**classlib**</span></span>

<span data-ttu-id="fbfdc-406">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-406">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fbfdc-407">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-407">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="fbfdc-408">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-408">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="fbfdc-409">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-409">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-410">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-410">**mstest, xunit**</span></span>

<span data-ttu-id="fbfdc-411">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-411">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="fbfdc-412">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-413">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-413">**globaljson**</span></span>

<span data-ttu-id="fbfdc-414">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-414">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="fbfdc-415">**web**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-415">**web**</span></span>

<span data-ttu-id="fbfdc-416">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-416">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="fbfdc-417">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-417">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-418">**webapi**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-418">**webapi**</span></span>

<span data-ttu-id="fbfdc-419">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-419">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="fbfdc-420">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-420">The possible values are:</span></span>

- <span data-ttu-id="fbfdc-421">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-421">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="fbfdc-422">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-422">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="fbfdc-423">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-423">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="fbfdc-424">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-424">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="fbfdc-425">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-425">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fbfdc-426">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-426">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-427">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-427">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="fbfdc-428">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-428">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fbfdc-429">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-429">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-430">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-430">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fbfdc-431">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-432">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-432">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="fbfdc-433">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-433">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="fbfdc-434">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-434">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-435">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-435">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="fbfdc-436">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-436">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="fbfdc-437">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-437">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-438">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-438">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="fbfdc-439">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-439">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fbfdc-440">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-441">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-441">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="fbfdc-442">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-442">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="fbfdc-443">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-443">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="fbfdc-444">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-444">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="fbfdc-445">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-445">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fbfdc-446">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-446">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-447">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-447">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-448">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-448">**mvc, razor**</span></span>

<span data-ttu-id="fbfdc-449">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-449">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="fbfdc-450">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-450">The possible values are:</span></span>

- <span data-ttu-id="fbfdc-451">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="fbfdc-451">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="fbfdc-452">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-452">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="fbfdc-453">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-453">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="fbfdc-454">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-454">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="fbfdc-455">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-455">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="fbfdc-456">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-456">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="fbfdc-457">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-457">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fbfdc-458">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-458">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-459">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-459">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="fbfdc-460">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-460">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fbfdc-461">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-461">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-462">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-462">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="fbfdc-463">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-463">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-464">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-464">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="fbfdc-465">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-465">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-466">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-466">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fbfdc-467">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-467">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fbfdc-468">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-468">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="fbfdc-469">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-469">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="fbfdc-470">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-470">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fbfdc-471">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-471">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="fbfdc-472">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-472">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="fbfdc-473">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-473">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-474">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-474">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="fbfdc-475">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-475">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fbfdc-476">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-476">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fbfdc-477">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-477">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="fbfdc-478">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-478">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fbfdc-479">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fbfdc-480">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-480">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="fbfdc-481">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-481">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="fbfdc-482">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-482">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="fbfdc-483">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-483">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="fbfdc-484">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-484">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="fbfdc-485">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-485">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fbfdc-486">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-486">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="fbfdc-487">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-487">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fbfdc-488">**page**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-488">**page**</span></span>

<span data-ttu-id="fbfdc-489">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-489">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="fbfdc-490">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-490">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="fbfdc-491">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-491">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="fbfdc-492">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-492">**viewimports**</span></span>

<span data-ttu-id="fbfdc-493">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-493">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="fbfdc-494">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-494">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fbfdc-495">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fbfdc-495">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="fbfdc-496">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-496">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="fbfdc-497">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-497">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fbfdc-498">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-498">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="fbfdc-499">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-499">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="fbfdc-500">**classlib**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-500">**classlib**</span></span>

<span data-ttu-id="fbfdc-501">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-501">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fbfdc-502">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-502">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="fbfdc-503">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-503">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="fbfdc-504">**mvc**</span><span class="sxs-lookup"><span data-stu-id="fbfdc-504">**mvc**</span></span>

<span data-ttu-id="fbfdc-505">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-505">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fbfdc-506">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-506">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="fbfdc-507">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-507">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="fbfdc-508">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-508">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="fbfdc-509">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-509">Values: `None` or `Individual`.</span></span> <span data-ttu-id="fbfdc-510">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-510">The default value is `None`.</span></span>

<span data-ttu-id="fbfdc-511">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-511">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="fbfdc-512">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-512">Values: `true` or `false`.</span></span> <span data-ttu-id="fbfdc-513">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="fbfdc-513">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="fbfdc-514">Esempi</span><span class="sxs-lookup"><span data-stu-id="fbfdc-514">Examples</span></span>

<span data-ttu-id="fbfdc-515">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-515">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="fbfdc-516">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-516">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="fbfdc-517">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-517">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="fbfdc-518">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-518">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="fbfdc-519">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="fbfdc-519">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="fbfdc-520">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="fbfdc-520">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="fbfdc-521">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="fbfdc-521">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="fbfdc-522">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbfdc-522">See also</span></span>

* [<span data-ttu-id="fbfdc-523">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="fbfdc-523">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="fbfdc-524">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="fbfdc-524">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="fbfdc-525">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="fbfdc-525">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="fbfdc-526">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="fbfdc-526">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
