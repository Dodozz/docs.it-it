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
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a>Interazione tra criteri di cache: durata massima e validità minima
Per garantire che all'applicazione client venga restituito il contenuto più aggiornato, l'interazione tra criteri di cache del client e requisiti di riconvalida del server determina sempre la creazione dei criteri di cache più conservativi. In tutti gli esempi di questo argomento vengono illustrati i criteri di cache per una risorsa memorizzata nella cache il 1° gennaio con scadenza il 4 gennaio.  
  
 Gli esempi seguenti illustrano i criteri di cache risultanti dall'interazione tra il valore di durata massima (`maxAge`) e il valore di validità minima (`minFresh`).  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e `minFresh` non viene specificato, il contenuto viene riconvalidato il 3 gennaio.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 1 giorno, in base sia al valore di `maxAge` sia al valore di `minFresh`, il contenuto rimane valido fino al 3 gennaio, data in cui deve essere riconvalidato.  
  
-   Se i criteri di cache prevedono l'impostazione di `maxAge` su 2 giorni e di `minFresh` su 2 giorni, in base al valore di `maxAge` il contenuto rimane valido fino al 3 gennaio, mentre in base al valore di `minFresh` è valido fino al 2 gennaio. Il contenuto deve essere quindi riconvalidato il 2 gennaio.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione della cache per le applicazioni di rete](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Criteri di cache](../../../docs/framework/network-programming/cache-policy.md)
- [Criteri di cache basati sulla posizione](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Criteri di cache basati sull'ora](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [Configurazione della memorizzazione nella cache per applicazioni di rete](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
- [Interazione tra criteri di cache: durata massima e obsolescenza massima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
