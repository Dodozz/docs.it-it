---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804276"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="6bb11-101">La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6bb11-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6bb11-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6bb11-102">Details</span></span>|<span data-ttu-id="6bb11-103">I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'</span><span class="sxs-lookup"><span data-stu-id="6bb11-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="6bb11-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6bb11-104">Suggestion</span></span>|<span data-ttu-id="6bb11-105">Questo problema è risolto in .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="6bb11-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="6bb11-106">In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6bb11-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="6bb11-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="6bb11-107">Scope</span></span>|<span data-ttu-id="6bb11-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6bb11-108">Edge</span></span>|
|<span data-ttu-id="6bb11-109">Versione</span><span class="sxs-lookup"><span data-stu-id="6bb11-109">Version</span></span>|<span data-ttu-id="6bb11-110">4.5</span><span class="sxs-lookup"><span data-stu-id="6bb11-110">4.5</span></span>|
|<span data-ttu-id="6bb11-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="6bb11-111">Type</span></span>|<span data-ttu-id="6bb11-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="6bb11-112">Runtime</span></span>|
