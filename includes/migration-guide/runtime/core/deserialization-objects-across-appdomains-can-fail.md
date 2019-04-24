---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804211"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="9d55b-101">La deserializzazione di oggetti tra domini app può non riuscire</span><span class="sxs-lookup"><span data-stu-id="9d55b-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9d55b-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d55b-102">Details</span></span>|<span data-ttu-id="9d55b-103">In alcuni casi, quando un'app usa due o più domini di app con diverse basi dell'applicazione, il tentativo di deserializzare gli oggetti nel contesto di una chiamata logica tra domini di app genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="9d55b-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="9d55b-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="9d55b-104">Suggestion</span></span>|<span data-ttu-id="9d55b-105">Vedere [Mitigazione: deserializzazione di oggetti tra domini app](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="9d55b-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="9d55b-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="9d55b-106">Scope</span></span>|<span data-ttu-id="9d55b-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9d55b-107">Edge</span></span>|
|<span data-ttu-id="9d55b-108">Versione</span><span class="sxs-lookup"><span data-stu-id="9d55b-108">Version</span></span>|<span data-ttu-id="9d55b-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="9d55b-109">4.5.1</span></span>|
|<span data-ttu-id="9d55b-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d55b-110">Type</span></span>|<span data-ttu-id="9d55b-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="9d55b-111">Runtime</span></span>|
