---
title: Sito Web che ospita un'applicazione in coda
ms.date: 03/30/2017
ms.assetid: c7a539fa-e442-4c08-a7f1-17b7f5a03e88
ms.openlocfilehash: c8584f78b6b31bc95e088b424122a9cf77a17f27
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402272"
---
# <a name="web-hosting-a-queued-application"></a>Sito Web che ospita un'applicazione in coda
Il servizio di attivazione processo Windows (WAS) gestisce l'attivazione e la durata dei processi di lavoro che contengono applicazioni che servizi di Windows Communication Foundation (WCF) host. Il modello di processo WAS generalizza il modello di processo IIS 6.0 per il server HTTP rimuovendo la dipendenza da HTTP. In questo modo i servizi WCF da usare HTTP e protocolli non HTTP, ad esempio NET. MSMQ e MSMQ. FormatName, in un ambiente di hosting che supporta l'attivazione basata su messaggi e offre la possibilità di ospitare un numero elevato di applicazioni in un determinato computer.  
  
 WAS include un servizio di attivazione di Accodamento messaggi (MSMQ) che attiva un'applicazione in coda quando uno o più i messaggi vengono posizionati in una delle code usate dall'applicazione. Il servizio di attivazione MSMQ è un servizio NT che viene automaticamente avviato per impostazione predefinita.  
  
 Per altre informazioni su WAS e i relativi vantaggi, vedere [Hosting nel servizio Attivazione processo Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md). Per altre informazioni su MSMQ, vedere [panoramica delle code](../../../../docs/framework/wcf/feature-details/queues-overview.md).
  
## <a name="queue-addressing-in-was"></a>Indirizzamento delle code in WAS  
 Le applicazioni WAS hanno indirizzi URL (Uniform Resource Identifier). Gli indirizzi delle applicazioni sono composti di due parti: un prefisso URI di base e un indirizzo relativo specifico dell'applicazione (percorso). Quando vengono congiunte, queste due parti forniscono l'indirizzo esterno di un'applicazione. Il prefisso URI di base viene creato dall'associazione di sito e viene usato per tutte le applicazioni presenti nel sito, ad esempio, "net.msmq://localhost", "msmq.formatname://localhost" o "TCP: //localhost". Gli indirizzi delle applicazioni vengono quindi creati aggiungendo frammenti del percorso specifico dell'applicazione (ad esempio "/ formare") e aggiungerli all'URI di base del prefisso per ottenere l'URI dell'applicazione completo, ad esempio, "MSMQ: //localhost/applicationone".  
  
 Il servizio di attivazione MSMQ usa l'URI dell'applicazione per individuare la coda di cui devono essere monitorati i messaggi. Quando il servizio di attivazione MSMQ viene avviato, enumera tutte le code pubbliche e private presenti nel computer da cui è prevista la ricezione e ne monitora i messaggi. Ogni 10 minuti, il servizio di attivazione MSMQ aggiorna l'elenco di code da monitorare. Quando viene trovato un messaggio in una coda, il servizio di attivazione associa il nome della coda all'URI dell'applicazione corrispondente più lungo per l'associazione net.msmq e attiva l'applicazione.  
  
> [!NOTE]
>  L'applicazione attivata deve corrispondere (corrispondenza più lunga) al prefisso del nome della coda.  
  
 Ad esempio, un nome di coda è: msmqWebHost/orderProcessing/service.svc. Se l'applicazione 1 ha una directory virtuale /msmqWebHost/orderProcessing in cui è presente un file service.svc e l'applicazione 2 ha una directory virtuale /msmqWebHost in cui è presente un file orderProcessing.svc, viene attivata l'applicazione 1. Se l'applicazione 1 viene eliminata, viene attivata l'applicazione 2.  
  
> [!NOTE]
>  Quando viene creata una coda, qualsiasi messaggio inviato a essa non attiva alcuna applicazione fino a quando il servizio di attivazione MSMQ non aggiorna l'elenco delle code, operazione che viene eseguita entro 10 minuti dal momento della creazione della coda. Quando si riavvia il servizio di attivazione viene aggiornato anche l'elenco delle code.  
  
### <a name="the-effect-of-private-and-public-queues-on-addressing"></a>Effetto delle code pubbliche e private sull'indirizzamento  
 Nell'operazione di monitoraggio, il servizio di attivazione MSMQ non fa alcuna distinzione tra code pubbliche e private. Non possono quindi esistere code pubbliche e private con lo stesso nome. In caso contrario, un'applicazione ospitata sul Web potrebbe essere attivata leggendo da entrambi i tipi di coda.  
  
### <a name="queue-configuration-for-activation"></a>Configurazione delle code per l'attivazione  
 Il servizio di attivazione MSMQ viene eseguito come SERVIZIO DI RETE. Si tratta del servizio che monitora le code per attivare applicazioni. Per consentire a tale servizio di attivare applicazioni dalla coda, quest'ultima deve assicurare l'accesso SERVIZIO DI RETE per la lettura dei messaggi presenti nel relativo elenco di controllo di accesso.  
  
### <a name="poison-messaging"></a>Messaggistica non elaborabile  
 Dei messaggi non elaborabili in WCF viene gestito dal canale, che non solo rileva che un messaggio non è elaborabile ma seleziona una disposizione in base alla configurazione utente. Il risultato dell'operazione è la presenza nella coda di un solo messaggio. L'applicazione ospitata sul Web viene interrotta più volte consecutivamente e il messaggio viene spostato in una coda di tentativi. A un certo momento, determinato in base all'intervallo di tempo che intercorre tra i cicli di ripetizione dei tentativi, il messaggio viene spostato dalla coda di tentativi alla coda principale, per riprovare l'operazione. Questo però richiede che il canale in coda sia attivo. Se l'applicazione viene riciclata da WAS, il messaggio resta nella coda di tentativi fino a quando non arriva un altro messaggio nella coda principale, per attivare l'applicazione in coda. La soluzione alternativa in questo caso consiste nello spostare manualmente il messaggio dalla coda di tentativi alla coda principale, per riattivare l'applicazione.  
  
### <a name="subqueue-and-system-queue-caveat"></a>Informazioni sulle code secondarie e le code di sistema  
 Un'applicazione ospitata da WAS non può essere attivata in base a messaggi presenti in una coda di sistema, quale quella di messaggi non recapitabili a livello di sistema, o in code secondarie, quali quelle di messaggi non elaborabili. Si tratta di una limitazione di questa versione del prodotto.  
  
## <a name="see-also"></a>Vedere anche

- [Gestione dei messaggi non elaborabili](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
- [Endpoint di servizio e indirizzamento delle code](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md)
