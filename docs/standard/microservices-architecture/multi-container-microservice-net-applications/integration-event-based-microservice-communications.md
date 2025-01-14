---
title: Implementazione della comunicazione basata su eventi tra microservizi (eventi di integrazione)
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Riconoscere gli eventi di integrazione per implementare la comunicazione basata su eventi tra microservizi.
ms.date: 10/02/2018
ms.openlocfilehash: 8a5cfa280063da742dc1693905fc44cf870c1fcc
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640719"
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementazione della comunicazione basata su eventi tra microservizi (eventi di integrazione)

Come descritto in precedenza, quando si usa la comunicazione basata su eventi, un microservizio pubblica un evento quando succede qualcosa di rilevante, ad esempio quando aggiorna un'entità di business. Altri microservizi sottoscrivono tali eventi. Quando un microservizio riceve un evento, può aggiornare le proprie entità di business, producendo la pubblicazione di altri eventi. È questa l'essenza del concetto di coerenza finale. Questo sistema di pubblicazione/sottoscrizione viene in genere eseguito usando un'implementazione di un bus di eventi. Il bus di eventi può essere progettato come interfaccia con l'API necessaria per sottoscrivere e annullare la sottoscrizione a eventi e per pubblicare eventi. Può anche avere uno o più implementazioni basate su qualsiasi comunicazione tra processi o di messaggistica, ad esempio una coda di messaggi o un bus di servizio che supporta la comunicazione asincrona e un modello di pubblicazione/sottoscrizione.

È possibile usare gli eventi per implementare le transazioni aziendali che si estendono su più servizi, offrendo una coerenza finale tra tali servizi. Una transazione con coerenza finale consiste in una serie di azioni distribuite. Per ogni azione, il microservizio aggiorna un'entità di business e pubblica un evento che attiva l'azione successiva.

![Microservizio Catalog che usa la comunicazione basata su eventi attraverso un bus di eventi, per ottenere la coerenza finale con Basket e ulteriori microservizi.](./media/image19.png)

**Figura 6-18**. Comunicazione basata sugli eventi in base a un bus di eventi

Questa sezione descrive come è possibile implementare questo tipo di comunicazione con .NET usando un'interfaccia di bus di eventi generica, come illustrato nella figura 6-18. Sono disponibili più implementazioni potenziali, ognuna delle quali usa una tecnologia o un'infrastruttura diversa, ad esempio RabbitMQ, bus di servizio di Azure o qualsiasi altro bus di servizio open source o commerciale di terze parti.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Uso dei broker di messaggi e dei bus di servizio per i sistemi di produzione

Come indicato nella sezione dedicata all'architettura, è possibile scegliere tra più tecnologie di messaggistica per l'implementazione del bus di eventi astratto. Tuttavia, queste tecnologie si trovano a livelli diversi. Ad esempio RabbitMQ, un trasporto di broker di messaggi, è a un livello inferiore rispetto a prodotti commerciali come il bus di servizio di Azure, NServiceBus, MassTransit o Brighter. La maggior parte di questi prodotti può lavorare al di sopra di RabbitMQ o del bus di servizio di Azure. La scelta del prodotto dipende dal numero di funzionalità e dalla quantità di scalabilità predefinita necessaria per l'applicazione.

Per implementare solo un modello di prova del bus di eventi per l'ambiente di sviluppo, come nell'esempio eShopOnContainers, potrebbe essere sufficiente una semplice implementazione sopra RabbitMQ eseguito come contenitore. Ma per i sistemi di produzione e mission-critical che necessitano di una scalabilità elevata, può essere opportuno valutare e usare il bus di servizio di Azure.

Se sono necessarie astrazioni di alto livello e funzionalità più avanzate come [Sagas](https://docs.particular.net/nservicebus/sagas/) per i processi a esecuzione prolungata che facilitano lo sviluppo distribuito, vale la pena prendere in considerazione altri bus di servizio commerciali e open source come NServiceBus, MassTransit e Brighter. In questo caso, le astrazioni e l'API da usare sarebbero direttamente quelle fornite dai bus di servizio di alto livello invece che dalle proprie astrazioni (come le [semplici astrazioni del bus di eventi fornite da eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)). A tale scopo, è possibile ricercare [il duplicato di eShopOnContainers usando NServiceBus](https://go.particular.net/eShopOnContainers) (esempio derivato aggiuntivo, implementato da Particular Software)

Naturalmente, è sempre possibile creare funzionalità personalizzate del bus di servizio sopra tecnologie di livello inferiore, come RabbitMQ e Docker, ma il lavoro necessario per partire da zero potrebbe essere troppo costoso per un'applicazione aziendale personalizzata.

Per reiterare: le astrazioni del bus di eventi di esempio e l'implementazione presentata nell'esempio eShopOnContainers sono destinate a essere utilizzate solo come modello di verifica. Se si decide che si desidera avere la comunicazione asincrona e basata su eventi, come illustrato nella sezione corrente, è consigliabile scegliere il prodotto del bus di servizio più adatto alle proprie esigenze per la produzione.

## <a name="integration-events"></a>Eventi di integrazione

Gli eventi di integrazione vengono usati per sincronizzare lo stato del dominio tra più microservizi o sistemi esterni. Questa operazione viene eseguita con la pubblicazione di eventi di integrazione all'esterno del microservizio. Quando un evento viene pubblicato in più microservizi di tipo ricevitore (in tanti microservizi quanto ne sono stati sottoscritti all'evento di integrazione), il gestore eventi appropriato in ogni microservizio di tipo ricevitore gestisce l'evento.

Un evento di integrazione è sostanzialmente una classe di dati, come nell'esempio seguente:

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

Gli eventi di integrazione possono essere definiti a livello di applicazione di ogni microservizio, in modo che vengono disaccoppiati da altri microservizi, analogamente al modo in cui i ViewModel vengono definiti nel server e nel client. Non è consigliabile però condividere una raccolta di eventi di integrazione comune tra più microservizi: tale operazione comporterebbe l'accoppiamento di tali microservizi con una singola libreria di dati di definizione eventi. Ciò è da evitare per gli stessi motivi per cui non è opportuno condividere un modello di dominio comune tra più microservizi, che devono invece essere completamente autonomi.

Esistono solo alcuni tipi di librerie che è necessario condividere tra i microservizi: le librerie che rappresentano blocchi di applicazione finali, ad esempio l'[API client del bus di eventi](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), come in eShopOnContainers e le librerie che costituiscono gli strumenti condivisibili come componenti NuGet, ad esempio i serializzatori JSON.

## <a name="the-event-bus"></a>Il bus di eventi

Un bus di eventi consente la comunicazione in stile pubblicazione/sottoscrizione tra microservizi senza che i componenti si rilevino esplicitamente a vicenda, come illustrato nella figura 6-19.

![Il modello di base pub/sub, Microservice A pubblica nel Bus di eventi, che distribuisce ai microservizi di sottoscrizione B e C, senza che l'editore debba conoscere i sottoscrittori.](./media/image20.png)

**Figura 6-19**. Nozioni di base di pubblicazione/sottoscrizione con un bus di eventi

Il bus di eventi è correlato allo schema Observer e allo schema publish-subscribe.

### <a name="observer-pattern"></a>Schema Observer

Nello [schema Observer](https://en.wikipedia.org/wiki/Observer_pattern) l'oggetto principale (noto come Observable) notifica agli altri oggetti interessati (noti come Observer) le informazioni pertinenti (eventi).

### <a name="publishsubscribe-pubsub-pattern"></a>Schema di pubblicazione/sottoscrizione (Pub/Sub)

Lo scopo dello [schema di pubblicazione/sottoscrizione](https://docs.microsoft.com/previous-versions/msp-n-p/ff649664(v=pandp.10)) corrisponde a quello dello schema Observer, e cioè notificare agli altri servizi quando si verificano determinati eventi. Ma esiste una differenza importante tra gli schemi Observer e Pub/Sub. Nello schema Observer, la trasmissione viene eseguita direttamente dall'oggetto Observable agli oggetti Observer, in modo che "si riconoscano" tra loro. Ma quando si usa uno schema Pub/Sub, esiste un terzo componente, denominato broker o broker dei messaggi o bus di eventi, noto sia a chi pubblica sia a chi sottoscrive. Di conseguenza, quando si usa lo schema di pubblicazione/sottoscrizione, chi pubblica viene disaccoppiato con precisione dai sottoscrittori, grazie al già citato bus di eventi o broker di messaggi.

### <a name="the-middleman-or-event-bus"></a>L'intermediario, o bus di eventi

Come è possibile ottenere anonimato tra autore e sottoscrittore? Un modo semplice è fare in modo che un intermediario si occupi di tutte le comunicazioni. Tale intermediario è un bus di eventi,

che in genere è costituito da due parti:

- l'astrazione o interfaccia

- una o più implementazioni

Nella figura 6-19 è possibile vedere come, dal punto di vista dell'applicazione, il bus di eventi non è nient'altro che un canale di pubblicazione/sottoscrizione. La modalità di implementazione di questa comunicazione asincrona può variare, perché può avere più implementazioni per poter passare dall'una all'altra, a seconda dei requisiti di ambiente (ad esempio, ambienti di produzione e di sviluppo).

Nella figura 6-20 è possibile visualizzare un'astrazione di un bus di eventi con più implementazioni basate sulle tecnologie di messaggistica di infrastruttura come RabbitMQ, il bus di servizio di Azure o un altro broker di messaggi/eventi.

![È buona norma che il bus di eventi sia definito tramite un'interfaccia, in modo da poter essere implementato con tecnologie diverse, come il bus di servizio di Azure RabbitMQ o altre tecnologie.](./media/image21.png)

**Figura 6- 20.** Più implementazioni di un bus di eventi

Tuttavia, come già accennato in precedenza, usando le proprie astrazioni (l'interfaccia del bus di eventi) è efficace solo se sono necessarie funzionalità del bus di eventi di base supportate dalle astrazioni. Se sono necessarie funzionalità del bus di servizio più avanzate, è consigliabile usare l'API e le astrazioni fornite dal bus di servizio commerciale preferito anziché le proprie astrazioni.

### <a name="defining-an-event-bus-interface"></a>Definizione dell'interfaccia di un bus di eventi

Iniziamo con un codice di implementazione per l'interfaccia del bus di eventi e le possibili implementazioni per scopi di esplorazione. L'interfaccia deve essere generica e semplice, come quella seguente.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);

    void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>;

    void SubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void UnsubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void Unsubscribe<T, TH>()
        where TH : IIntegrationEventHandler<T>
        where T : IntegrationEvent;
}
```

Il metodo `Publish` è semplice. Il bus di eventi trasmetterà l'evento di integrazione che gli è stato passato a qualsiasi microservizio o persino a un'applicazione esterna, sottoscritto a tale evento. Questo metodo viene usato dal microservizio che pubblica l'evento.

I metodi `Subscribe` (sono possibili diverse implementazioni, a seconda degli argomenti) vengono usati dai microservizi che vogliono ricevere gli eventi. Questo metodo prevede due argomenti. Il primo è l'evento di integrazione da sottoscrivere (`IntegrationEvent`). Il secondo argomento è il gestore dell'evento di integrazione (o metodo di callback), denominato `IIntegrationEventHandler<T>`, da eseguire quando il microservizio di tipo ricevitore riceve il messaggio di evento di integrazione.

> [!div class="step-by-step"]
> [Precedente](database-server-container.md)
> [Successivo](rabbitmq-event-bus-development-test-environment.md)
