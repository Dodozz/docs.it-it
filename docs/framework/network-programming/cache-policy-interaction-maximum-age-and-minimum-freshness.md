---
title: 'Interazione tra criteri di cache: durata massima e validità minima'
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
ms.openlocfilehash: 93136d4c87463db7128a68957b243c1ef13a90eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174057"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="c111e-102">Interazione tra criteri di cache: durata massima e validità minima</span><span class="sxs-lookup"><span data-stu-id="c111e-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>
<span data-ttu-id="c111e-103">Per garantire che all'applicazione client venga restituito il contenuto più aggiornato, l'interazione tra criteri di cache del client e requisiti di riconvalida del server determina sempre la creazione dei criteri di cache più conservativi.</span><span class="sxs-lookup"><span data-stu-id="c111e-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="c111e-104">In tutti gli esempi di questo argomento vengono illustrati i criteri di cache per una risorsa memorizzata nella cache il 1° gennaio con scadenza il 4 gennaio.</span><span class="sxs-lookup"><span data-stu-id="c111e-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="c111e-105">Gli esempi seguenti illustrano i criteri di cache risultanti dall'interazione tra il valore di durata massima (`maxAge`) e il valore di validità minima (`minFresh`).</span><span class="sxs-lookup"><span data-stu-id="c111e-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
-   <span data-ttu-id="c111e-106">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e `minFresh` non viene specificato, il contenuto viene riconvalidato il 3 gennaio.</span><span class="sxs-lookup"><span data-stu-id="c111e-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="c111e-107">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 1 giorno, in base sia al valore di `maxAge`</span><span class="sxs-lookup"><span data-stu-id="c111e-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="c111e-108">sia al valore di `minFresh`, il contenuto rimane valido fino al 3 gennaio,</span><span class="sxs-lookup"><span data-stu-id="c111e-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="c111e-109">data in cui deve essere riconvalidato.</span><span class="sxs-lookup"><span data-stu-id="c111e-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="c111e-110">Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 2 giorni, in base al valore di `maxAge` il contenuto rimane valido fino al 3 gennaio,</span><span class="sxs-lookup"><span data-stu-id="c111e-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="c111e-111">mentre in base al valore di `minFresh` è valido fino al 2 gennaio.</span><span class="sxs-lookup"><span data-stu-id="c111e-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="c111e-112">Il contenuto deve essere quindi riconvalidato il 2 gennaio.</span><span class="sxs-lookup"><span data-stu-id="c111e-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c111e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c111e-113">See also</span></span>

- [<span data-ttu-id="c111e-114">Gestione della cache per le applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c111e-114">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="c111e-115">Criteri di cache</span><span class="sxs-lookup"><span data-stu-id="c111e-115">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="c111e-116">Criteri di cache basati sulla posizione</span><span class="sxs-lookup"><span data-stu-id="c111e-116">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="c111e-117">Criteri di cache basati sull'ora</span><span class="sxs-lookup"><span data-stu-id="c111e-117">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [<span data-ttu-id="c111e-118">Configurazione della memorizzazione nella cache per applicazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c111e-118">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [<span data-ttu-id="c111e-119">Interazione tra criteri di cache: durata massima e obsolescenza massima</span><span class="sxs-lookup"><span data-stu-id="c111e-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
