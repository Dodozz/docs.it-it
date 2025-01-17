---
title: Monitoraggio dell'integrità
description: Esplorare un approccio per implementare il monitoraggio dell'integrità.
ms.date: 01/07/2019
ms.openlocfilehash: b03506972166eec1864de840c1abda05bc3e5277
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639870"
---
# <a name="health-monitoring"></a>Monitoraggio dell'integrità

Il monitoraggio dell'integrità consente di ottenere quasi in tempo reale informazioni sullo stato di contenitori e microservizi. Il monitoraggio dell'integrità è fondamentale per vari aspetti dei microservizi operativi ed è particolarmente importante quando gli agenti di orchestrazione eseguono aggiornamenti parziali dell'applicazione in fasi, come illustrato più avanti.

Le applicazioni basate su microservizi usano spesso heartbeat o controlli di integrità per consentire ai monitor di prestazioni, alle utilità di pianificazione e agli agenti di orchestrazione di tenere traccia dei numerosi servizi. Se i servizi non sono in grado di inviare, su richiesta o in base a una pianificazione, un segnale del tipo "Sono attivo", l'applicazione potrebbe essere esposta a rischi in fase di distribuzione degli aggiornamenti oppure potrebbe rilevare gli errori troppo tardi e non essere in grado di arrestare una catena di errori che può causare interruzioni significative.

Nel modello tipico, i servizi inviano report sul proprio stato e queste informazioni vengono aggregate per fornire una visualizzazione complessiva dello stato di integrità dell'applicazione. Se si usa un agente di orchestrazione, è possibile fornire informazioni sull'integrità al cluster dell'agente di orchestrazione, in modo che il cluster possa agire di conseguenza. Investendo sulla creazione di report sull'integrità di alta qualità personalizzati per l'applicazione, è possibile rilevare e risolvere molto più facilmente i problemi dell'applicazione in esecuzione.

## <a name="implement-health-checks-in-aspnet-core-services"></a>Implementare i controlli di integrità nei servizi ASP.NET Core

Quando si sviluppa un microservizio o un'applicazione Web ASP.NET Core, è possibile usare la funzionalità predefinita per i controlli di integrità rilasciata in ASP .NET Core 2.2. Come molte delle funzionalità di ASP.NET Core, i controlli di integrità includono un set di servizi e un middleware.

I servizi e il middleware per i controlli di integrità sono facili da usare e offrono funzionalità che consentono di accertarsi del corretto funzionamento di qualsiasi risorsa esterna necessaria per l'applicazione (ad esempio un database di SQL Server o un API remota). Quando si usa questa funzionalità, è possibile anche decidere cosa si intende per integrità della risorsa, come illustrato più avanti.

Per usare questa funzionalità in modo efficace, è prima necessario configurare i servizi nei microservizi. In secondo luogo, è necessaria un'applicazione front-end che esegua query per i report sull'integrità. Tale applicazione front-end potrebbe essere un'applicazione di creazione di report personalizzata oppure un agente di orchestrazione in grado di agire in base agli stati di integrità.

### <a name="use-the-healthchecks-feature-in-your-back-end-aspnet-microservices"></a>Usare la funzionalità HealthChecks nei microservizi ASP.NET di back-end

Questa sezione illustra l'uso della funzionalità HealthChecks in un'applicazione API Web 2.2 di ASP.NET Core di esempio. L'implementazione di questa funzionalità in microservizi su larga scala, ad esempio eShopOnContainers, è illustrata nella sezione successiva. Per iniziare, è necessario definire gli elementi che costituiscono uno stato integro per ogni microservizio. Nell'applicazione di esempio, un microservizio è integro se la relativa API è accessibile tramite HTTP e se è disponibile anche il database SQL Server correlato.

In .NET Core 2.2, con le API predefinite, è possibile configurare i servizi, aggiungere un controllo di integrità per il microservizio e il relativo database di SQL Server dipendente in questo modo:

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void ConfigureServices(IServiceCollection services)
{
    //...
    // Registers required services for health checks
    services.AddHealthChecks()
    // Add a health check for a SQL database
    .AddCheck("MyDatabase", new SqlConnectionHealthCheck(Configuration["ConnectionStrings:DefaultConnection"]));
}
```

Nel codice precedente il metodo `services.AddHealthChecks()` configura un controllo HTTP di base che restituisce un codice di stato **200** per lo stato integro.  Inoltre, il metodo di estensione `AddCheck()` configura un `SqlConnectionHealthCheck` personalizzato che controlla l'integrità del database SQL correlato.

Il metodo `AddCheck()` aggiunge un nuovo controllo di integrità con un nome specificato e l'implementazione del tipo `IHealthCheck`. È possibile aggiungere più controlli di integrità usando il metodo AddCheck, in modo che un microservizio non restituisca lo stato di integro fino a quando tutti i controlli non risultano integri.

`SqlConnectionHealthCheck` è una classe personalizzata che implementa `IHealthCheck`, che accetta una stringa di connessione come parametro di costruttore ed esegue una query semplice per verificare se la connessione al database SQL ha esito positivo. Restituisce `HealthCheckResult.Healthy()` se la query è stata eseguita correttamente e `FailureStatus` con l'eccezione effettiva in caso di errore.

```csharp
// Sample SQL Connection Health Check
public class SqlConnectionHealthCheck : IHealthCheck
{
    private static readonly string DefaultTestQuery = "Select 1";

    public string ConnectionString { get; }

    public string TestQuery { get; }

    public SqlConnectionHealthCheck(string connectionString)
        : this(connectionString, testQuery: DefaultTestQuery)
    {
    }

    public SqlConnectionHealthCheck(string connectionString, string testQuery)
    {
        ConnectionString = connectionString ?? throw new ArgumentNullException(nameof(connectionString));
        TestQuery = testQuery;
    }

    public async Task<HealthCheckResult> CheckHealthAsync(HealthCheckContext context, CancellationToken cancellationToken = default(CancellationToken))
    {
        using (var connection = new SqlConnection(ConnectionString))
        {
            try
            {
                await connection.OpenAsync(cancellationToken);

                if (TestQuery != null)
                {
                    var command = connection.CreateCommand();
                    command.CommandText = TestQuery;

                    await command.ExecuteNonQueryAsync(cancellationToken);
                }
            }
            catch (DbException ex)
            {
                return new HealthCheckResult(status: context.Registration.FailureStatus, exception: ex);
            }
        }

        return HealthCheckResult.Healthy();
    }
}
```

Si noti che nel codice precedente, `Select 1` è la query usata per controllare l'integrità del database. Per monitorare la disponibilità dei microservizi, gli agenti di orchestrazione come Kubernetes e Service Fabric eseguono periodicamente controlli di integrità, inviando richieste di esecuzione di test sui microservizi. È importante mantenere efficienti le query sul database in modo che queste operazioni siano veloci e non determinino un maggiore utilizzo delle risorse.

Infine, creare un middleware che risponde al percorso URL "/hc":

```csharp
// Startup.cs from .NET Core 2.2 Web Api sample
//
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecks("/hc");
    //…
} 
```

Quando l'endpoint `<yourmicroservice>/hc` viene richiamato, esegue tutti i controlli di integrità configurati nel metodo `AddHealthChecks()` nella classe di avvio e visualizza il risultato.

### <a name="healthchecks-implementation-in-eshoponcontainers"></a>Implementazione di HealthChecks in eShopOnContainers

I microservizi in eShopOnContainers si basano su più servizi per eseguire le attività. Ad esempio, il microservizio `Catalog.API` da eShopOnContainers dipende da molti servizi, ad esempio Archiviazione BLOB di Azure, SQL Server e RabbitMQ. Pertanto, include diversi controlli di integrità aggiunti con il metodo `AddCheck()`. Per ogni servizio dipendente, è necessario aggiungere un'implementazione personalizzata di `IHealthCheck` che definisce lo stato di integrità corrispondente.

Il progetto open source [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) risolve questo problema fornendo implementazioni per controlli di integrità personalizzati per ognuno di questi servizi aziendali basati su .NET Core 2.2. Ogni controllo di integrità è disponibile come singolo pacchetto NuGet che può essere facilmente aggiunto al progetto. eShopOnContainers li usa ampiamente in tutti i relativi microservizi.

Ad esempio, nel microservizio `Catalog.API` sono stati aggiunti i pacchetti NuGet seguenti:

![Visualizzazione di Esplora soluzioni del progetto Catalog.API in cui si fa riferimento a pacchetti NuGet AspNetCore.Diagnostics.HealthChecks](./media/image6.png)

**Figura 8-7**. Controlli di integrità personalizzati implementati in Catalog.API tramite AspNetCore.Diagnostics.HealthChecks

Nel codice seguente, vengono aggiunte le implementazioni dei controlli di integrità per ogni servizio dipendente e quindi viene configurato il middleware:

```csharp
// Startup.cs from Catalog.api microservice
//
public static IServiceCollection AddCustomHealthCheck(this IServiceCollection services, IConfiguration configuration)
{
    var accountName = configuration.GetValue<string>("AzureStorageAccountName");
    var accountKey = configuration.GetValue<string>("AzureStorageAccountKey");

    var hcBuilder = services.AddHealthChecks();

    hcBuilder
        .AddSqlServer(
            configuration["ConnectionString"],
            name: "CatalogDB-check",
            tags: new string[] { "catalogdb" });

    if (!string.IsNullOrEmpty(accountName) && !string.IsNullOrEmpty(accountKey))
    {
        hcBuilder
            .AddAzureBlobStorage(
                $"DefaultEndpointsProtocol=https;AccountName={accountName};AccountKey={accountKey};EndpointSuffix=core.windows.net",
                name: "catalog-storage-check",
                tags: new string[] { "catalogstorage" });
    }
    if (configuration.GetValue<bool>("AzureServiceBusEnabled"))
    {
        hcBuilder
            .AddAzureServiceBusTopic(
                configuration["EventBusConnection"],
                topicName: "eshop_event_bus",
                name: "catalog-servicebus-check",
                tags: new string[] { "servicebus" });
    }
    else
    {
        hcBuilder
            .AddRabbitMQ(
                $"amqp://{configuration["EventBusConnection"]}",
                name: "catalog-rabbitmqbus-check",
                tags: new string[] { "rabbitmqbus" });
    }

    return services;
}
```

Infine, viene aggiunto il middleware HealthCheck per l'ascolto dell'endpoint "/hc":

```csharp
// HealthCheck middleware
app.UseHealthChecks("/hc", new HealthCheckOptions()
{
    Predicate = _ => true,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
}
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a>Eseguire query sui microservizi per creare report sullo stato di integrità

Dopo aver configurato i controlli di integrità come descritto in questo articolo, quando il microservizio è in esecuzione in Docker è possibile verificarne l'integrità direttamente da un browser. È necessario pubblicare la porta del contenitore nell'host Docker in modo da poter accedere al contenitore tramite l'IP dell'host Docker o tramite `localhost`, come illustrato nella Figura 8-8.

![Visualizzazione nel browser della risposta JSON restituita da un controllo di integrità](./media/image7.png)

**Figura 8-8**. Verifica dello stato di integrità di un singolo servizio da un browser

In questo test, si può notare che il microservizio `Catalog.API` (in esecuzione sulla porta 5101) è integro e restituisce lo stato HTTP 200 e le informazioni sullo stato in JSON. Il servizio ha controllato anche l'integrità della propria dipendenza dal database SQL Server e di RabbitMQ, quindi il controllo di integrità è risultato integro.

## <a name="use-watchdogs"></a>Usare watchdog

Un watchdog è un servizio separato in grado di controllare l'integrità e il carico tra servizi e segnalare l'integrità dei microservizi eseguendo una query con la libreria `HealthChecks` introdotta in precedenza. Ciò consente di evitare gli errori che non verrebbero rilevati in base alla visualizzazione di un singolo servizio. I watchdog possono anche contenere codice in grado di eseguire azioni correttive per condizioni note senza interazione da parte dell'utente.

L'esempio eShopOnContainers contiene una pagina Web che visualizza report di esempio sul controllo di integrità, come illustrato nella figura 8-9. Questo è il tipo watchdog più semplice possibile, poiché si limita a visualizzare lo stato dei microservizi e delle applicazioni Web in eShopOnContainers. In genere un watchdog esegue anche azioni quando rileva stati non integri.

Per fortuna [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks) fornisce anche il pacchetto NuGet [AspNetCore.HealthChecks.UI](https://www.nuget.org/packages/AspNetCore.HealthChecks.UI/) che può essere usato per visualizzare i risultati dei controlli di integrità dagli URI configurati.

![Visualizzazione nel browser dell'app WebStatus, che mostra lo stato di integrità di tutti i microservizi da eShopOnContainers](./media/image8.png)

**Figura 8-9**. Report di controllo di integrità di esempio in eShopOnContainers

In breve, questo servizio watchdog esegue una query sull'endpoint "/hc" di ogni microservizio. In tal modo verranno eseguiti tutti i controlli di integrità definiti al suo interno e verrà restituito uno stato di integrità globale in base a tutti i controlli. L'utilizzo di HealthChecksUI è facile con poche voci di configurazione e due righe di codice che devono essere aggiunte nel file Startup.cs del servizio watchdog.

File di configurazione di esempio per l'interfaccia utente dei controlli di integrità:

```json
// Configuration
{
  "HealthChecks-UI": {
    "HealthChecks": [
      {
        "Name": "Ordering HTTP Check",
        "Uri": "http://localhost:5102/hc"
      },
      {
        "Name": "Ordering HTTP Background Check",
        "Uri": "http://localhost:5111/hc"
      },
      //...
    ]}
}
```

File Startup.cs con aggiunta di HealthChecksUI:

```csharp
// Startup.cs from WebStatus(Watch Dog) service
//
public void ConfigureServices(IServiceCollection services)
{
    //…
    // Registers required services for health checks
    services.AddHealthChecksUI();
}
//…
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseHealthChecksUI(config=> config.UIPath = “/hc-ui”);
    //…
}
```

## <a name="health-checks-when-using-orchestrators"></a>Controlli di integrità quando si usano agenti di orchestrazione

Per monitorare la disponibilità dei microservizi, gli agenti di orchestrazione come Kubernetes e Service Fabric eseguono periodicamente controlli di integrità, inviando richieste di esecuzione di test sui microservizi. Quando un agente di orchestrazione determina che un servizio o contenitore non è integro, interrompe il routing delle richieste a tale istanza. In genere crea anche una nuova istanza di tale contenitore.

Ad esempio, gran parte degli agenti di orchestrazione può usare controlli di integrità per gestire le distribuzioni senza tempi di inattività. Solo quando lo stato di un servizio o contenitore diventa integro, l'agente di orchestrazione avvierà il routing del traffico alle istanze del servizio o contenitore.

Il monitoraggio dell'integrità è particolarmente importante quando un agente di orchestrazione esegue l'aggiornamento dell'applicazione. Alcuni agenti di orchestrazione (ad esempio Azure Service Fabric) aggiornano i servizi in fasi, ad esempio aggiornano un quinto della superficie di cluster per ogni aggiornamento dell'applicazione. Il set di nodi che viene aggiornato allo stesso tempo è detto *dominio di aggiornamento*. Quando un dominio di aggiornamento risulta aggiornato ed è disponibile agli utenti, deve superare i controlli di integrità prima che la distribuzione passi al dominio di aggiornamento successivo.

Un altro aspetto dell'integrità del servizio è la segnalazione delle metriche dal servizio. Si tratta di una funzionalità avanzata del modello di integrità di alcuni agenti di orchestrazione, ad esempio Service Fabric. Le metriche sono importanti quando si usa un agente di orchestrazione perché vengono usate per bilanciare l'utilizzo delle risorse. Le metriche possono anche essere un indicatore dell'integrità del sistema. Ad esempio, un'applicazione potrebbe disporre di molti microservizi e ogni istanza potrebbe segnalare una metrica di richieste al secondo (RPS). Se un servizio usa più risorse (memoria, processore e così via) di un altro servizio, l'agente di orchestrazione potrebbe spostare le istanze del servizio all'interno del cluster per tentare di mantenere uniforme l'utilizzo delle risorse.

Si noti che Azure Service Fabric fornisce il proprio [modello di monitoraggio dell'integrità](/azure/service-fabric/service-fabric-health-introduction), più avanzato rispetto ai semplici controlli di integrità.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Monitoraggio avanzato: visualizzazione, analisi e avvisi

La parte finale del monitoraggio è la visualizzazione del flusso di eventi, la generazione di report sulle prestazioni del servizio e l'invio di avvisi quando vengono rilevati problemi. È possibile usare diverse soluzioni per questo aspetto del monitoraggio.

È possibile usare semplici applicazioni personalizzate che visualizzano lo stato dei servizi, ad esempio la pagina personalizzata visualizzata nella spiegazione di [AspNetCore.Diagnostics.HealthChecks](https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks). In alternativa è possibile usare strumenti più avanzati come [Monitoraggio di Azure](https://azure.microsoft.com/services/monitor/) per la generazione di avvisi in base al flusso di eventi.

Infine, se si archiviano tutti i flussi di eventi, per visualizzare i dati è possibile usare Microsoft Power BI o una soluzione alternativa quale Kibana o Splunk.

## <a name="additional-resources"></a>Risorse aggiuntive

- **HealthChecks e interfaccia utente di HealthChecks per ASP.NET Core** \
  <https://github.com/Xabaril/AspNetCore.Diagnostics.HealthChecks>

- **Introduzione al monitoraggio dell'integrità di Service Fabric** \
  [https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction](/azure/service-fabric/service-fabric-health-introduction)

- **Monitoraggio di Azure**
  <https://azure.microsoft.com/services/monitor/>

>[!div class="step-by-step"]
>[Precedente](implement-circuit-breaker-pattern.md)
>[Successivo](../secure-net-microservices-web-applications/index.md)
