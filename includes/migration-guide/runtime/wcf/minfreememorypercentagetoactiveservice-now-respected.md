---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235635"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="f7197-101">L'impostazione MinFreeMemoryPercentageToActiveService viene ora rispettata</span><span class="sxs-lookup"><span data-stu-id="f7197-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f7197-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f7197-102">Details</span></span>|<span data-ttu-id="f7197-103">Questa impostazione consente di stabilire la quantità minima di memoria che deve essere disponibile nel server per poter attivare un servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="f7197-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="f7197-104">È progettata in modo da prevenire le eccezioni <xref:System.OutOfMemoryException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="f7197-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="f7197-105">In .NET Framework 4.5 questa impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="f7197-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="f7197-106">In .NET Framework 4.5.1 questa impostazione viene applicata.</span><span class="sxs-lookup"><span data-stu-id="f7197-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="f7197-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f7197-107">Suggestion</span></span>|<span data-ttu-id="f7197-108">Viene generata un'eccezione se la quantità di memoria libera disponibile sul server Web è inferiore alla percentuale definita dall'impostazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f7197-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="f7197-109">Alcuni servizi WCF correttamente avviati ed eseguiti in un ambiente di memoria limitato potrebbero avere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f7197-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="f7197-110">Ambito</span><span class="sxs-lookup"><span data-stu-id="f7197-110">Scope</span></span>|<span data-ttu-id="f7197-111">Secondario</span><span class="sxs-lookup"><span data-stu-id="f7197-111">Minor</span></span>|
|<span data-ttu-id="f7197-112">Versione</span><span class="sxs-lookup"><span data-stu-id="f7197-112">Version</span></span>|<span data-ttu-id="f7197-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f7197-113">4.5.1</span></span>|
|<span data-ttu-id="f7197-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="f7197-114">Type</span></span>|<span data-ttu-id="f7197-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="f7197-115">Runtime</span></span>|
