---
title: Progettazione di un modello di dominio del microservizio
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Comprendere i concetti principali quando si progetta un modello di dominio orientato a DDD.
ms.date: 10/08/2018
ms.openlocfilehash: c6d2e84189ff542a2ed4c584c4a47bf7bf0e946a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644187"
---
# <a name="design-a-microservice-domain-model"></a>Progettare un modello di dominio del microservizio

*Definire un modello di dominio avanzato per ogni microservizio aziendale o contesto limitato.*

L'obiettivo consiste nel creare un modello di dominio coerente per ogni microservizio aziendale o contesto limitato. Tenere presente, tuttavia, che un contesto limitato o un microservizio aziendale è costituito talvolta da diversi servizi fisici che condividono un unico modello di dominio. Quest'ultimo deve acquisire le regole, il comportamento, il linguaggio aziendale e i vincoli del singolo contesto delimitato o microservizio aziendale che rappresenta.

## <a name="the-domain-entity-pattern"></a>Schema Domain Entity

Le entità rappresentano oggetti di dominio e vengono definite principalmente in base alla loro identità, continuità e persistenza nel tempo, e non solo in base agli attributi che le caratterizzano. Come sostiene Eric Evans, "un oggetto definito principalmente dalla propria identità prende il nome di entità". Le entità sono molto importanti nel modello di dominio, poiché costituiscono la base per il modello. È quindi necessario identificarle e progettarle attentamente.

*L'identità di un'entità può coinvolgere più microservizi o contesti limitati.*

La stessa identità, ovvero lo stesso valore `Id` ma forse non la stessa entità di dominio, può essere modellata in più microservizi o contesti limitati. Questo non significa tuttavia che la stessa entità, con gli stessi attributi e la stessa logica, venga implementata in più contesti delimitati. Al contrario, le entità presenti in ogni contesto delimitato limitano i relativi attributi e comportamenti a quelli strettamente necessari nel dominio del contesto delimitato.

È possibile, ad esempio, che all'entità "acquirente" sia associata la maggior parte degli attributi di persona definiti nell'entità utente del microservizio dell'identità o del profilo, inclusa l'identità. Nel microservizio degli ordini, tuttavia, è possibile che all'entità acquirente sia associato un minor numero di attributi, poiché solo alcuni dati dell'acquirente sono effettivamente correlati al processo di ordine. Il contesto di ogni microservizio o contesto delimitato influisce sul relativo modello di dominio.

*Le entità di dominio devono implementare il comportamento oltre agli attributi dei dati.*

In una progettazione basata su domini, un'entità di dominio deve implementare la logica di dominio o il comportamento correlato ai dati dell'entità (l'oggetto a cui si accede in memoria). Nell'ambito della classe di un'entità ordine, ad esempio, è necessario che le operazioni e la logica aziendale siano implementate come i metodi per attività quali l'aggiunta di un elemento ordine, la convalida dei dati e il calcolo totale. I metodi di un'entità si occupano delle invarianti e delle regole dell'entità per evitare che le regole vengano disseminate nel livello dell'applicazione.

La figura 7-8 illustra un'entità di dominio che implementa non solo gli attributi dei dati, ma anche le operazioni o i metodi con la logica di dominio correlata.

![Un'entità del modello di dominio implementa i comportamenti usando i metodi, vale a dire, non è un modello "anemico".](./media/image9.png)

**Figura 7-8**. Esempio di progettazione di un'entità di dominio che implementa dati e comportamento

In alcuni casi, naturalmente, è possibile che un'entità non implementi alcuna logica nell'ambito della classe di entità. Questa situazione può verificarsi nelle entità figlio all'interno di un aggregazione se l'entità figlio non contiene alcuna logica speciale, poiché la maggior parte della logica è definita nella radice di aggregazione. Se si ha un microservizio complesso in cui la maggior parte della logica è implementata nelle classi del servizio anziché nelle entità di dominio, è possibile che si abbia a che fare con un modello di dominio anemico, illustrato nella sezione seguente.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Modello di dominio avanzato e modello di dominio anemico a confronto

Nel post [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler descrive così un modello di dominio anemico:

La caratteristica principale di un modello di dominio anemico è che inizialmente sembra un oggetto reale. Alcuni oggetti, denominati in base ai nomi presenti nello spazio di dominio, sono connessi con la stessa struttura e le stesse relazioni avanzate che hanno i veri modelli di dominio. Quando se ne osserva il comportamento, tuttavia, ci si accorge che questi oggetti non hanno pressoché alcun tipo di comportamento, essendo in realtà poco più che contenitori di proprietà Get e Set.

Quando si usa un modello di dominio anemico, ovviamente, questi modelli di dati vengono usati da un set di oggetti servizio (tradizionalmente denominato *livello aziendale*) che acquisisce tutta la logica aziendale o di dominio. Il livello aziendale si basa quindi sul modello di dati, che usa come dati.

Il modello di dominio anemico è una progettazione di tipo procedurale. Gli oggetti entità anemici non sono oggetti reali perché non hanno un comportamento (metodi). Si limitano a contenere proprietà di dati e, pertanto, non hanno una progettazione orientata agli oggetti. Inserendo tutti i tipi di comportamento in oggetti servizio (il livello aziendale), tuttavia, si finisce per avere [blocchi di codice complicato](https://en.wikipedia.org/wiki/Spaghetti_code) o [script transazionali](https://martinfowler.com/eaaCatalog/transactionScript.html) e, quindi, si perdono i vantaggi offerti da un modello di dominio.

Indipendentemente dal fatto che il microservizio o il contesto limitato sia molto semplice (un servizio CRUD), è possibile che il modello di dominio anemico sotto forma di oggetti entità contenenti solo le proprietà dei dati sia sufficiente e, in questo caso, non sarebbe necessario implementare schemi di progettazione basata su domini più complessi. Si tratterà semplicemente di un modello di persistenza, poiché è stata intenzionalmente creata un'entità contenente solo i dati necessari per il servizio CRUD.

Ecco perché le architetture di microservizi sono ideali per un approccio a più architetture basato sul contesto delimitato. In eShopOnContainers, ad esempio, il microservizio degli ordini implementa schemi di progettazione basata su domini, ma non il microservizio catalogo, che è un semplice servizio CRUD.

Alcune persone sostengono che il modello di dominio anemico sia un antipattern: dipende essenzialmente da cosa si sta implementando. Se il microservizio che si sta creando è abbastanza semplice (ad esempio, un servizio CRUD), il modello di dominio anemico che ne consegue non è un antipattern. Se invece è necessario affrontare la complessità di un dominio di microservizio con molte regole in continua evoluzione, è possibile che il modello di dominio anemico sia davvero un antipattern per il microservizio o il contesto limitato in questione. In questo caso, progettandolo come un modello avanzato con entità contenenti dati e comportamento, nonché implementando altri schemi di progettazione basata su domini (aggregazioni, oggetti valore e così via), è possibile ottenere vantaggi significativi per il successo a lungo termine di questo microservizio.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **DevIQ. Entità di dominio** \
  <https://deviq.com/entity/>

- **Martin Fowler. Modello di dominio** \
  <https://martinfowler.com/eaaCatalog/domainModel.html>

- **Martin Fowler. The Anemic Domain Model** \ (Il modello di dominio anemico)
  <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>Schema Value Object

Come ha osservato Eric Evans: "Molti oggetti non hanno un'identità concettuale, ma descrivono alcune caratteristiche di un elemento".

Un'entità richiede un'identità, che non è necessaria invece in molti oggetti presenti in un sistema, come lo schema Value Object. Un oggetto valore è un oggetto senza identità concettuale che descrive un aspetto di un dominio. Si tratta di oggetti per i quali è necessario creare un'istanza che rappresenti gli elementi di progettazione temporaneamente richiesti. L'importante è *cosa* sono, non *chi* sono. Alcuni esempi possono essere numeri e stringhe, ma anche concetti di livello superiore come gruppi di attributi.

È possibile che un elemento che rappresenta un'entità in un microservizio non svolga la stessa funzione in un altro microservizio poiché, in questo secondo caso, il contesto limitato ha un significato diverso. È possibile, ad esempio, che un indirizzo in un'applicazione di e-commerce non abbia alcuna identità, poiché rappresenta solo un gruppo di attributi del profilo cliente relativo a una persona o una società. In questo caso, l'indirizzo deve essere classificato come un oggetto valore. In un'applicazione per una società di energia elettrica, invece, l'indirizzo del cliente può essere importante per il dominio aziendale. L'indirizzo, quindi, deve avere un'identità in modo che il sistema di fatturazione sia direttamente collegato all'indirizzo. In questo caso, l'indirizzo deve essere classificato come un'entità di dominio.

Una persona con un nome e un cognome, in genere, costituisce un'entità perché ogni persona ha un'identità, anche se il nome e il cognome coincidono con un altro set di valori, come nel caso in cui i nomi facciano riferimento anche a una persona diversa.

Gli oggetti valore sono difficili da gestire nei database relazionali e in ORM come Entity Framework, mentre nei database orientati ai documenti sono più facili da implementare e usare.

EF Core 2.0 include la funzionalità [Entità di proprietà](https://devblogs.microsoft.com/dotnet/announcing-entity-framework-core-2-0/#owned-entities-and-table-splitting) che semplifica la gestione degli oggetti valore, come si vedrà in dettaglio più avanti.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Martin Fowler. Schema Value Object** \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Oggetto valore** \
  <https://deviq.com/value-object/>

- **Oggetti valore nello sviluppo basato su test** \
  [https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

- **Eric Evans. Domain-Driven Design (Progettazione basata su domini): Tackling Complexity in the Heart of Software.** (Gestire le complessità nel software) (Libro. Include una trattazione sugli oggetti valore) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

### <a name="the-aggregate-pattern"></a>Schema Aggregate

Un modello di dominio contiene cluster di vari processi ed entità di dati in grado di controllare un'area significativa di funzionalità, ad esempio per la gestione dell'inventario o l'evasione degli ordini. L'aggregazione costituisce un'unità di progettazione basata su domini più dettagliata, che descrive un cluster o un gruppo di entità e comportamenti che è possibile considerare come un'unica unità.

In genere, un'aggregazione viene definita in base alle transazioni necessarie. Un esempio classico è un ordine contenente un elenco di elementi ordine, ciascuno dei quali costituirà un'entità. In particolare, costituirà un'entità figlio all'interno dell'aggregazione ordine, che conterrà anche l'entità ordine come entità principale, solitamente definita "radice di aggregazione".

Identificare le aggregazioni può essere difficile. Un'aggregazione è un gruppo di oggetti che devono essere coerenti tra loro: non è sufficiente, quindi, selezionare un gruppo di oggetti e contrassegnarli come un'aggregazione. È necessario iniziare con il concetto di dominio e prendere in considerazione le entità usate nelle transazioni più comuni relative a questo concetto. Queste entità, che devono essere coerenti a livello di transazione, formano un'aggregazione. Pensare alle operazioni delle transazioni costituisce probabilmente il modo migliore per identificare le aggregazioni.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>Schema Aggregate Root o Root Entity

Un'aggregazione è composta da almeno un'entità: la radice di aggregazione, definita anche entità radice o entità principale. Può avere più entità figlio e oggetti valore, che interagiscono per implementare le transazioni e il comportamento richiesti.

Lo scopo di una radice di aggregazione è garantire la coerenza dell'aggregazione: deve essere il solo punto di ingresso per gli aggiornamenti dell'aggregazione eseguiti tramite operazioni o metodi nella classe della radice di aggregazione. Ma non solo: eventuali modifiche alle entità all'interno dell'aggregazione devono essere apportate solo tramite la radice di aggregazione, che deve controllare la coerenza dell'aggregazione considerando tutte le invarianti e le regole di coerenza che devono essere rispettate nell'aggregazione. Se si modifica un entità figlio o un oggetto valore in modo indipendente, la radice di aggregazione non può garantire che l'aggregazione sia in uno stato valido. Sarebbe come un tavolo con una gamba fissata male. Mantenere la coerenza, quindi, è lo scopo principale della radice di aggregazione.

Nella figura 7-9 è possibile osservare aggregazioni di esempio come l'aggregazione Buyer (acquirente), che contiene un'unica entità (la radice di aggregazione Buyer). L'aggregazione Order contiene invece più entità e un oggetto valore.

![Un modello di dominio DDD è composto da aggregati, un aggregato può avere una o più entità e includere anche oggetti valore.](./media/image10.png)

**Figura 7-9**. Esempio di aggregazioni con una o più entità

L'aggregazione Buyer può avere entità figlio aggiuntive, in base al dominio, come avviene nel microservizio degli ordini nell'applicazione di riferimento eShopOnContainers. La figura 7-9 illustra un caso in cui l'aggregazione Buyer contiene un'unica entità, come esempio di aggregazione contenente solo una radice di aggregazione.

Per mantenere le aggregazioni separate in un modello di progettazione basata su domini, è buona norma impedire l'esplorazione diretta tra le aggregazioni e mantenere solo il campo della chiave esterna, come implementato nel [modello di dominio del microservizio degli ordini](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) in eShopOnContainers. L'entità Order include solo un campo di chiave esterna per l'aggregazione Buyer, ma non una proprietà di navigazione EF Core, come illustrato nel codice seguente:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
    // ... Additional code
}
```

Identificare ed eseguire operazioni sulle aggregazioni richiede esperienza e ricerca. Per altre informazioni, vedere l'elenco di Risorse aggiuntive seguente.

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Vaughn Vernon. Effective Aggregate Design - Part I: (Progettazione efficace delle aggregazioni - Parte I) Modeling a Single Aggregate** (Modellazione di un  singolo aggregato) (da <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_1.pdf>

- **Vaughn Vernon. Effective Aggregate Design - Part II: (Progettazione efficace delle aggregazioni - Parte II) Making Aggregates Work Together** (Integrazione degli aggregati) (da <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf>

- **Vaughn Vernon. Effective Aggregate Design - Part III: (Progettazione efficace delle aggregazioni - Parte III) Gaining Insight Through Discovery** (Ottenere informazioni dettagliate attraverso l'individuazione) (da <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_3.pdf>

- **Sergey Grybniak. DDD Tactical Design Patterns** \ (Schemi progettuali tattici DDD)
  <https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part>

- **Chris Richardson. Developing Transactional Microservices Using Aggregates** \ (Sviluppo di microservizi transazionali usando aggregazioni)
  <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson>

- **DevIQ. Schema Aggregate** \
  <https://deviq.com/aggregate-pattern/>

>[!div class="step-by-step"]
>[Precedente](ddd-oriented-microservice.md)
>[Successivo](net-core-microservice-domain-model.md)
