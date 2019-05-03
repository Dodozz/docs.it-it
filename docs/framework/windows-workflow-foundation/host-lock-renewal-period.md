---
title: Host Lock Renewal Period
ms.date: 03/30/2017
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
ms.openlocfilehash: 91d83259c766120f7e3ffc9e49f1cf1b18c32a18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945613"
---
# <a name="host-lock-renewal-period"></a>Host Lock Renewal Period
Il **Host Lock Renewal Period** proprietà la Store di istanza del flusso di lavoro SQL consente di specificare il periodo di tempo entro il quale l'host rinnova il blocco su un'istanza del flusso di lavoro. Il blocco rimane valido per Host Lock Renewal Period + 30 secondi. Se l'host non riesce a rinnovare il blocco (ovvero estende il lease) entro questo periodo di tempo, il blocco scade e il provider di persistenza sblocca l'istanza. Il valore di questa proprietà è di tipo TimeSpan nel formato "hh". Il valore minimo consentito è "00: 00:01" (1 secondo). Il valore predefinito di questa proprietà è "00: 00:30" (30 secondi).  
  
 Questa proprietà è significativa nelle situazioni in cui un host del servizio flusso di lavoro non riesce prima che possa sbloccare un'istanza del servizio flusso di lavoro che possiede. In questo scenario il blocco sull'istanza del servizio flusso di lavoro nel database di persistenza viene rimosso dal provider di persistenza dopo la scadenza del blocco in modo che un altro host del servizio flusso di lavoro in esecuzione nello stesso computer o in un altro computer in una server farm possa acquisire il blocco e caricare l'istanza del servizio flusso di lavoro in memoria per riprendere l'esecuzione dall'ultimo stato persistente.  
  
 L'impostazione di un valore più alto per questa proprietà determina il blocco delle istanze del servizio flusso di lavoro nel database di persistenza per un periodo più lungo e pertanto il recupero dell'istanza dall'ultimo punto di persistenza viene ritardato. L'impostazione di un intervallo breve per questa proprietà determina il prelievo in modo rapido dell'istanza del servizio flusso di lavoro da parte dell'host del servizio flusso di lavoro, ma provoca un aumento del carico di lavoro per l'host del servizio flusso di lavoro e il database di SQL Server.  
  
 L'archivio di istanze del flusso di lavoro SQL esegue un'attività interna che attiva e rileva periodicamente istanze i cui blocchi sono scaduti. Quando trova istanze con i blocchi scaduti, posiziona le istanze nella tabella RunnableInstances in modo che queste istanze possano essere prelevate ed eseguite da un host del flusso di lavoro.
