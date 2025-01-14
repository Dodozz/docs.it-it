---
title: Aggiunta dello stato in linea e non in linea
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 15a963d4de0dcf1d7f0162b0a3266e17d4073ecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857740"
---
# <a name="adding-online-and-offline-status"></a>Aggiunta dello stato in linea e non in linea
In molti casi, per un'applicazione è importante monitorare dettagli specifici riguardanti lo stato di una connessione del canale peer. È possibile ottenere queste informazioni chiamando il metodo `GetProperty` su un'implementazione dell'interfaccia <xref:System.ServiceModel.IOnlineStatus>. Un oggetto con un'implementazione di questa interfaccia può monitorare lo stato della connessione o registrarsi per gestori eventi, ad esempio `OnOnline` e `OnOffline`, e reagire immediatamente quando si verificano modifiche allo stato in linea.  
  
 Nell'infrastruttura del canale peer un client viene considerato in linea se è connesso ad almeno un altro peer, e non in linea in caso contrario. Questo può essere particolarmente utile durante il debug di applicazioni in fase di sviluppo o la visualizzazione di informazioni dettagliate all'utente finale.  
  
> [!NOTE]
>  Un gestore eventi in linea deve innanzitutto assicurarsi che il nodo sia aperto prima dell'invio di qualsiasi messaggio.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di un'applicazione del canale peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
