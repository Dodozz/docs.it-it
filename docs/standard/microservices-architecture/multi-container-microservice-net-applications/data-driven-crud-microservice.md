---
title: Creazione di un microservizio CRUD semplice basato sui dati
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Informazioni sulla creazione di un microservizio CRUD semplice basato sui dati nel contesto di un'applicazione di microservizi.
ms.date: 01/07/2019
ms.openlocfilehash: 53aba727c8dae35df8b34bc1558c0cc390fe2014
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053559"
---
# <a name="creating-a-simple-data-driven-crud-microservice"></a>Creazione di un microservizio CRUD semplice basato sui dati

Questa sezione spiega come creare un semplice microservizio che esegue operazioni CRUD (create, read, update, delete), ovvero di creazione, lettura, aggiornamento ed eliminazione, su un'origine dati.

## <a name="designing-a-simple-crud-microservice"></a>Progettazione di un microservizio CRUD semplice

Dal punto di vista della progettazione, questo tipo di microservizio in contenitori è molto semplice. È probabile che il problema da risolvere sia semplice o che l'implementazione sia solo un modello di verifica.

![Un microservizio CRUD semplice è uno schema progettuale interno.](./media/image4.png)

**Figura 6-4**. Progettazione interna per microservizi CRUD semplici

Un esempio di questo tipo di servizio semplice basato sui dati è il microservizio Catalog dall'applicazione di esempio eShopOnContainers. Questo tipo di servizio implementa tutte le funzionalità in un unico progetto API Web ASP.NET Core che include le classi per il relativo modello di dati, la relativa logica di business e il relativo codice di accesso ai dati. Archivia anche i dati correlati in un database in esecuzione in SQL Server (come un altro contenitore per scopi di sviluppo/test), ma potrebbe essere anche un qualsiasi normale host di SQL Server, come illustrato nella Figura 6-5.

![Il microservizio logico Catalog include il proprio database Catalog, che può essere incluso o meno nello stesso host Docker. Il fatto che il database sia incluso nello stesso host Docker è ottimale per lo sviluppo, ma non per la produzione.](./media/image5.png)

**Figura 6-5**. Progettazione di un microservizio CRUD/basato sui dati semplice

Quando si sviluppa questo tipo di servizio, sono necessari solo [ASP.NET Core](https://docs.microsoft.com/aspnet/core/) e una API di accesso ai dati oppure ORM come [Entity Framework Core](https://docs.microsoft.com/ef/core/index). È anche possibile generare automaticamente metadati [Swagger](https://swagger.io/) tramite [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) per fornire una descrizione delle funzionalità offerte del servizio, come spiegato nella sezione successiva.

Si noti che poter eseguire un server di database, come SQL Server, all'interno di un contenitore Docker è ideale per gli ambienti di sviluppo, perché garantisce che tutte le dipendenze siano attive e in esecuzione senza dover eseguire il provisioning di un database nel cloud o in locale. Questo risulta molto utile quando si eseguono test di integrazione. Per ambienti di produzione, però, è consigliabile non eseguire un server di database in un contenitore perché in genere tale approccio non garantisce una disponibilità elevata. Per un ambiente di produzione in Azure, è consigliabile usare Azure SQL DB o una qualsiasi altra tecnologia di database in grado di offrire disponibilità e scalabilità elevate. Per un approccio NoSQL è ad esempio possibile scegliere CosmosDB.

Modificando infine i file di metadati di Dockerfile e di docker-compose.yml, è possibile configurare la modalità di creazione dell'immagine di questo contenitore, ovvero quale immagine di base userà, oltre ad impostazioni di progettazione, come i nomi interni ed esterni e le porte TCP.

## <a name="implementing-a-simple-crud-microservice-with-aspnet-core"></a>Implementazione di un microservizio CRUD semplice con ASP.NET Core

Per implementare un microservizio CRUD semplice con .NET Core e Visual Studio, è innanzitutto necessario creare un progetto API Web ASP.NET Core semplice (in esecuzione in .NET Core, in modo che sia eseguibile in un host Docker Linux), come illustrato nella Figura 6-6.

![Per creare un progetto API Web ASP.NET Core, selezionare prima un'applicazione Web ASP.NET Core, quindi selezionare il tipo di API.](./media/image6.png)

**Figura 6-6**. Creazione di un progetto API Web ASP.NET Core in Visual Studio

Dopo aver creato il progetto, è possibile implementare i controller MVC, come in qualsiasi altro progetto API Web, usando l'API di Entity Framework o altre API. In un nuovo progetto API Web è possibile notare che l'unica dipendenza presente in tale microservizio è su ASP.NET Core stesso. Internamente, nella dipendenza *Microsoft.AspNetCore.All*, il progetto include riferimenti a Entity Framework e a molti altri pacchetti NuGet di .NET Core, come illustrato nella Figura 6-7.

![Il progetto API include riferimenti al pacchetto NuGet Microsoft.AspNetCore.App, che a sua volta include riferimenti a tutti i pacchetti essenziali. Può anche includere altri pacchetti.](./media/image8.png)

**Figura 6-7**. Dipendenze in un microservizio API Web CRUD semplice

### <a name="implementing-crud-web-api-services-with-entity-framework-core"></a>Implementazione di servizi API Web CRUD con Entity Framework Core

Entity Framework (EF) Core è una versione semplice, estendibile e multipiattaforma della tecnologia di accesso dati Entity Framework più diffusa. EF Core è un mapper relazionale a oggetti che consente agli sviluppatori di .NET di usare un database con gli oggetti .NET.

Il microservizio Catalog usa Entity Framework e il provider SQL Server perché il relativo database è in esecuzione in un contenitore con l'immagine di SQL Server per Linux Docker. Il database può però essere distribuito in qualsiasi istanza di SQL Server, ad esempio Windows locale o Azure SQL DB. L'unico elemento da modificare è la stringa di connessione nel microservizio API Web ASP.NET.

#### <a name="the-data-model"></a>Modello di dati

Con Entity Framework Core, l'accesso ai dati viene eseguito tramite un modello. Un modello è costituito da classi di entità (modello di dominio) e da un contesto derivato (DbContext) che rappresenta una sessione con il database, per eseguire una query e salvare i dati. È possibile generare un modello da un database esistente, scrivere manualmente il codice di un modello in modo che corrisponda al database oppure usare migrazioni di Entity Framework per creare un database a partire dal modello, usando l'approccio incentrato sul codice (che facilita lo sviluppo del database di pari passo con l'evoluzione del modello nel tempo). Per il microservizio Catalog viene usato l'ultimo approccio. Nell'esempio di codice seguente è incluso un esempio della classe di entità CatalogItem, che è una semplice classe di entità [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) (Plain Old CLR Object).

```csharp
public class CatalogItem
{
    public int Id { get; set; }
    public string Name { get; set; }
    public string Description { get; set; }
    public decimal Price { get; set; }
    public string PictureFileName { get; set; }
    public string PictureUri { get; set; }
    public int CatalogTypeId { get; set; }
    public CatalogType CatalogType { get; set; }
    public int CatalogBrandId { get; set; }
    public CatalogBrand CatalogBrand { get; set; }
    public int AvailableStock { get; set; }
    public int RestockThreshold { get; set; }
    public int MaxStockThreshold { get; set; }

    public bool OnReorder { get; set; }
    public CatalogItem() { }

    // Additional code ...
}
```

È inoltre necessario una classe DbContext che rappresenta una sessione con il database. Per il microservizio Catalog la classe CatalogContext deriva dalla classe di base di DbContext, come illustrato nell'esempio seguente:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {
    }
    public DbSet<CatalogItem> CatalogItems { get; set; }
    public DbSet<CatalogBrand> CatalogBrands { get; set; }
    public DbSet<CatalogType> CatalogTypes { get; set; }

    // Additional code ...

}
```

Possono esistere altre implementazioni di `DbContext`. Ad esempio, nel microservizio Catalog.API di esempio, è presente un secondo elemento `DbContext` denominato `CatalogContextSeed` in cui inserisce automaticamente i dati di esempio la prima volta che prova ad accedere al database. Questo metodo è utile anche per i dati di demo e per scenari di test automatizzati.

All'interno di `DbContext` si usa il metodo `OnModelCreating` per personalizzare i mapping di entità di oggetto/database e altri [punti di estendibilità di Entity Framework](https://devblogs.microsoft.com/dotnet/implementing-seeding-custom-conventions-and-interceptors-in-ef-core-1-0/).

##### <a name="querying-data-from-web-api-controllers"></a>Esecuzione di query sui dati da controller API Web

Per recuperare le istanze di classi di entità dal database si usa in genere LINQ (Language Integrated Query), come illustrato nell'esempio seguente:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _catalogContext;
    private readonly CatalogSettings _settings;
    private readonly ICatalogIntegrationEventService _catalogIntegrationEventService;

    public CatalogController(CatalogContext context,
                             IOptionsSnapshot<CatalogSettings> settings,
                             ICatalogIntegrationEventService catalogIntegrationEventService)
    {
        _catalogContext = context ?? throw new ArgumentNullException(nameof(context));
        _catalogIntegrationEventService = catalogIntegrationEventService ?? throw new ArgumentNullException(nameof(catalogIntegrationEventService));

        _settings = settings.Value;
        ((DbContext)context).ChangeTracker.QueryTrackingBehavior = QueryTrackingBehavior.NoTracking;
    }

    // GET api/v1/[controller]/items[?pageSize=3&pageIndex=10]
    [HttpGet]
    [Route("[action]")]
    [ProducesResponseType(typeof(PaginatedItemsViewModel<CatalogItem>), (int)HttpStatusCode.OK)]
    public async Task<IActionResult> Items([FromQuery]int pageSize = 10,
                                           [FromQuery]int pageIndex = 0)

    {
        var totalItems = await _catalogContext.CatalogItems
            .LongCountAsync();

        var itemsOnPage = await _catalogContext.CatalogItems
            .OrderBy(c => c.Name)
            .Skip(pageSize * pageIndex)
            .Take(pageSize)
            .ToListAsync();

        itemsOnPage = ChangeUriPlaceholder(itemsOnPage);

        var model = new PaginatedItemsViewModel<CatalogItem>(
            pageIndex, pageSize, totalItems, itemsOnPage);

        return Ok(model);
    }
    //...
}
```

##### <a name="saving-data"></a>Salvataggio di dati

I dati vengano creati, eliminati e modificati nel database tramite le istanze di classi di entità. È possibile aggiungere codice analogo all'esempio hardcoded seguente (dati fittizi, in questo caso) ai controller API Web.

```csharp
var catalogItem = new CatalogItem() {CatalogTypeId=2, CatalogBrandId=2,
                                     Name="Roslyn T-Shirt", Price = 12};
_context.Catalog.Add(catalogItem);
_context.SaveChanges();
```

##### <a name="dependency-injection-in-aspnet-core-and-web-api-controllers"></a>Inserimento delle dipendenze in ASP.NET Core e controller API Web

In ASP.NET Core è possibile usare il modello predefinito di inserimento delle dipendenze. Non è necessario configurare un contenitore IoC (Inversion of Control) di terze parti, anche se è possibile inserire il contenitore IoC preferito nell'infrastruttura ASP.NET Core. In questo caso, è possibile inserire direttamente la classe DBContext richiesta di Entity Framework o altri repository tramite il costruttore del controller.

Nell'esempio precedente della classe `CatalogController` si inseriscono un oggetto di tipo `CatalogContext` e altri oggetti tramite il costruttore `CatalogController()`.

Un'importante configurazione da definire nel progetto API Web è la registrazione della classe DbContext nel contenitore IoC del servizio. Tale operazione viene in genere eseguita nella classe `Startup` chiamando il metodo `services.AddDbContext<DbContext>()` all'interno del metodo `ConfigureServices()`, come illustrato nell'esempio seguente:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Additional code...

    services.AddDbContext<CatalogContext>(options =>
    {
        options.UseSqlServer(Configuration["ConnectionString"],
        sqlServerOptionsAction: sqlOptions =>
        {
           sqlOptions.
               MigrationsAssembly(
                   typeof(Startup).
                    GetTypeInfo().
                     Assembly.
                      GetName().Name);

           //Configuring Connection Resiliency:
           sqlOptions.
               EnableRetryOnFailure(maxRetryCount: 5,
               maxRetryDelay: TimeSpan.FromSeconds(30),
               errorNumbersToAdd: null);

       });

       // Changing default behavior when client evaluation occurs to throw.
       // Default in EFCore would be to log warning when client evaluation is done.
       options.ConfigureWarnings(warnings => warnings.Throw(
           RelationalEventId.QueryClientEvaluationWarning));
   });

  //...

}
```

### <a name="additional-resources"></a>Risorse aggiuntive

- **Esecuzione di query su dati** \
  [https://docs.microsoft.com/ef/core/querying/index](/ef/core/querying/index)

- **Salvataggio di dati** \
  [https://docs.microsoft.com/ef/core/saving/index](/ef/core/saving/index)

## <a name="the-db-connection-string-and-environment-variables-used-by-docker-containers"></a>Stringa di connessione di database e variabili di ambiente usate dai contenitori Docker

È possibile usare le impostazioni di ASP.NET Core e aggiungere una proprietà ConnectionString al file settings.json come illustrato nell'esempio seguente:

```json
{
    "ConnectionString": "Server=tcp:127.0.0.1,5433;Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word",
    "ExternalCatalogBaseUrl": "http://localhost:5101",
    "Logging": {
        "IncludeScopes": false,
        "LogLevel": {
            "Default": "Debug",
            "System": "Information",
            "Microsoft": "Information"
        }
    }
}
```

Il file settings.json può contenere valori predefiniti per la proprietà ConnectionString o per qualsiasi altra proprietà. Quando si usa Docker, però, tali proprietà verranno però sovrascritte dai valori delle variabili di ambiente specificate nel file docker-compose.override.yml.

Dal file docker-compose.yml o docker-compose.override.yml è possibile inizializzare le variabili di ambiente in modo che Docker le configuri automaticamente come variabili di ambiente del sistema operativo, come illustrato nel file docker-compose.override.yml seguente. In questo esempio la stringa di connessione e le altre righe vanno a capo, ma dovrebbero rimanere sulla stessa riga nel file dell'utente.

```yml
# docker-compose.override.yml

#
catalog.api:
  environment:
    - ConnectionString=Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
    # Additional environment variables for this service
  ports:
    - "5101:80"
```

I file docker-compose.yml a livello di soluzione non sono solo più flessibili dei file di configurazione a livello di progetto o microservizio, ma anche più sicuri se si sostituiscono le variabili di ambiente dichiarate nei file docker-compose con i valori impostati dagli strumenti di distribuzione, ad esempio dalle attività di distribuzione di Azure DevOps Services Docker.

Per ottenere infine tale valore dal codice, è possibile usare Configuration\["ConnectionString"\], come illustrato nel metodo ConfigureServices in un esempio di codice precedente.

Per ambienti di produzione, però, è possibile che si voglia esplorare altre modalità di archiviazione dei segreti, ad esempio le stringhe di connessione. Un metodo ottimale per la gestione dei segreti dell'applicazione è l'uso di [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).

Azure Key Vault contribuisce ad archiviare proteggere i segreti e le chiavi di crittografia usati dai servizi e dalle applicazioni cloud dell'utente. Un segreto è un elemento sul quale di desidera avere un controllo restrittivo, ad esempio le chiavi API, le stringhe di connessione, le password e così via. Il controllo restrittivo include *tra le altre caratteristiche* la registrazione dell'uso, l'impostazione della scadenza e la gestione dell'accesso.

Azure Key Vault consente un livello di controllo molto dettagliato sull'uso dei segreti dell'applicazione, senza che altri utenti debbano conoscerli. I segreti possono anche essere ruotati per la sicurezza avanzata, senza interrompere lo sviluppo o il funzionamento.

Le applicazioni devono essere registrate in Active Directory per l'organizzazione, in modo che possano usare Key Vault.

Per informazioni dettagliate, vedere la *documentazione Concetti di Key Vault*.

### <a name="implementing-versioning-in-aspnet-web-apis"></a>Implementazione del controllo delle versioni in API Web ASP.NET

In seguito alla modifica dei requisiti di business, è possibile che vengano aggiunte nuove raccolte di risorse, che le relazioni tra le risorse cambino e che la struttura dei dati nelle risorse subisca modifiche. L'aggiornamento di un'API Web in modo che possa gestire i nuovi requisiti è un processo relativamente semplice, ma è necessario considerare gli effetti che tali modifiche avranno sulle applicazioni client che utilizzano l'API Web. Anche se lo sviluppatore che progetta e implementa un'API Web dispone del controllo completo su tale API, non può avere lo stesso livello di controllo sulle applicazioni client che potrebbero essere create da organizzazioni di terze parti operanti in remoto.

Il controllo delle versioni consente a un'API Web di indicare le funzionalità e le risorse che espone. Un'applicazione client può quindi inviare richieste a una versione specifica di una funzione o di una risorsa. Esistono diversi approcci per l'implementazione del controllo delle versioni:

- Controllo delle versioni dell'URI

- Controllo delle versioni della stringa di query

- Controllo delle versioni dell'intestazione

Il controllo delle versioni della stringa di query e dell'URI sono i più semplici da implementare. Il controllo delle versioni dell'intestazione costituisce un valido approccio, ma non è esplicito e semplice come il controllo delle versioni dell'URI. Dal momento che è il più semplice e il più esplicito, il controllo delle versioni dell'URI è l'approccio usato nell'applicazione di esempio eShopOnContainers.

Con il controllo delle versioni dell'URI, secondo l'implementazione dell'applicazione di esempio eShopOnContainers, ogni volta che si modifica l'API Web o si cambia lo schema delle risorse, per ogni risorsa viene aggiunto un numero di versione all'URI. Gli URI esistenti continueranno a funzionare come prima, restituendo le risorse conformi allo schema che corrisponde alla versione richiesta.

Come illustrato nell'esempio di codice seguente, è possibile impostare la versione usando l'attributo Route nel controller API Web, in modo da renderla esplicita nell'URI (v1 in questo caso).

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    // Implementation ...
```

Questo meccanismo di controllo delle versioni è semplice e dipende dal server che inoltra la richiesta all'endpoint appropriato. Per un controllo delle versioni più sofisticato e per il metodo migliore quando si usa REST, tuttavia, è opportuno usare ipermedia e implementare [HATEOAS (Hypertext as the Engine of Application State)](https://docs.microsoft.com/azure/architecture/best-practices/api-design#use-hateoas-to-enable-navigation-to-related-resources).

### <a name="additional-resources"></a>Risorse aggiuntive

- **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy (Controllo facilitato delle versioni delle API Web ASP.NET Core RESTful)**  \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Versioning a RESTful web API (Controllo delle versioni delle API Web RESTful)**  \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Roy Fielding. Versioning, Hypermedia, and REST (Controllo delle versioni, ipermedia e REST)**  \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

## <a name="generating-swagger-description-metadata-from-your-aspnet-core-web-api"></a>Generazione dei metadati delle descrizioni Swagger dall'API Web ASP.NET Core

[Swagger](https://swagger.io/) è un framework open source di uso comune basato su un vasto ecosistema di strumenti che consentono di progettare, creare, documentare e utilizzare API RESTful. Si sta affermando come lo standard per il dominio dei metadati delle descrizioni di API. È opportuno includere i metadati delle descrizioni Swagger con qualsiasi tipo di microservizio, sia quelli basati sui dati che quelli più avanzati basati su dominio, come descritto nella sezione seguente.

L'elemento centrale di Swagger è la specifica Swagger, costituita dai metadati delle descrizioni di API salvati in un file JSON o YAML. La specifica crea il contratto RESTful per l'API, che elenca in dettaglio tutte le risorse e le operazioni sia nel formato leggibile che in quello macchina, per agevolare lo sviluppo, l'individuazione e l'integrazione.

La specifica è la base della specifica OpenAPI (OAS) ed è sviluppata in una community aperta, trasparente e collaborativa allo scopo di standardizzare le modalità di definizione delle interfacce RESTful.

La specifica definisce la struttura in base alla quale è possibile individuare un servizio e riconoscerne le funzionalità. Per altre informazioni, incluso un editor Web ed esempi di specifiche Swagger rese disponibili da società quali Spotify, Uber, Slack e Microsoft, visitare il sito di Swagger (<https://swagger.io>).

### <a name="why-use-swagger"></a>Perché usare Swagger?

I motivi principali per generare i metadati di Swagger per le API sono i seguenti.

**Consentire ad altri prodotti di utilizzare e integrare automaticamente le API**. Decine di prodotti e [strumenti in commercio](https://swagger.io/commercial-tools/), oltre a numerosi [framework e librerie](https://swagger.io/open-source-integrations/) supportano Swagger. Microsoft offre prodotti e strumenti di alto livello in grado di utilizzare automaticamente API basate su Swagger, tra cui:

- [AutoRest](https://github.com/Azure/AutoRest). È possibile generare automaticamente le classi client .NET per chiamare Swagger. Questo strumento può essere usato dall'interfaccia della riga di comando ed è inoltre integrato in Visual Studio in modo da poterlo usare più facilmente tramite l'interfaccia utente grafica.

- [Microsoft Flow](https://flow.microsoft.com/). È possibile [usare e integrare automaticamente l'API](https://flow.microsoft.com/blog/integrating-custom-api/) in un flusso di lavoro Microsoft Flow di alto livello senza che siano necessarie competenze di programmazione.

- [Microsoft PowerApps](https://powerapps.microsoft.com/). È possibile utilizzare automaticamente l'API da [app per dispositivi mobili PowerApps](https://powerapps.microsoft.com/blog/register-and-use-custom-apis-in-powerapps/) create con [PowerApps Studio](https://powerapps.microsoft.com/build-powerapps/) senza che siano necessarie competenze di programmazione.

- [App per la logica del servizio app di Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-what-are-logic-apps). È possibile [usare e integrare automaticamente l'API in un'app per la logica del servizio app di Azure](https://docs.microsoft.com/azure/app-service-logic/app-service-logic-custom-hosted-api) senza che siano necessarie competenze di programmazione.

**Consente di generare automaticamente la documentazione dell'API**. Quando si creano API RESTful su vasta scala, ad esempio applicazioni complesse basate su microservizi, è necessario gestire molti endpoint con modelli di dati diversi usati nei payload di richiesta e risposta. Poter disporre della documentazione adeguata e di un solido strumento Esplora API, come avviene con Swagger, è di fondamentale importanza per l'applicazione delle API e per fare in modo che vengano adottate dagli sviluppatori.

Microsoft Flow, PowerApps e le app per la logica di Azure usano proprio i metadati di Swagger per sapere come usare le API e connettersi ad esse.

Sono disponibili diverse opzioni per automatizzare la generazione di metadati di Swagger per le applicazioni API REST di ASP.NET Core, sotto forma di pagine della Guida dell'API funzionale basate su *swagger-ui*.

La più diffusa è probabilmente [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle.AspNetCore), che è usata attualmente in [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) e verrà illustrata in maggior dettaglio in questa guida. È anche possibile usare [NSwag](https://github.com/RSuter/NSwag), che genera client API Typescript e C\# e controller C\# da una specifica Swagger o OpenAPI e anche tramite scansione del file DLL contenente i controller, mediante [NSwagStudio](https://github.com/RSuter/NSwag/wiki/NSwagStudio).

### <a name="how-to-automate-api-swagger-metadata-generation-with-the-swashbuckle-nuget-package"></a>Come automatizzare la generazione di metadati di Swagger per le API con il pacchetto NuGet Swashbuckle

La generazione manuale di metadati di Swagger, in un file JSON o YAML, può essere un lavoro noioso. È però possibile automatizzare l'individuazione delle API per i servizi delle API Web ASP.NET usando il [pacchetto NuGet Swashbuckle](https://aka.ms/swashbuckledotnetcore) per generare dinamicamente i metadati di Swagger per le API.

Swashbuckle genera automaticamente i metadati di Swagger per i progetti di API Web ASP.NET. Supporta i progetti API Web ASP.NET Core e l'API Web ASP.NET tradizionale, oltre a qualsiasi altra versione, ad esempio i microservizi delle app per le API di Azure, per le app per dispositivi mobili di Azure e Azure Service Fabric basati su ASP.NET. Supporta anche API Web semplici distribuite nei contenitori, come nel caso dell'applicazione di riferimento.

Swashbuckle combina Esplora API e Swagger o [swagger-ui](https://github.com/swagger-api/swagger-ui) per offrire un'esperienza di individuazione e documentazione completa per i consumer di API. Oltre al motore di generazione dei metadati di Swagger, Swashbuckle contiene anche una versione incorporata di swagger-ui, che verrà eseguito automaticamente una volta installato Swashbuckle.

Questo significa che è possibile offrire a corredo dell'API con una comoda interfaccia utente di individuazione per consentire agli sviluppatori di usare l'API. Tale interfaccia richiede una minima quantità di codice e manutenzione perché è generata automaticamente, consentendo all'utente di concentrare l'attenzione sulla creazione dell'API. Il risultato per Esplora API è simile a quello illustrato nella Figura 6-8.

![L'API dell'interfaccia utente di Swagger generata da Swashbuckle include tutte le azioni pubblicate.](./media/image9.png)

**Figura 6-8**. Interfaccia Esplora API Swashbuckle basato su metadati di Swagger: microservizio Catalog di eShopOnContainers

Ma l'interfaccia Esplora API non è l'aspetto più interessante in questo caso. Dopo aver creato un'API Web in grado di descrivere se stessa nei metadati di Swagger, è possibile usare facilmente l'API da strumenti basati su Swagger, inclusi i generatori di codice di classe proxy client che possono essere destinati a più piattaforme. Come già accennato, ad esempio, [AutoRest](https://github.com/Azure/AutoRest) genera automaticamente classi client .NET. Ma sono disponibili anche strumenti aggiuntivi, come [swagger codegen](https://github.com/swagger-api/swagger-codegen), che consente di generare automaticamente il codice di librerie client API, stub server e documentazione.

Attualmente Swashbuckle è costituito da cinque pacchetti NuGet interni sotto il metapacchetto di alto livello [Swashbuckle.AspNetCore](https://www.nuget.org/packages/Swashbuckle.AspNetCore) per le applicazioni ASP.NET Core.

Dopo aver installato questi pacchetti NuGet nel progetto API Web, è necessario configurare Swagger nella classe Startup, come illustrato nel codice seguente (semplificato):

```csharp
public class Startup
{
    public IConfigurationRoot Configuration { get; }
    // Other startup code...

    public void ConfigureServices(IServiceCollection services)
    {
        // Other ConfigureServices() code...

        // Add framework services.
        services.AddSwaggerGen(options =>
        {
            options.DescribeAllEnumsAsStrings();
            options.SwaggerDoc("v1", new Swashbuckle.AspNetCore.Swagger.Info
            {
                Title = "eShopOnContainers - Catalog HTTP API",
                Version = "v1",
                Description = "The Catalog Microservice HTTP API. This is a Data-Driven/CRUD microservice sample",
                TermsOfService = "Terms Of Service"
            });
        });

        // Other ConfigureServices() code...
    }

    public void Configure(IApplicationBuilder app,
        IHostingEnvironment env,
        ILoggerFactory loggerFactory)
    {
        // Other Configure() code...
        // ...
        app.UseSwagger()
            .UseSwaggerUI(c =>
            {
                c.SwaggerEndpoint("/swagger/v1/swagger.json", "My API V1");
            });
    }
}
```

Al termine, è possibile avviare l'applicazione e sfogliare gli endpoint dell'interfaccia utente e JSON di Swagger seguenti usando URL simili a questi:

```url
  http://<your-root-url>/swagger/v1/swagger.json

  http://<your-root-url>/swagger/
```

In precedenza è stata illustrata l'interfaccia utente generata creata da Swashbuckle per un URL come `http://<your-root-url>/swagger`. Nella Figura 6-9 è anche possibile vedere come eseguire il test di un qualsiasi metodo di API.

![I dettagli dell'API interfaccia utente di Swagger visualizzano un esempio della risposta e possono essere usati per eseguire l'API reale, molto utile per l'individuazione degli sviluppatori.](./media/image10.png)

**Figura 6-9**. Test del metodo API Catalog/Items nell'interfaccia utente di Swashbuckle

Nella figura 6-10 sono illustrati i metadati JSON di Swagger generati dal microservizio eShopOnContainers (ovvero quello che gli strumenti usano nel livello sottostante) quando si richiede `http://<your-root-url>/swagger/v1/swagger.json` con [Postman](https://www.getpostman.com/).

![Interfaccia utente Postman di esempio con metadati JSON di Swagger](./media/image11.png)

**Figura 6-10**. Metadati JSON di Swagger

È davvero semplice. E dal momento che vengono generati automaticamente, i metadati di Swagger aumenteranno quando si aggiungeranno ulteriori funzionalità all'API.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Pagine della Guida dell'API Web ASP.NET con Swagger** \
  [https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger](/aspnet/core/tutorials/web-api-help-pages-using-swagger)

- **Introduzione a Swashbuckle e ad ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-swashbuckle](/aspnet/core/tutorials/getting-started-with-swashbuckle)

- **Introduzione a NSwag e ad ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/tutorials/getting-started-with-nswag](/aspnet/core/tutorials/getting-started-with-nswag)

> [!div class="step-by-step"]
> [Precedente](microservice-application-design.md)
> [Successivo](multi-container-applications-docker-compose.md)
