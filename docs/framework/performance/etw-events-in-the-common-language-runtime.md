---
title: Eventi ETW in Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d059a5d4df402b309f628bf3e9393114c4cdeec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723199"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="69201-102">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="69201-102">ETW Events in the Common Language Runtime</span></span>
<span data-ttu-id="69201-103">Common Language Runtime (CLR) fornisce utili informazioni di diagnostica ETW (Event Tracing for Windows) tramite svariati eventi di debug e profilatura.</span><span class="sxs-lookup"><span data-stu-id="69201-103">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="69201-104">Gli eventi ETW di CLR sfruttano il sistema di traccia Windows ETW per migliorare il supporto esistente per la profilatura e il debug offerto da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="69201-104">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="69201-105">Per altre informazioni su ETW, vedere l'articolo [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) (Migliorare il debug e l'ottimizzazione delle prestazioni con ETW) su MSDN.</span><span class="sxs-lookup"><span data-stu-id="69201-105">More information about ETW is available in the article [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkID=161142) on MSDN.</span></span> <span data-ttu-id="69201-106">Per informazioni su Xperf, vedere la voce [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) (Xperf di Windows Performance Toolkit) nel blog NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="69201-106">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](https://go.microsoft.com/fwlink/?LinkID=161144) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="69201-107">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] o versioni successive è richiesto per tutti gli eventi descritti in questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="69201-107">The [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="69201-108">Il sistema operativo Windows Vista è il client minimo supportato e Windows Server 2008 è il server minimo supportato.</span><span class="sxs-lookup"><span data-stu-id="69201-108">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69201-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="69201-109">In This Section</span></span>  
 [<span data-ttu-id="69201-110">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69201-110">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 <span data-ttu-id="69201-111">Descrive gli strumenti e i comandi per acquisire e visualizzare gli eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="69201-111">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="69201-112">Provider ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="69201-112">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 <span data-ttu-id="69201-113">Fornisce informazioni sui provider di runtime e rundown e su come usarli per la raccolta di dati ETW.</span><span class="sxs-lookup"><span data-stu-id="69201-113">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="69201-114">Parole chiave e livelli ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="69201-114">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="69201-115">Descrive la parole chiave per i provider di runtime e rundown che consentono di filtrare gli eventi per categoria.</span><span class="sxs-lookup"><span data-stu-id="69201-115">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="69201-116">Eventi ETW di CLR</span><span class="sxs-lookup"><span data-stu-id="69201-116">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)  
 <span data-ttu-id="69201-117">Contiene informazioni dettagliate sugli eventi ETW di CLR e su parole chiave, livelli e dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="69201-117">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69201-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69201-118">See also</span></span>

- [<span data-ttu-id="69201-119">Eventi ETW in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69201-119">ETW Events in the .NET Framework</span></span>](../../../docs/framework/performance/etw-events.md)
