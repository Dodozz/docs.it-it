---
title: Servizio di routing
ms.date: 03/30/2017
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
ms.openlocfilehash: 511802012a90413a11612406f584c2e2909fe06e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603714"
---
# <a name="routing-service"></a>Servizio di routing
Il servizio di routing è un intermediario SOAP generico che funge da router dei messaggi. La funzionalità principale del servizio di routing consiste nella capacità di indirizzare messaggi in base al relativo contenuto, il che rende possibile l'inoltro di un messaggio a un endpoint client in base a un valore presente all'interno del messaggio stesso, nell'intestazione o nel corpo.  
  
 Il <xref:System.ServiceModel.Routing.RoutingService> viene implementato come servizio Windows Communication Foundation (WCF) nel <xref:System.ServiceModel.Routing> dello spazio dei nomi. Il servizio di routing espone uno o più endpoint servizio che ricevono messaggi e quindi indirizza ogni messaggio a uno o più endpoint client in base al contenuto del messaggio stesso. Il servizio offre le funzionalità indicate di seguito.  
  
- Routing basato sul contenuto  
  
    - Aggregazione dei servizi  
  
    - Controllo delle versioni dei servizi  
  
    - Routing prioritario  
  
    - Configurazione dinamica  
  
- Bridging del protocollo  
  
- Elaborazione SOAP  
  
- Gestione avanzata degli errori  
  
- Endpoint di backup  
  
 Mentre è possibile creare un servizio di intermediario che soddisfi uno o più di questi obiettivi, spesso tale implementazione viene associata a uno scenario o una soluzione specifica e non può essere agevolmente applicata alle nuove applicazioni.  
  
 Il servizio di Routing fornisce un intermediario SOAP di collegamento, generico e dinamicamente configurabile è compatibile con i modelli di servizio WCF e canale, che consente di eseguire routing basato sul contenuto di messaggi basati su SOAP.  
  
> [!NOTE]
>  Attualmente il servizio di routing non supporta il routing dei servizi WCF REST.  Per indirizzare chiamate REST, è consigliabile usare <xref:System.Web.Routing> oppure [Application Request Routing](https://go.microsoft.com/fwlink/?LinkId=164589).  
  
## <a name="content-based-routing"></a>Routing basato sul contenuto  
 Il routing basato sul contenuto consiste nella possibilità di indirizzare un messaggio in base a uno o più valori contenuti nel messaggio. Il servizio di routing controlla ogni messaggio e lo indirizza all'endpoint di destinazione in base ai contenuti del messaggio e alla logica di routing creata. Il routing basato sul contenuto rappresenta la base per l'aggregazione e il controllo delle versioni dei servizi, nonché per il routing prioritario.  
  
 Per implementare il routing basato sul contenuto, il servizio di routing si basa sulle implementazioni di <xref:System.ServiceModel.Dispatcher.MessageFilter> usate per individuare la corrispondenza con valori specifici all'interno dei messaggi da indirizzare. Se un **MessageFilter** corrisponde a un messaggio, il messaggio viene instradato all'endpoint di destinazione associato con il **MessageFilter**.  I filtri messaggi vengono raggruppati in tabelle dei filtri (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) allo scopo di costruire logica di routing complessa. Una tabella dei filtri potrebbe ad esempio contenere cinque filtri messaggi reciprocamente esclusivi che indirizzano i messaggi a uno solo dei cinque endpoint di destinazione.  
  
 Il servizio di routing consente di configurare la logica usata per eseguire routing basato sul contenuto, nonché di aggiornare in modo dinamico la logica di routing in fase di esecuzione.  
  
 Il raggruppamento dei filtri messaggi in apposite tabelle consente di costruire logica di routing in grado di gestire più scenari di routing, ad esempio:  
  
- Aggregazione dei servizi  
  
- Controllo delle versioni dei servizi  
  
- Routing prioritario  
  
- Configurazione dinamica  
  
 Per altre informazioni sui filtri messaggi e le tabelle dei filtri, vedere [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md) e [filtri messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md).  
  
### <a name="service-aggregation"></a>Aggregazione dei servizi  
 Tramite il routing basato sul contenuto è possibile esporre un endpoint che riceve messaggi dalle applicazioni client esterne e quindi indirizza ogni messaggio all'endpoint interno appropriato in base a un valore all'interno del messaggio. Ciò si rivela utile se si desidera offrire un endpoint specifico per una varietà di applicazioni di back-end e presentare un endpoint dell'applicazione ai clienti in fase di esecuzione del factoring dell'applicazione in una varietà di servizi.  
  
### <a name="service-versioning"></a>Controllo delle versioni dei servizi  
 In fase di migrazione a una nuova versione della soluzione, potrebbe essere necessario gestire parallelamente anche la versione precedente per i clienti esistenti. Spesso è quindi necessario che i client che si connettono alla versione più recente usino un indirizzo diverso quando comunicando con la soluzione. Il servizio di routing consente di esporre un endpoint servizio per entrambe le versioni della soluzione indirizzando messaggi alla soluzione appropriata in base a informazioni specifiche della versione contenute nel messaggio. Per un esempio di tale implementazione vedere [How To: Controllo delle versioni del servizio](../../../../docs/framework/wcf/feature-details/how-to-service-versioning.md).  
  
### <a name="priority-routing"></a>Routing prioritario  
 Se si fornisce un servizio per più client, è possibile stipulare con alcuni partner un contratto di servizio in base al quale i rispettivi dati devono essere elaborati separatamente rispetto ai dati degli altri client. Grazie a un filtro che cerca le informazioni specifiche del cliente contenute nel messaggio, è possibile indirizzare agevolmente i messaggi dei partner specifici a un endpoint creato per soddisfare i requisiti del contratto di servizio.  
  
## <a name="dynamic-configuration"></a>Configurazione dinamica  
 Per supportare sistemi di estrema importanza, in cui l'elaborazione dei messaggi non deve implicare interruzioni del servizio, è essenziale poter modificare la configurazione dei componenti all'interno del sistema in fase di esecuzione. Per supportare questa esigenza, il servizio di routing offre un'implementazione di <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.Routing.RoutingExtension>, che consente l'aggiornamento dinamico della configurazione del servizio di routing in fase di esecuzione.  
  
 Per altre informazioni sulla configurazione dinamica del servizio di Routing, vedere [Routing Introduzione](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="protocol-bridging"></a>Bridging del protocollo  
 Una delle sfide degli scenari di intermediari è rappresentata dal fatto che gli endpoint interni possono disporre di requisiti di versione SOAP o trasporto diversi rispetto all'endpoint su cui vengono ricevuti i messaggi. Per supportare questo scenario, il servizio di routing può eseguire il bridge dei protocolli, inclusa l'elaborazione del messaggio SOAP per l'elemento <xref:System.ServiceModel.Channels.MessageVersion> richiesto da uno o più endpoint di destinazione. In questo modo, un protocollo può essere usato per le comunicazione interna, mentre un altro protocollo può essere usato per le comunicazioni esterne.  
  
 Per supportare il routing di messaggi tra endpoint con trasporti diversi, il servizio di routing usa associazioni fornite dal sistema che consentono il bridging di protocolli diversi da parte del servizio. Il bridging viene eseguito automaticamente se l'endpoint servizio esposto dal servizio di routing usa un protocollo diverso rispetto agli endpoint client ai quali vengono indirizzati i messaggi.  
  
## <a name="soap-processing"></a>Elaborazione SOAP  
 Un'esigenza comune relativa al routing è rappresentata dalla capacità di indirizzare messaggi tra endpoint con requisiti SOAP diversi. Per supportare questo requisito, il servizio di Routing fornisce un <xref:System.ServiceModel.Routing.SoapProcessingBehavior> che crea automaticamente un nuovo **MessageVersion** che soddisfi i requisiti dell'endpoint di destinazione prima che il messaggio viene instradato a esso. Questo comportamento crea inoltre una nuova **MessageVersion** per qualsiasi messaggio di risposta prima di restituirlo all'applicazione client richiedente, per garantire che le **MessageVersion** della risposta corrisponda a quella di la richiesta originale.  
  
 Per altre informazioni sull'elaborazione SOAP, vedere [Routing Introduzione](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="error-handling"></a>Gestione degli errori  
 In un sistema costituito da servizi distribuiti che si basano sulle comunicazioni di rete, è importante assicurarsi che le comunicazioni all'interno del sistema non vengano interrotte dagli errori temporanei della rete.  Il servizio di routing implementa la gestione degli errori che consente di gestire molti scenari di errore delle comunicazioni che potrebbero altrimenti comportare un'interruzione del servizio.  
  
 Se si verificano eccezioni <xref:System.ServiceModel.CommunicationException> durante un tentativo di invio di un messaggio da parte del servizio di routing, viene eseguita la gestione degli errori.  Queste eccezioni indicano in genere che si è verificato un problema durante il tentativo di comunicare con l'endpoint client definito, ad esempio <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>.  Il codice di gestione degli errori verrà inoltre rilevare e tentare di ripetere l'invio una **TimeoutException** si verifica, ovvero un'altra eccezione comune non derivata da **CommunicationException**.  
  
 Per altre informazioni sulla gestione degli errori, vedere [Routing Introduzione](../../../../docs/framework/wcf/feature-details/routing-introduction.md).  
  
## <a name="backup-endpoints"></a>Endpoint di backup  
 Oltre agli endpoint client di destinazione associati a ogni definizione di filtro nella tabella dei filtri, è possibile creare un elenco di endpoint di backup a cui indirizzare il messaggio in caso di errore della trasmissione. Se si verifica un errore ed è definito un elenco di backup per la voce di filtro, il servizio di routing tenterà di inviare il messaggio al primo endpoint presente nell'elenco. Se il tentativo di trasmissione ha esito negativo, il servizio tenterà con l'endpoint successivo e così via finché la trasmissione non avrà esito positivo, restituirà un errore non correlato alla trasmissione o finché tutti gli endpoint nell'elenco di backup non avranno restituito un errore di trasmissione.  
  
 Per altre informazioni sugli endpoint di backup, vedere [Routing Introduction](../../../../docs/framework/wcf/feature-details/routing-introduction.md) e [filtri messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md).  
  
## <a name="streaming"></a>Flusso  
 Il servizio di routing può inviare flussi di messaggi se si imposta l'associazione in modo che supporti i flussi.  Tuttavia, in alcune condizioni potrebbe essere necessario memorizzare i messaggi nel buffer:  
  
- Multicast (memorizzazione nel buffer per la creazione di copie aggiuntive dei messaggi)  
  
- Failover (memorizzazione nel buffer nel caso che sia necessario inviare il messaggio a un endpoint di backup)  
  
- System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly impostato su false (memorizzazione nel buffer per inviare a MessageFilterTable un MessageBuffer in modo che i filtri possano esaminare il corpo del messaggio)  
  
- Configurazione dinamica  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione al routing](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
- [Contratti di routing](../../../../docs/framework/wcf/feature-details/routing-contracts.md)
- [Filtri per messaggi](../../../../docs/framework/wcf/feature-details/message-filters.md)
