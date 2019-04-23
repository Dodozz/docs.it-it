---
title: Traccia
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 2379b290494e72b65db5ddc6a7bc5df376d4373f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093397"
---
# <a name="tracing"></a><span data-ttu-id="96e19-102">Traccia</span><span class="sxs-lookup"><span data-stu-id="96e19-102">Tracing</span></span>
<span data-ttu-id="96e19-103">Windows Communication Foundation (WCF) fornisce strumenti applicativi e dati di diagnostica per l'analisi e monitoraggio degli errori.</span><span class="sxs-lookup"><span data-stu-id="96e19-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="96e19-104">Al posto di un debugger, è possibile utilizzare la traccia per capire il comportamento o le cause di errori di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96e19-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="96e19-105">È anche possibile correlare errori e processi attraverso i componenti per fornire un'esperienza end-to-end.</span><span class="sxs-lookup"><span data-stu-id="96e19-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="96e19-106">WCF restituisce i dati seguenti per l'analisi diagnostica:</span><span class="sxs-lookup"><span data-stu-id="96e19-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="96e19-107">Tracce delle attività cardine di processo in tutti i componenti delle applicazioni, ad esempio chiamate dell'operazione, eccezioni del codice, avvisi e altri eventi di elaborazione significativi.</span><span class="sxs-lookup"><span data-stu-id="96e19-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="96e19-108">Eventi di errore di Windows quando la funzionalità di traccia non viene eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="96e19-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96e19-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="96e19-109">In This Section</span></span>  
 [<span data-ttu-id="96e19-110">Configurazione delle funzionalità di traccia</span><span class="sxs-lookup"><span data-stu-id="96e19-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="96e19-111">In questo argomento viene illustrato come è possibile configurare la traccia a livelli diversi per rispondere a requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="96e19-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="96e19-112">Traccia end-to-end</span><span class="sxs-lookup"><span data-stu-id="96e19-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="96e19-113">Contenuto della sezione viene illustrato come utilizzare la traccia e propagazione di attività per la correlazione end-to-end per agevolare il debug.</span><span class="sxs-lookup"><span data-stu-id="96e19-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="96e19-114">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="96e19-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="96e19-115">Contenuto della sezione viene illustrato come utilizzare la traccia per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96e19-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="96e19-116">Problemi di sicurezza e suggerimenti utili per la traccia</span><span class="sxs-lookup"><span data-stu-id="96e19-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="96e19-117">In questo argomento viene descritto come proteggere informazioni riservate e vengono elencati suggerimenti utili durante l'utilizzo di WebHost.</span><span class="sxs-lookup"><span data-stu-id="96e19-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="96e19-118">Riferimenti per le tracce</span><span class="sxs-lookup"><span data-stu-id="96e19-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="96e19-119">Questo argomento elenca tutte le tracce generate da WCF.</span><span class="sxs-lookup"><span data-stu-id="96e19-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e19-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96e19-120">See also</span></span>

- [<span data-ttu-id="96e19-121">Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="96e19-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
