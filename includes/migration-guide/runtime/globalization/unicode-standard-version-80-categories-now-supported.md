---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236064"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="baa37-101">Le categorie dello standard Unicode versione 8.0 sono ora supportate</span><span class="sxs-lookup"><span data-stu-id="baa37-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="baa37-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="baa37-102">Details</span></span>|<span data-ttu-id="baa37-103">In .NET Framework 4.6.2 i dati Unicode sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="baa37-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="baa37-104">Quando si richiedono le categorie di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="baa37-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="baa37-105">Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.</span><span class="sxs-lookup"><span data-stu-id="baa37-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="baa37-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="baa37-106">Suggestion</span></span>|<span data-ttu-id="baa37-107">Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.</span><span class="sxs-lookup"><span data-stu-id="baa37-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="baa37-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="baa37-108">Scope</span></span>|<span data-ttu-id="baa37-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="baa37-109">Minor</span></span>|
|<span data-ttu-id="baa37-110">Versione</span><span class="sxs-lookup"><span data-stu-id="baa37-110">Version</span></span>|<span data-ttu-id="baa37-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="baa37-111">4.6.2</span></span>|
|<span data-ttu-id="baa37-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="baa37-112">Type</span></span>|<span data-ttu-id="baa37-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="baa37-113">Runtime</span></span>|
|<span data-ttu-id="baa37-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="baa37-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
