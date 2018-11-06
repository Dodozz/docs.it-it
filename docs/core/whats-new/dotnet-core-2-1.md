---
title: Novità di .NET Core 2.1
description: Informazioni sulle nuove funzionalità in .NET Core 2.1.
dev_langs:
- csharp
- vb
author: rpetrusha
ms.author: ronpet
ms.date: 10/10/2018
ms.openlocfilehash: bf14e21ec4d390d8ab753bfa45533442ff4f6e68
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49120947"
---
# <a name="whats-new-in-net-core-21"></a><span data-ttu-id="22a54-103">Novità di .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="22a54-103">What's new in .NET Core 2.1</span></span>

<span data-ttu-id="22a54-104">.NET Core 2.1 include miglioramenti e nuove funzionalità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a54-104">.NET Core 2.1 includes enhancements and new features in the following areas:</span></span>

- [<span data-ttu-id="22a54-105">Strumenti</span><span class="sxs-lookup"><span data-stu-id="22a54-105">Tooling</span></span>](#tooling)
- [<span data-ttu-id="22a54-106">Roll forward</span><span class="sxs-lookup"><span data-stu-id="22a54-106">Roll forward</span></span>](#roll-forward)
- [<span data-ttu-id="22a54-107">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="22a54-107">Deployment</span></span>](#deployment)
- [<span data-ttu-id="22a54-108">Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="22a54-108">Windows Compatibility Pack</span></span>](#windows-compatibility-pack)
- [<span data-ttu-id="22a54-109">Miglioramenti della compilazione JIT</span><span class="sxs-lookup"><span data-stu-id="22a54-109">JIT compilation improvements</span></span>](#jit-compiler-improvements)
- [<span data-ttu-id="22a54-110">Modifiche dell'API</span><span class="sxs-lookup"><span data-stu-id="22a54-110">API changes</span></span>](#api-changes)

## <a name="tooling"></a><span data-ttu-id="22a54-111">Strumenti</span><span class="sxs-lookup"><span data-stu-id="22a54-111">Tooling</span></span>

<span data-ttu-id="22a54-112">.NET Core 2.1 SDK (v 2.1.300), ovvero il set di strumenti incluso in .NET Core 2.1, include le modifiche e i miglioramenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a54-112">The .NET Core 2.1 SDK (v 2.1.300), the tooling included with .NET Core 2.1, includes the following changes and enhancements:</span></span>

### <a name="build-performance-improvements"></a><span data-ttu-id="22a54-113">Miglioramenti delle prestazioni di compilazione</span><span class="sxs-lookup"><span data-stu-id="22a54-113">Build performance improvements</span></span>

<span data-ttu-id="22a54-114">Un obiettivo fondamentale di .NET Core 2.1 è il miglioramento delle prestazioni in fase di compilazione, in particolare per le compilazioni incrementali.</span><span class="sxs-lookup"><span data-stu-id="22a54-114">A major focus of .NET Core 2.1 is improving build-time performance, particularly for incremental builds.</span></span> <span data-ttu-id="22a54-115">Questi miglioramenti delle prestazioni si applicano sia alle compilazioni dalla riga di comando con `dotnet build` che alle compilazioni in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="22a54-115">These performance improvements apply to both command-line builds using `dotnet build` and to builds in Visual Studio.</span></span> <span data-ttu-id="22a54-116">Alcune aree specifiche di miglioramento includono:</span><span class="sxs-lookup"><span data-stu-id="22a54-116">Some individual areas of improvement include:</span></span>

- <span data-ttu-id="22a54-117">Per la risoluzione degli asset dei pacchetti, risoluzione solo degli asset usati da una compilazione anziché di tutti gli asset.</span><span class="sxs-lookup"><span data-stu-id="22a54-117">For package asset resolution, resolving only assets used by a build rather than all assets.</span></span>

- <span data-ttu-id="22a54-118">Memorizzazione nella cache dei riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="22a54-118">Caching of assembly references.</span></span>

- <span data-ttu-id="22a54-119">Uso dei server di compilazione SDK a esecuzione prolungata, ovvero processi che si estendono attraverso singole chiamate a `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="22a54-119">Use of long-running SDK build servers, which are processes that span across individual `dotnet build` invocations.</span></span> <span data-ttu-id="22a54-120">Eliminano la necessità di compilare tramite JIT blocchi di codice di grandi dimensioni ogni volta che viene eseguito `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="22a54-120">They eliminate the need to JIT-compile large blocks of code every time `dotnet build` is run.</span></span> <span data-ttu-id="22a54-121">I processi del server di compilazione possono essere terminati automaticamente con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="22a54-121">Build server processes can be automatically terminated with the following command:</span></span>

   ```console
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a><span data-ttu-id="22a54-122">Nuovi comandi dell'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="22a54-122">New CLI commands</span></span>

<span data-ttu-id="22a54-123">Numerosi strumenti precedentemente disponibili solo a livello di singolo progetto usando [`DotnetCliToolReference`](../tools/extensibility.md) sono ora disponibili come parte di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="22a54-123">A number of tools that were available only on a per project basis using [`DotnetCliToolReference`](../tools/extensibility.md) are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="22a54-124">Questi strumenti comprendono:</span><span class="sxs-lookup"><span data-stu-id="22a54-124">These tools include:</span></span>

- <span data-ttu-id="22a54-125">`dotnet watch` fornisce un watcher del file system che rimane in attesa delle modifiche a un file prima di eseguire un determinato set di comandi.</span><span class="sxs-lookup"><span data-stu-id="22a54-125">`dotnet watch` provides a file system watcher that waits for a file to change before executing a designated set of commands.</span></span> <span data-ttu-id="22a54-126">Ad esempio, il comando seguente ricompila automaticamente il progetto corrente e genera un output dettagliato ogni volta che viene modificato un file in esso contenuto:</span><span class="sxs-lookup"><span data-stu-id="22a54-126">For example, the following command automatically rebuilds the current project and generates verbose output whenever a file in it changes:</span></span>

   ```console
   dotnet watch -- --verbose build
   ```

   <span data-ttu-id="22a54-127">Si noti l'opzione `--` che precede l'opzione `--verbose`.</span><span class="sxs-lookup"><span data-stu-id="22a54-127">Note the `--` option that precedes the `--verbose` option.</span></span> <span data-ttu-id="22a54-128">Delimita le opzioni passate direttamente al comando `dotnet watch` dagli argomenti passati al processo figlio `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="22a54-128">It delimits the options passed directly to the `dotnet watch` command from the arguments that are passed to the child `dotnet` process.</span></span> <span data-ttu-id="22a54-129">Senza di essa, l'opzione `--verbose` si applica al comando `dotnet watch` e non al comando `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="22a54-129">Without it, the `--verbose` option applies to the `dotnet watch` command, not the `dotnet build` command.</span></span>
  
   <span data-ttu-id="22a54-130">Per altre informazioni, vedere [Sviluppare app ASP.NET Core con dotnet watch](/aspnet/core/tutorials/dotnet-watch).</span><span class="sxs-lookup"><span data-stu-id="22a54-130">For more information, see [Develop ASP.NET Core apps using dotnet watch](/aspnet/core/tutorials/dotnet-watch)</span></span>

- <span data-ttu-id="22a54-131">`dotnet dev-certs` genera e gestisce i certificati usati durante lo sviluppo nelle applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-131">`dotnet dev-certs` generates and manages certificates used during development in ASP.NET Core applications.</span></span>

- <span data-ttu-id="22a54-132">`dotnet user-secrets` gestisce i segreti in un archivio di segreti dell'utente nelle applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-132">`dotnet user-secrets` manages the secrets in a user secret store in ASP.NET Core applications.</span></span>

- <span data-ttu-id="22a54-133">`dotnet sql-cache` crea una tabella e gli indici in un database di Microsoft SQL Server da usare per la memorizzazione nella cache distribuita.</span><span class="sxs-lookup"><span data-stu-id="22a54-133">`dotnet sql-cache` creates a table and indexes in a Microsoft SQL Server database to be used for distributed caching.</span></span>

- <span data-ttu-id="22a54-134">`dotnet ef` è uno strumento per la gestione di database, oggetti <xref:Microsoft.EntityFrameworkCore.DbContext> e migrazioni in applicazioni Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-134">`dotnet ef` is a tool for managing databases, <xref:Microsoft.EntityFrameworkCore.DbContext> objects, and migrations in Entity Framework Core applications.</span></span> <span data-ttu-id="22a54-135">Per altre informazioni, vedere [Strumenti da riga di comando di EF Core .NET](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="22a54-135">For more information, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

### <a name="global-tools"></a><span data-ttu-id="22a54-136">Strumenti globali</span><span class="sxs-lookup"><span data-stu-id="22a54-136">Global Tools</span></span>

<span data-ttu-id="22a54-137">.NET Core 2.1 supporta gli *strumenti globali*, vale a dire strumenti personalizzati disponibili globalmente dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="22a54-137">.NET Core 2.1 supports *Global Tools* -- that is, custom tools that are available globally from the command line.</span></span> <span data-ttu-id="22a54-138">Il modello di estendibilità nelle versioni precedenti di .NET Core rendeva disponibili gli strumenti personalizzati a livello di singolo progetto solo usando [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).</span><span class="sxs-lookup"><span data-stu-id="22a54-138">The extensibility model in previous versions of .NET Core made custom tools available on a per project basis only by using [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).</span></span>

<span data-ttu-id="22a54-139">Per installare uno strumento globale, usare il comando [dotnet tool install](../tools/dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="22a54-139">To install a Global Tool, you use the [dotnet tool install](../tools/dotnet-tool-install.md) command.</span></span> <span data-ttu-id="22a54-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="22a54-140">For example:</span></span>

```console
dotnet tool install -g dotnetsay
```

<span data-ttu-id="22a54-141">Dopo l'installazione, lo strumento può essere eseguito dalla riga di comando specificando il nome dello strumento.</span><span class="sxs-lookup"><span data-stu-id="22a54-141">Once installed, the tool can be run from the command line by specifying the tool name.</span></span> <span data-ttu-id="22a54-142">Per altre informazioni, vedere [Panoramica degli strumenti globali .NET Core](../tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22a54-142">For more information, see [.NET Core Global Tools overview](../tools/global-tools.md).</span></span>

### <a name="tool-management-with-the-dotnet-tool-command"></a><span data-ttu-id="22a54-143">Strumento di gestione con il comando `dotnet tool`</span><span class="sxs-lookup"><span data-stu-id="22a54-143">Tool management with the `dotnet tool` command</span></span>

<span data-ttu-id="22a54-144">In .NET Core SDK 2.1 (v 2.1.300), tutte le operazioni con gli strumenti usano il comando `dotnet tool`.</span><span class="sxs-lookup"><span data-stu-id="22a54-144">In .NET Core SDK 2.1 (v 2.1.300), all tools operations use the `dotnet tool` command.</span></span> <span data-ttu-id="22a54-145">Sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="22a54-145">The following options are available:</span></span>

- <span data-ttu-id="22a54-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) per installare uno strumento.</span><span class="sxs-lookup"><span data-stu-id="22a54-146">[`dotnet tool install`](../tools/dotnet-tool-install.md) to install a tool.</span></span>

- <span data-ttu-id="22a54-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) per disinstallare e reinstallare uno strumento, aggiornandolo in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="22a54-147">[`dotnet tool update`](../tools/dotnet-tool-update.md) to uninstall and reinstall a tool, which effectively updates it.</span></span>

- <span data-ttu-id="22a54-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) per elencare gli strumenti attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="22a54-148">[`dotnet tool list`](../tools/dotnet-tool-list.md) to list currently installed tools.</span></span>

- <span data-ttu-id="22a54-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) per disinstallare gli strumenti attualmente installati.</span><span class="sxs-lookup"><span data-stu-id="22a54-149">[`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) to uninstall currently installed tools.</span></span>

## <a name="roll-forward"></a><span data-ttu-id="22a54-150">Roll forward</span><span class="sxs-lookup"><span data-stu-id="22a54-150">Roll forward</span></span>

<span data-ttu-id="22a54-151">Di tutte le applicazioni .NET Core a partire da .NET Core 2.0 viene eseguito automaticamente il roll forward alla *versione secondaria* più recente installata in un sistema.</span><span class="sxs-lookup"><span data-stu-id="22a54-151">All .NET Core applications starting with the .NET Core 2.0 automatically roll forward to the latest *minor version* installed on a system.</span></span>

<span data-ttu-id="22a54-152">A partire da .NET Core 2.0, se la versione di .NET Core con cui è stata compilata un'applicazione non è presente in fase di esecuzione, l'applicazione verrà eseguita automaticamente con la *versione secondaria* installata più recente di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-152">Starting with .NET Core 2.0, if the version of .NET Core that an application was built with is not present at runtime, the application automatically runs against the latest installed *minor version* of .NET Core.</span></span> <span data-ttu-id="22a54-153">In altre parole, se un'applicazione è compilata con .NET Core 2.0 e .NET Core 2.0 non è presente nel sistema host ma .NET Core 2.1 lo è, l'applicazione verrà eseguita con .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="22a54-153">In other words, if an application is built with .NET Core 2.0, and .NET Core 2.0 is not present on the host system but .NET Core 2.1 is, the application runs with .NET Core 2.1.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22a54-154">Questo comportamento di roll forward non si applica alle versioni di anteprima,</span><span class="sxs-lookup"><span data-stu-id="22a54-154">This roll-forward behavior doesn't apply to preview releases.</span></span> <span data-ttu-id="22a54-155">né alle versioni principali.</span><span class="sxs-lookup"><span data-stu-id="22a54-155">Nor does it apply to major releases.</span></span> <span data-ttu-id="22a54-156">Ad esempio, un'applicazione .NET Core 1.0 non esegue il roll forward a .NET Core 2.0 o a .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="22a54-156">For example, a .NET Core 1.0 application wouldn't roll forward to .NET Core 2.0 or .NET Core 2.1.</span></span>

<span data-ttu-id="22a54-157">È anche possibile disabilitare il roll forward alla versione secondaria in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a54-157">You can also disable minor version roll forward in any of three ways:</span></span>

- <span data-ttu-id="22a54-158">Impostare la variabile di ambiente `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` su 0.</span><span class="sxs-lookup"><span data-stu-id="22a54-158">Set the `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` environment variable to 0.</span></span>

- <span data-ttu-id="22a54-159">Aggiungere la riga seguente al file runtimeconfig.json:</span><span class="sxs-lookup"><span data-stu-id="22a54-159">Add the following line to the runtimeconfig.json file:</span></span>

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- <span data-ttu-id="22a54-160">Quando si usano gli [strumenti dell'interfaccia della riga di comando di .NET Core](../tools/index.md), includere l'opzione seguente con un comando di .NET Core, ad esempio `run`:</span><span class="sxs-lookup"><span data-stu-id="22a54-160">When using [.NET Core CLI tools](../tools/index.md), include the following option with a .NET Core command such as `run`:</span></span>

   ```console
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

## <a name="deployment"></a><span data-ttu-id="22a54-161">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="22a54-161">Deployment</span></span>

### <a name="self-contained-application-servicing"></a><span data-ttu-id="22a54-162">Manutenzione di un'applicazione autonoma</span><span class="sxs-lookup"><span data-stu-id="22a54-162">Self-contained application servicing</span></span>

<span data-ttu-id="22a54-163">`dotnet publish` pubblica ora applicazioni autonome con una versione runtime servita.</span><span class="sxs-lookup"><span data-stu-id="22a54-163">`dotnet publish` now publishes self-contained applications with a serviced runtime version.</span></span> <span data-ttu-id="22a54-164">Quando si pubblica un'applicazione autonoma con .NET Core 2.1 SDK (v 2.1.300), l'applicazione include l'ultima versione runtime servita conosciuta da tale SDK.</span><span class="sxs-lookup"><span data-stu-id="22a54-164">When you publish a self-contained application with the .NET Core 2.1 SDK (v 2.1.300), your application includes the latest serviced runtime version known by that SDK.</span></span> <span data-ttu-id="22a54-165">Quando si esegue l'aggiornamento all'SDK più recente, si pubblicherà con l'ultima versione runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-165">When you upgrade to the latest SDK, you’ll publish with the latest .NET Core runtime version.</span></span> <span data-ttu-id="22a54-166">Questo vale per i runtime di .NET Core 1.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="22a54-166">This applies for .NET Core 1.0 runtimes and later.</span></span>

<span data-ttu-id="22a54-167">La pubblicazione autonoma si basa sulle versioni runtime in NuGet.org. Non è necessario disporre del runtime servito nel computer.</span><span class="sxs-lookup"><span data-stu-id="22a54-167">Self-contained publishing relies on runtime versions on NuGet.org. You do not need to have the serviced runtime on your machine.</span></span>

<span data-ttu-id="22a54-168">Tramite .NET Core 2.0 SDK, le applicazioni autonome sono pubblicate con il runtime .NET Core 2.0.0, a meno che non venga specificata un'altra versione tramite la proprietà `RuntimeFrameworkVersion`.</span><span class="sxs-lookup"><span data-stu-id="22a54-168">Using the .NET Core 2.0 SDK, self-contained applications are published with the .NET Core 2.0.0 runtime unless a different version is specified via the `RuntimeFrameworkVersion` property.</span></span> <span data-ttu-id="22a54-169">Con questo nuovo comportamento, non sarà più necessario impostare questa proprietà per selezionare una versione runtime successiva per un'applicazione autonoma.</span><span class="sxs-lookup"><span data-stu-id="22a54-169">With this new behavior, you’ll no longer need to set this property to select a higher runtime version for a self-contained application.</span></span> <span data-ttu-id="22a54-170">L'approccio più semplice in futuro consiste nel pubblicare sempre con .NET Core 2.1 SDK (v 2.1.300).</span><span class="sxs-lookup"><span data-stu-id="22a54-170">The easiest approach going forward is to always publish with .NET Core 2.1 SDK (v 2.1.300).</span></span>

<span data-ttu-id="22a54-171">Per altre informazioni, vedere [Roll forward del runtime di distribuzione autonoma](../deploying/runtime-patch-selection.md).</span><span class="sxs-lookup"><span data-stu-id="22a54-171">For more information, see [Self-contained deploymnet runtime roll forward](../deploying/runtime-patch-selection.md).</span></span>
## <a name="windows-compatibility-pack"></a><span data-ttu-id="22a54-172">Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="22a54-172">Windows Compatibility Pack</span></span>

<span data-ttu-id="22a54-173">Quando si porta il codice esistente da .NET Framework a .NET Core, è possibile usare [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility),</span><span class="sxs-lookup"><span data-stu-id="22a54-173">When you port existing code from the .NET Framework to .NET Core, you can use the [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span> <span data-ttu-id="22a54-174">che garantisce l'accesso a 20.000 API in più rispetto a quelle disponibili in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-174">It provides access to 20,000 more APIs than are available in .NET Core.</span></span> <span data-ttu-id="22a54-175">Queste API includono tipi nello spazio dei nomi <xref:System.Drawing?displayProperty=nameWithType>, la classe <xref:System.Diagnostics.EventLog>, WMI, contatori delle prestazioni, servizi di Windows e tipi e membri del Registro di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="22a54-175">These APIs include types in the <xref:System.Drawing?displayProperty=nameWithType> namespace, the <xref:System.Diagnostics.EventLog> class, WMI, Performance Counters, Windows Services, and the Windows registry types and members.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="22a54-176">Miglioramenti del compilatore JIT</span><span class="sxs-lookup"><span data-stu-id="22a54-176">JIT compiler improvements</span></span>

<span data-ttu-id="22a54-177">.NET Core include una nuova tecnologia del compilatore JIT denominata *compilazione a livelli* (nota anche come *ottimizzazione adattiva*) che può migliorare significativamente le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="22a54-177">.NET Core incorporates a new JIT compiler technology called *tiered compilation* (also known as *adaptive optimization*) that can significantly improve performance.</span></span> <span data-ttu-id="22a54-178">La compilazione a livelli è un'impostazione che prevede il consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="22a54-178">Tiered compilation is an opt-in setting.</span></span>

<span data-ttu-id="22a54-179">Una delle attività importanti eseguite dal compilatore JIT è l'ottimizzazione dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="22a54-179">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="22a54-180">Per i percorsi del codice poco usati, tuttavia, il compilatore può richiedere più tempo per l'ottimizzazione del codice rispetto a quanto impiegato dal runtime per l'esecuzione del codice non ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="22a54-180">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends running unoptimized code.</span></span> <span data-ttu-id="22a54-181">La compilazione a livelli introduce due fasi nella compilazione JIT:</span><span class="sxs-lookup"><span data-stu-id="22a54-181">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="22a54-182">Un **primo livello**, che genera il codice il più rapidamente possibile.</span><span class="sxs-lookup"><span data-stu-id="22a54-182">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="22a54-183">Un **secondo livello**, che genera codice ottimizzato per i metodi che vengono eseguiti frequentemente.</span><span class="sxs-lookup"><span data-stu-id="22a54-183">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="22a54-184">Il secondo livello di compilazione viene eseguito in parallelo per prestazioni migliorate.</span><span class="sxs-lookup"><span data-stu-id="22a54-184">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="22a54-185">È possibile acconsentire esplicitamente alla compilazione a livelli in uno dei due modi seguenti.</span><span class="sxs-lookup"><span data-stu-id="22a54-185">You can opt into tiered compilation in either of two ways.</span></span>

- <span data-ttu-id="22a54-186">Per usare la compilazione a livelli in tutti i progetti che usano .NET Core 2.1 SDK, impostare la variabile di ambiente seguente:</span><span class="sxs-lookup"><span data-stu-id="22a54-186">To use tiered compilation in all projects that use the .NET Core 2.1 SDK, set the following environment variable:</span></span>

  ```console
  COMPlus_TieredCompilation="1"
  ```

- <span data-ttu-id="22a54-187">Per usare la compilazione a livelli in base al progetto, aggiungere la proprietà `<TieredCompilation>` alla sezione `<PropertyGroup>` del file di progetto MSBuild, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="22a54-187">To use tiered compilation on a per-project basis, add the `<TieredCompilation>` property to the `<PropertyGroup>` section of the MSBuild project file, as the following example shows:</span></span>

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a><span data-ttu-id="22a54-188">Modifiche API</span><span class="sxs-lookup"><span data-stu-id="22a54-188">API changes</span></span>

### <a name="spant-and-memoryt"></a><span data-ttu-id="22a54-189">`Span<T>` e `Memory<T>`</span><span class="sxs-lookup"><span data-stu-id="22a54-189">`Span<T>` and `Memory<T>`</span></span>

<span data-ttu-id="22a54-190">.NET Core 2.1 include alcuni nuovi tipi che rendono molto più efficiente l'uso di matrici e altri tipi di memoria.</span><span class="sxs-lookup"><span data-stu-id="22a54-190">.NET Core 2.1 includes some new types that make working with arrays and other types of memory much more efficient.</span></span> <span data-ttu-id="22a54-191">I nuovi tipi includono:</span><span class="sxs-lookup"><span data-stu-id="22a54-191">The new types include:</span></span>

- <span data-ttu-id="22a54-192"><xref:System.Span%601?displayProperty=nameWithType> e <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22a54-192"><xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="22a54-193"><xref:System.Memory%601?displayProperty=nameWithType> e <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22a54-193"><xref:System.Memory%601?displayProperty=nameWithType> and <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="22a54-194">Senza questi tipi, quando si passano elementi quali una parte di una matrice o una sezione di un buffer di memoria, è necessario creare una copia di una parte dei dati prima di passarli a un metodo.</span><span class="sxs-lookup"><span data-stu-id="22a54-194">Without these types, when passing such items as a portion of an array or a section of a memory buffer, you have to make a copy of some portion of the data before passing it to a method.</span></span> <span data-ttu-id="22a54-195">Questi tipi forniscono una visualizzazione virtuale dei dati che elimina la necessità di un'allocazione di memoria e di operazioni di copia aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="22a54-195">These types provide a virtual view of that data that eliminates the need for the additional memory allocation and copy operations.</span></span>

<span data-ttu-id="22a54-196">L'esempio seguente usa un'istanza <xref:System.Span%601> e un'istanza <xref:System.Memory%601> per fornire una visualizzazione virtuale di 10 elementi di una matrice.</span><span class="sxs-lookup"><span data-stu-id="22a54-196">The following example uses a <xref:System.Span%601> and <xref:System.Memory%601> instance to provide a virtual view of 10 elements of an array.</span></span>

[!CODE-csharp[Span\<T>](~/samples/core/whats-new/whats-new-in-21/cs/program.cs)]

[!CODE-vb[Memory\<T>](~/samples/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a><span data-ttu-id="22a54-197">Compressione Brotli</span><span class="sxs-lookup"><span data-stu-id="22a54-197">Brotli compression</span></span>

<span data-ttu-id="22a54-198">.NET Core 2.1 aggiunge il supporto per la compressione e la decompressione Brotli.</span><span class="sxs-lookup"><span data-stu-id="22a54-198">.NET Core 2.1 adds support for Brotli compression and decompression.</span></span> <span data-ttu-id="22a54-199">Brotli è un algoritmo di compressione generico senza perdita di dati definito in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) e supportato dalla maggior parte dei Web browser e dai principali server Web.</span><span class="sxs-lookup"><span data-stu-id="22a54-199">Brotli is a general-purpose lossless compression algorithm that is defined in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) and is supported by most web browsers and major web servers.</span></span> <span data-ttu-id="22a54-200">È possibile usare la classe <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> basata sul flusso o le classi <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> e <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> basate sull'intervallo a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="22a54-200">You can use the stream-based <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> class or the high-performance span-based <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> and <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> classes.</span></span> <span data-ttu-id="22a54-201">L'esempio seguente illustra la compressione con la classe <xref:System.IO.Compression.BrotliStream>:</span><span class="sxs-lookup"><span data-stu-id="22a54-201">The following example illustrates compression with the <xref:System.IO.Compression.BrotliStream> class:</span></span>

[!CODE-csharp[Brotli compression](~/samples/core/whats-new/whats-new-in-21/cs/brotli.cs#1)]

<span data-ttu-id="22a54-202">Il comportamento di <xref:System.IO.Compression.BrotliStream> è lo stesso di <xref:System.IO.Compression.DeflateStream> e <xref:System.IO.Compression.GZipStream>, che rende più facile convertire il codice che chiama queste API in <xref:System.IO.Compression.BrotliStream>.</span><span class="sxs-lookup"><span data-stu-id="22a54-202">The <xref:System.IO.Compression.BrotliStream> behavior is the same as <xref:System.IO.Compression.DeflateStream> and <xref:System.IO.Compression.GZipStream>, which makes it easy to convert code that calls these APIs to <xref:System.IO.Compression.BrotliStream>.</span></span>

### <a name="new-cryptography-apis-and-cryptography-improvements"></a><span data-ttu-id="22a54-203">Nuove API di crittografia e miglioramenti della crittografia</span><span class="sxs-lookup"><span data-stu-id="22a54-203">New cryptography APIs and cryptography improvements</span></span>

<span data-ttu-id="22a54-204">.NET Core 2.1 include numerosi miglioramenti alle API di crittografia:</span><span class="sxs-lookup"><span data-stu-id="22a54-204">.NET Core 2.1 includes numerous enhancements to the cryptography APIs:</span></span>

- <span data-ttu-id="22a54-205"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> è disponibile nel pacchetto System.Security.Cryptography.Pkcs.</span><span class="sxs-lookup"><span data-stu-id="22a54-205"><xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> is available in the System.Security.Cryptography.Pkcs package.</span></span> <span data-ttu-id="22a54-206">L'implementazione è la stessa della classe <xref:System.Security.Cryptography.Pkcs.SignedCms> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22a54-206">The implementation is the same as the <xref:System.Security.Cryptography.Pkcs.SignedCms> class in the .NET Framework.</span></span>

- <span data-ttu-id="22a54-207">I nuovi overload dei metodi <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> e <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> accettano un identificatore dell'algoritmo hash per consentire ai chiamanti di ottenere i valori di identificazione personale dei certificati usando algoritmi diversi da SHA-1.</span><span class="sxs-lookup"><span data-stu-id="22a54-207">New overloads of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> and <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> methods accept a hash algorithm identifier to enable callers to get certificate thumbprint values using algorithms other than SHA-1.</span></span>

- <span data-ttu-id="22a54-208">Le nuove API di crittografia basate su <xref:System.Span%601> sono disponibili per hashing, HMAC, generazione casuale di numeri crittografici, generazione di firma asimmetrica, elaborazione di firma asimmetrica e crittografia RSA.</span><span class="sxs-lookup"><span data-stu-id="22a54-208">New <xref:System.Span%601>-based cryptography APIs are available for hashing, HMAC, cryptographic random number generation, asymmetric signature generation, asymmetric signature processing, and RSA encryption.</span></span>

- <span data-ttu-id="22a54-209">Le prestazioni di <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> risultano migliorate del 15% circa con un'implementazione basata su <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="22a54-209">The performance of <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> has improved by about 15% by using a <xref:System.Span%601>-based implementation.</span></span>

- <span data-ttu-id="22a54-210">La nuova classe <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> include due nuovi metodi:</span><span class="sxs-lookup"><span data-stu-id="22a54-210">The new <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> class includes two new methods:</span></span>

  - <span data-ttu-id="22a54-211"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> richiede una quantità fissa di tempo per restituire uno tra due input della stessa lunghezza, pertanto è appropriato per l'uso nella verifica crittografica per evitare di contribuire alle informazioni side-channel sulla durata.</span><span class="sxs-lookup"><span data-stu-id="22a54-211"><xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> takes a fixed amount of time to return for any two inputs of the same length, which makes it suitable for use in cryptographic verification to avoid contributing to timing side-channel information.</span></span>

  - <span data-ttu-id="22a54-212"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> è una routine di cancellazione della memoria che non può essere ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="22a54-212"><xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> is a memory-clearing routine that cannot be optimized.</span></span>

- <span data-ttu-id="22a54-213">Il metodo statico <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> riempie un <xref:System.Span%601> con valori casuali.</span><span class="sxs-lookup"><span data-stu-id="22a54-213">The static <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> method fills a <xref:System.Span%601> with random values.</span></span>

- <span data-ttu-id="22a54-214"><xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> è ora supportato in Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="22a54-214">The <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> is now supported on Linux and maxOS.</span></span>

- <span data-ttu-id="22a54-215">Diffie-Hellman a curva ellittica (ECDH) è ora disponibile nella famiglia di classi <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22a54-215">Elliptic-Curve Diffie-Hellman (ECDH) is now available in the <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType> class family.</span></span> <span data-ttu-id="22a54-216">La superficie di attacco è uguale a quella di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22a54-216">The surface area is the same as in the .NET Framework.</span></span>

- <span data-ttu-id="22a54-217">L'istanza restituita da <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> può eseguire la crittografia o la decrittografia con OAEP usando un digest SHA-2, nonché generare o convalidare firme con RSA-PSS.</span><span class="sxs-lookup"><span data-stu-id="22a54-217">The instance returned by <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> can encrypt or decrypt with OAEP using a SHA-2 digest, as well as generate or validate signatures using RSA-PSS.</span></span>

### <a name="sockets-improvements"></a><span data-ttu-id="22a54-218">Miglioramenti del socket</span><span class="sxs-lookup"><span data-stu-id="22a54-218">Sockets improvements</span></span>

<span data-ttu-id="22a54-219">.NET Core include un nuovo tipo, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, e un tipo <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType> riscritto, che costituiscono la base delle API di rete di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="22a54-219">.NET Core includes a new type, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, and a rewritten <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, that form the basis of higher-level networking APIs.</span></span>  <span data-ttu-id="22a54-220"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, ad esempio, è la base dell'implementazione di <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="22a54-220"><xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, for example, is the basis of the <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="22a54-221">Nelle versioni precedenti di .NET Core le API di livello superiore si basavano su implementazioni di rete native.</span><span class="sxs-lookup"><span data-stu-id="22a54-221">In previous versions of .NET Core, higher-level APIs were based on native networking implementations.</span></span>

<span data-ttu-id="22a54-222">L'implementazione dei socket introdotta in .NET Core 2.1 comporta numerosi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="22a54-222">The sockets implementation introduced in .NET Core 2.1 has a number of advantages:</span></span>

- <span data-ttu-id="22a54-223">Miglioramento significativo delle prestazioni rispetto all'implementazione precedente.</span><span class="sxs-lookup"><span data-stu-id="22a54-223">A significant performance improvement when compared with the previous implementation.</span></span>

- <span data-ttu-id="22a54-224">Eliminazione delle dipendenze della piattaforma, con una conseguente semplificazione della distribuzione e della manutenzione.</span><span class="sxs-lookup"><span data-stu-id="22a54-224">Elimination of platform dependencies, which simplifies deployment and servicing.</span></span>

- <span data-ttu-id="22a54-225">Comportamento coerente in tutte le piattaforme .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22a54-225">Consistent behavior across all .NET Core platforms.</span></span>

<span data-ttu-id="22a54-226"><xref:System.Net.Http.SocketsHttpHandler> è l'implementazione predefinita in .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="22a54-226"><xref:System.Net.Http.SocketsHttpHandler> is the default implementation in .NET Core 2.1.</span></span> <span data-ttu-id="22a54-227">Tuttavia, è possibile configurare l'applicazione per usare la classe <xref:System.Net.Http.HttpClientHandler> precedente chiamando il metodo <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="22a54-227">However, you can configure your application to use the older <xref:System.Net.Http.HttpClientHandler> class by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

<span data-ttu-id="22a54-228">È anche possibile usare una variabile di ambiente per rifiutare esplicitamente l'uso di implementazioni dei socket basate su <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="22a54-228">You can also use an environment variable to opt out of using sockets implementations based on <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="22a54-229">A tale scopo, impostare `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` su `false` o su 0.</span><span class="sxs-lookup"><span data-stu-id="22a54-229">To do this, set the `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` to either `false` or 0.</span></span>

<span data-ttu-id="22a54-230">In Windows è anche possibile scegliere di usare <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, che si basa su un'implementazione nativa, o la classe <xref:System.Net.Http.SocketsHttpHandler> passando un'istanza della classe al costruttore <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="22a54-230">On Windows, you can also choose to use <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, which relies on a native implementation, or the <xref:System.Net.Http.SocketsHttpHandler> class by passing an instance of the class to the <xref:System.Net.Http.HttpClient> constructor.</span></span>

<span data-ttu-id="22a54-231">In Linux e macOS è possibile configurare <xref:System.Net.Http.HttpClient> solo in base al processo.</span><span class="sxs-lookup"><span data-stu-id="22a54-231">On Linux and macOS, you can only configure <xref:System.Net.Http.HttpClient> on a per-process basis.</span></span> <span data-ttu-id="22a54-232">In Linux è necessario distribuire [libcurl](https://curl.haxx.se/libcurl/) se si vuole usare l'implementazione precedente di <xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="22a54-232">On Linux, you need to deploy [libcurl](https://curl.haxx.se/libcurl/) if you want to use the old <xref:System.Net.Http.HttpClient> implementation.</span></span> <span data-ttu-id="22a54-233">(installato con .NET Core 2.0).</span><span class="sxs-lookup"><span data-stu-id="22a54-233">(It is installed with .NET Core 2.0.)</span></span>

## <a name="see-also"></a><span data-ttu-id="22a54-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a54-234">See also</span></span>

* <span data-ttu-id="22a54-235">[What's new in .NET Core](index.md) (Novità di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="22a54-235">[What's new in .NET Core](index.md)</span></span>  
* [<span data-ttu-id="22a54-236">Nuove funzionalità di EF Core 2.1</span><span class="sxs-lookup"><span data-stu-id="22a54-236">New features in EF Core 2.1</span></span>](/ef/core/what-is-new/ef-core-2.1)  
* [<span data-ttu-id="22a54-237">Novità di ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="22a54-237">What's new in ASP.NET Core 2.1</span></span>](/aspnet/core/aspnetcore-2.1)
