---
title: Debug, traccia e profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 855a1329c9804e4b40d796c639bbe8768156dcc2
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092501"
---
# <a name="debugging-tracing-and-profiling"></a><span data-ttu-id="e5845-102">Debug, traccia e profilatura</span><span class="sxs-lookup"><span data-stu-id="e5845-102">Debugging, Tracing, and Profiling</span></span>
<span data-ttu-id="e5845-103">Per eseguire il debug di un'applicazione .NET Framework, l'ambiente del compilatore e di runtime deve essere configurato per consentire a un debugger di connettersi all'applicazione e di produrre simboli e mappe di linee, se possibile, per l'applicazione e il corrispondente Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e5845-103">To debug a .NET Framework application, the compiler and runtime environment must be configured to enable a debugger to attach to the application and to produce both symbols and line maps, if possible, for the application and its corresponding Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="e5845-104">Dopo il debug di un'applicazione gestita, è possibile eseguire la profilatura per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e5845-104">After a managed application has been debugged, it can be profiled to boost performance.</span></span> <span data-ttu-id="e5845-105">La profilatura valuta e descrive le righe del codice sorgente che generano il codice eseguito con maggiore frequenza e il tempo richiesto per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="e5845-105">Profiling evaluates and describes the lines of source code that generate the most frequently executed code, and how much time it takes to execute them.</span></span>  
  
 <span data-ttu-id="e5845-106">Il debug delle applicazioni .NET framework viene eseguito facilmente tramite Visual Studio, che gestisce molti dettagli della configurazione.</span><span class="sxs-lookup"><span data-stu-id="e5845-106">.NET Framework applications are easily debugged by using Visual Studio, which handles many of the configuration details.</span></span> <span data-ttu-id="e5845-107">Se Visual Studio non è installato, è possibile esaminare e migliorare le prestazioni delle applicazioni .NET Framework usando le classi di debug nello spazio dei nomi <xref:System.Diagnostics> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5845-107">If Visual Studio is not installed, you can examine and improve the performance of .NET Framework applications by using the debugging classes in the .NET Framework <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="e5845-108">Questo spazio dei nomi include le classi <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.TraceSource> per la traccia del flusso di esecuzione e le classi <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> e <xref:System.Diagnostics.PerformanceCounter> per il codice di profilatura.</span><span class="sxs-lookup"><span data-stu-id="e5845-108">This namespace includes the <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug>, and <xref:System.Diagnostics.TraceSource> classes for tracing execution flow, and the <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog>, and <xref:System.Diagnostics.PerformanceCounter> classes for profiling code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5845-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e5845-109">In This Section</span></span>  
 [<span data-ttu-id="e5845-110">Abilitazione del debug ad associazione JIT</span><span class="sxs-lookup"><span data-stu-id="e5845-110">Enabling JIT-Attach Debugging</span></span>](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 <span data-ttu-id="e5845-111">Mostra come configurare il Registro di sistema per eseguire l'associazione JIT di un motore di debug in un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5845-111">Shows how to configure the registry to JIT-attach a debug engine to a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="e5845-112">Semplificazione del debug di un'immagine</span><span class="sxs-lookup"><span data-stu-id="e5845-112">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)  
 <span data-ttu-id="e5845-113">Mostra come attivare il rilevamento JIT e disattivare l'ottimizzazione per rendere più semplice l'esecuzione del debug di un assembly.</span><span class="sxs-lookup"><span data-stu-id="e5845-113">Shows how to turn JIT tracking on and optimization off to make an assembly easier to debug.</span></span>  
  
 [<span data-ttu-id="e5845-114">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="e5845-114">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="e5845-115">Descrive come monitorare l'esecuzione dell'applicazione mentre è in esecuzione e come instrumentarla per visualizzare lo stato o gli errori durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5845-115">Describes how to monitor the execution of your application while it is running, and how to instrument it to display how well it is performing or whether something has gone wrong.</span></span>  
  
 [<span data-ttu-id="e5845-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="e5845-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 <span data-ttu-id="e5845-117">Descrive gli assistenti al debug gestito, strumenti di supporto al debug che funzionano in combinazione con Common Language Runtime (CLR) per fornire informazioni sullo stato di runtime.</span><span class="sxs-lookup"><span data-stu-id="e5845-117">Describes managed debugging assistants (MDAs), which are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span>  
  
 [<span data-ttu-id="e5845-118">Miglioramento del debug tramite gli attributi di visualizzazione del debugger</span><span class="sxs-lookup"><span data-stu-id="e5845-118">Enhancing Debugging with the Debugger Display Attributes</span></span>](../../../docs/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes.md)  
 <span data-ttu-id="e5845-119">Descrive in che modo lo sviluppatore di un tipo può specificarne l'aspetto quando viene visualizzato in un debugger.</span><span class="sxs-lookup"><span data-stu-id="e5845-119">Describes how the developer of a type can specify what that type will look like when it is displayed in a debugger.</span></span>  
  
 [<span data-ttu-id="e5845-120">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="e5845-120">Performance Counters</span></span>](../../../docs/framework/debug-trace-profile/performance-counters.md)  
 <span data-ttu-id="e5845-121">Descrive i contatori che è possibile usare per registrare le prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e5845-121">Describes the counters that you can use to track the performance of an application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5845-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e5845-122">Related Sections</span></span>  
 [<span data-ttu-id="e5845-123">Eseguire il debug di App ASP.NET o ASP.NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5845-123">Debug ASP.NET or ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/debugging-aspnet-and-ajax-applications)  
 <span data-ttu-id="e5845-124">Fornisce i prerequisiti e le istruzioni su come eseguire il debug di un'applicazione ASP.NET durante lo sviluppo o dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e5845-124">Provides prerequisites and instructions for how to debug an ASP.NET application during development or after deployment.</span></span>  
  
 [<span data-ttu-id="e5845-125">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="e5845-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="e5845-126">Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="e5845-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
