---
title: 'Mitigazione: Verifica della presenza dei due punti nel percorso'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 342c3ce59ad80c9a60f2a2b69b30f77ff0549415
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176761"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="825dc-102">Mitigazione: Verifica della presenza dei due punti nel percorso</span><span class="sxs-lookup"><span data-stu-id="825dc-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="825dc-103">A partire dalle applicazioni dedicate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], sono state apportate alcune modifiche per supportare i percorsi in precedenza non supportati (entrambi in termini di lunghezza e il formato).</span><span class="sxs-lookup"><span data-stu-id="825dc-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="825dc-104">In particolare, i controlli per la sintassi del separatore dell'unità appropriata (due punti) sono stati resi più corretti.</span><span class="sxs-lookup"><span data-stu-id="825dc-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="825dc-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="825dc-105">Impact</span></span>  
 <span data-ttu-id="825dc-106">Queste modifiche bloccano alcuni percorsi URI supportati in precedenza dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="825dc-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="825dc-107">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="825dc-107">Mitigation</span></span>  
 <span data-ttu-id="825dc-108">Per risolvere il problema di un percorso in precedenza accettabile che non è più supportato dai metodi <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> e <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType>, è possibile eseguire queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="825dc-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="825dc-109">Rimuovere manualmente lo schema da un URL.</span><span class="sxs-lookup"><span data-stu-id="825dc-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="825dc-110">Ad esempio, rimuovere `file://` da un URL.</span><span class="sxs-lookup"><span data-stu-id="825dc-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="825dc-111">Passare l'URI a un costruttore <xref:System.Uri> e recuperare il valore della proprietà <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="825dc-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="825dc-112">Rifiutare esplicitamente la normalizzazione del nuovo percorso impostando il commutatore `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> su `true`.</span><span class="sxs-lookup"><span data-stu-id="825dc-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="825dc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="825dc-113">See also</span></span>

- [<span data-ttu-id="825dc-114">Modifiche di ridestinazione</span><span class="sxs-lookup"><span data-stu-id="825dc-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
