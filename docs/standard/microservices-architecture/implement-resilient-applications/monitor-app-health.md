---
title: Monitoraggio dell'integrità
description: Esplorare un approccio per implementare il monitoraggio dell'integrità.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: 666b55608ca4e5d18448e1a0b4a1735f3e856474
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362483"
---
# <a name="health-monitoring"></a>Monitoraggio dell'integrità

Il monitoraggio dell'integrità consente di ottenere quasi in tempo reale informazioni sullo stato di contenitori e microservizi. Il monitoraggio dell'integrità è fondamentale per vari aspetti dei microservizi operativi ed è particolarmente importante quando gli agenti di orchestrazione eseguono aggiornamenti parziali dell'applicazione in fasi, come illustrato più avanti.

Le applicazioni basate su microservizi usano spesso heartbeat o controlli di integrità per consentire ai monitor di prestazioni, alle utilità di pianificazione e agli agenti di orchestrazione di tenere traccia dei numerosi servizi. Se i servizi non sono in grado di inviare, su richiesta o in base a una pianificazione, un segnale del tipo "Sono attivo", l'applicazione potrebbe essere esposta a rischi in fase di distribuzione degli aggiornamenti oppure potrebbe rilevare gli errori troppo tardi e non essere in grado di arrestare una catena di errori che può causare interruzioni significative.

Nel modello tipico, i servizi inviano report sul proprio stato e queste informazioni vengono aggregate per fornire una visualizzazione complessiva dello stato di integrità dell'applicazione. Se si usa un agente di orchestrazione, è possibile fornire informazioni sull'integrità al cluster dell'agente di orchestrazione, in modo che il cluster possa agire di conseguenza. Investendo sulla creazione di report sull'integrità di alta qualità personalizzati per l'applicazione, è possibile rilevare e risolvere molto più facilmente i problemi dell'applicazione in esecuzione.

## <a name="implement-health-checks-in-aspnet-core-services"></a>Implementare i controlli di integrità nei servizi ASP.NET Core

Quando si sviluppa un'applicazione Web o un microservizio ASP.NET Core, è possibile usare una libreria fuori banda sperimentale (non appartenente ufficialmente ad ASP.NETCore e ora deprecata), denominata *Health Checks* dal team di ASP.NET. È disponibile in questo [repository GitHub dotnet-architecture](https://github.com/dotnet-architecture/HealthChecks). La versione ufficiale di *Health Checks* [verrà rilasciata in ASP.NET Core 2.2](https://github.com/aspnet/Announcements/issues/307) (data di rilascio prevista entro la fine del 2018).

Questa libreria è facile da usare e offre funzionalità che consentono di accertarsi del corretto funzionamento di qualsiasi risorsa specifica esterna necessaria per l'applicazione (ad esempio un database di SQL Server o un API remota). Quando si usa questa libreria, è possibile anche decidere cosa si intende per integrità della risorsa, come illustrato più avanti.

Per usare questa libreria, è necessario usare prima la libreria presente nei microservizi. In secondo luogo, è necessaria un'applicazione front-end che esegua query per i report sull'integrità. Tale applicazione front-end potrebbe essere un'applicazione di creazione di report personalizzata oppure un agente di orchestrazione in grado di agire in base agli stati di integrità.

### <a name="use-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Usare la libreria HealthChecks nei microservizi ASP.NET di back-end

È possibile verificare come viene usata la libreria HealthChecks nell'applicazione di esempio eShopOnContainers. Per iniziare, è necessario definire gli elementi che costituiscono uno stato integro per ogni microservizio. Nell'applicazione di esempio, un microservizio è integro se la relativa API è accessibile tramite HTTP e se è disponibile anche il database SQL Server correlato.

In futuro sarà possibile installare la libreria HealthChecks come pacchetto NuGet. Al momento della scrittura di questo articolo, tuttavia, è necessario scaricare e compilare il codice come parte della soluzione. Clonare il codice disponibile in <https://github.com/dotnet-architecture/HealthChecks> e copiare le cartelle seguenti nella soluzione:

- src/common
- src/Microsoft.AspNetCore.HealthChecks
- src/Microsoft.Extensions.HealthChecks
- src/Microsoft.Extensions.HealthChecks.SqlServer

È anche possibile usare controlli aggiuntivi, come quelli per Azure (Microsoft.Extensions.HealthChecks.AzureStorage), ma poiché questa versione di eShopOnContainers non presenta dipendenze da Azure, non è necessario. Non sono necessari i controlli di integrità ASP.NET perché eShopOnContainers è basato su ASP.NET Core.

La figura 8-7 illustra la libreria HealthChecks in Visual Studio, pronta per essere usata come blocco predefinito da qualsiasi microservizio.

![Visualizzazione della cartella HealthChecks in Esplora soluzioni con i tre progetti.](./media/image6.png)

**Figura 8-7**. Codice sorgente della libreria HealthChecks di ASP.NET Core in una soluzione Visual Studio

Come descritto in precedenza, la prima operazione da eseguire in ogni progetto di microservizio consiste nell'aggiunta di un riferimento alle tre librerie HealthChecks. Successivamente, occorre aggiungere le azioni di controllo di integrità che si vuole eseguire in tale microservizio. Queste azioni sono fondamentalmente dipendenze da altri microservizi (HttpUrlCheck) o database (attualmente SqlCheck\* per i database SQL Server). Aggiungere l'azione all'interno della classe di avvio di ogni microservizio ASP.NET o applicazione Web ASP.NET.

Ogni servizio o applicazione Web deve essere configurato tramite l'aggiunta di tutte le relative dipendenze HTTP o di database come unico metodo AddHealthCheck. Ad esempio, l'applicazione Web MVC da eShopOnContainers dipende da molti servizi, pertanto dispone di diversi metodi AddCheck aggiunti ai controlli di integrità.

Nel codice (semplificato) seguente, ad esempio, è possibile notare come il microservizio del catalogo aggiunge una dipendenza dal proprio database di SQL Server.

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

Tuttavia, l'applicazione Web MVC di eShopOnContainers presenta più dipendenze dai restanti microservizi. Di conseguenza chiama un solo metodo AddUrlCheck per ogni microservizio, come illustrato nell'esempio (semplificato) seguente:

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

In tal modo, un microservizio non fornisce uno stato "integro" finché non risultano integri anche tutti i controlli.

Se il microservizio non ha una dipendenza da un servizio o SQL Server, è consigliabile aggiungere solo un controllo Healthy("Ok"). Il codice seguente è tratto dal microservizio `basket.api` di eShopOnContainers. (Il microservizio basket usa la cache Redis, ma la libreria non include ancora un provider di controlli di integrità Redis).

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Per poter esporre l'endpoint di controllo di integrità, un servizio o un'applicazione Web deve abilitare il metodo di estensione `UseHealthChecks([*url_for_health_checks*])`. Questo metodo si inserisce al livello di `WebHostBuilder` nel metodo principale della classe `Program` dell'applicazione Web o del servizio ASP.NET Core, subito dopo <xref:Microsoft.AspNetCore.WebHost.CreateDefaultBuilder>, come illustrato nel codice semplificato seguente:

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = WebHost.CreateDefaultBuilder(args)
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseStartup<Startup>()
                .Build();

            host.Run();
        }
    }
}
```

Il processo funziona come segue: ogni microservizio espone l'endpoint /hc. Tale endpoint viene creato dal middleware ASP.NET Core della libreria HealthChecks. Quando l'endpoint viene richiamato, esegue tutti i controlli di integrità configurati nel metodo AddHealthChecks nella classe di avvio.

Il metodo UseHealthChecks prevede una porta o un percorso. Tale porta o percorso è l'endpoint da usare per controllare lo stato di integrità del servizio. Ad esempio, il microservizio del catalogo usa il percorso /hc.

### <a name="cache-health-check-responses"></a>Memorizzare nella cache le risposte del controllo di integrità

Poiché non si vuole causare un attacco Denial of Service (DoS) nei servizi, o semplicemente non si vuole compromettere le prestazioni del servizio con il controllo troppo frequente delle risorse, è possibile memorizzare nella cache i risultati e configurare una durata della cache per ogni controllo di integrità.

Per impostazione predefinita, la durata della cache internamente è impostata su 5 minuti, ma è possibile modificare la durata della cache in ogni controllo di integrità, come illustrato nel codice seguente:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="query-your-microservices-to-report-about-their-health-status"></a>Eseguire query sui microservizi per creare report sullo stato di integrità

Dopo aver configurato i controlli di integrità come descritto in questo articolo, quando il microservizio è in esecuzione in Docker è possibile verificarne l'integrità direttamente da un browser.

È necessario pubblicare la porta del contenitore nell'host Docker in modo da poter accedere al contenitore tramite l'IP dell'host Docker o tramite `localhost`, come illustrato nella Figura 8-8.

![Visualizzazione nel browser della risposta JSON restituita da un controllo di integrità](./media/image7.png)

**Figura 8-8**. Verifica dello stato di integrità di un singolo servizio da un browser

In questo test, si può notare che il microservizio catalog.api (in esecuzione sulla porta 5101) è integro, restituendo lo stato HTTP 200 e le informazioni sullo stato in JSON. Il servizio, inoltre, ha controllato internamente l'integrità dello stato della propria dipendenza dal database SQL Server e anche il controllo di integrità è stato rilevato come integro.

## <a name="use-watchdogs"></a>Usare watchdog

Un watchdog è un servizio separato in grado di controllare l'integrità e il carico tra servizi e segnalare l'integrità dei microservizi eseguendo una query con la libreria `HealthChecks` introdotta in precedenza. Ciò consente di evitare gli errori che non verrebbero rilevati in base alla visualizzazione di un singolo servizio. I watchdog possono anche contenere codice in grado di eseguire azioni correttive per condizioni note senza interazione da parte dell'utente.

L'esempio eShopOnContainers contiene una pagina Web che visualizza report di esempio sul controllo di integrità, come illustrato nella figura 8-9. Questo è il tipo watchdog più semplice possibile, poiché si limita a visualizzare lo stato dei microservizi e delle applicazioni Web in eShopOnContainers. In genere un watchdog esegue anche azioni quando rileva stati non integri.

![Visualizzazione di esplorazione dell'app WebStatus, che illustra lo stato di integrità di cinque microservizi da eShopOnContainers](./media/image8.png)

**Figura 8-9**. Report di controllo di integrità di esempio in eShopOnContainers

In breve, il middleware ASP.NET della libreria HealthChecks di ASP.NET Core fornisce un singolo endpoint di controllo di integrità per ogni microservizio. In tal modo verranno eseguiti tutti i controlli di integrità definiti al suo interno e verrà restituito uno stato di integrità globale in base a tutti i controlli.

La libreria HealthChecks è estensibile tramite nuovi controlli di integrità delle risorse esterne future. Ad esempio, si prevede che in futuro la libreria avrà controlli di integrità per la cache Redis e per altri database. La libreria consente la creazione di report sull'integrità tramite dipendenze di più servizi o applicazioni ed è possibile eseguire azioni in base a tali controlli di integrità.

## <a name="health-checks-when-using-orchestrators"></a>Controlli di integrità quando si usano agenti di orchestrazione

Per monitorare la disponibilità dei microservizi, gli agenti di orchestrazione come Kubernetes e Service Fabric eseguono periodicamente controlli di integrità, inviando richieste di esecuzione di test sui microservizi. Quando un agente di orchestrazione determina che un servizio o contenitore non è integro, interrompe il routing delle richieste a tale istanza. In genere crea anche una nuova istanza di tale contenitore.

Ad esempio, gran parte degli agenti di orchestrazione può usare controlli di integrità per gestire le distribuzioni senza tempi di inattività. Solo quando lo stato di un servizio o contenitore diventa integro, l'agente di orchestrazione avvierà il routing del traffico alle istanze del servizio o contenitore.

Il monitoraggio dell'integrità è particolarmente importante quando un agente di orchestrazione esegue l'aggiornamento dell'applicazione. Alcuni agenti di orchestrazione (ad esempio Azure Service Fabric) aggiornano i servizi in fasi, ad esempio aggiornano un quinto della superficie di cluster per ogni aggiornamento dell'applicazione. Il set di nodi che viene aggiornato allo stesso tempo è detto *dominio di aggiornamento*. Quando un dominio di aggiornamento risulta aggiornato ed è disponibile agli utenti, deve superare i controlli di integrità prima che la distribuzione passi al dominio di aggiornamento successivo.

Un altro aspetto dell'integrità del servizio è la segnalazione delle metriche dal servizio. Si tratta di una funzionalità avanzata del modello di integrità di alcuni agenti di orchestrazione, ad esempio Service Fabric. Le metriche sono importanti quando si usa un agente di orchestrazione perché vengono usate per bilanciare l'utilizzo delle risorse. Le metriche possono anche essere un indicatore dell'integrità del sistema. Ad esempio, un'applicazione potrebbe disporre di molti microservizi e ogni istanza potrebbe segnalare una metrica di richieste al secondo (RPS). Se un servizio usa più risorse (memoria, processore e così via) di un altro servizio, l'agente di orchestrazione potrebbe spostare le istanze del servizio all'interno del cluster per tentare di mantenere uniforme l'utilizzo delle risorse.

Si noti che Azure Service Fabric fornisce il proprio [modello di monitoraggio dell'integrità](/azure/service-fabric/service-fabric-health-introduction), più avanzato rispetto ai semplici controlli di integrità.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Monitoraggio avanzato: visualizzazione, analisi e avvisi

La parte finale del monitoraggio è la visualizzazione del flusso di eventi, la generazione di report sulle prestazioni del servizio e l'invio di avvisi quando vengono rilevati problemi. È possibile usare diverse soluzioni per questo aspetto del monitoraggio.

È possibile usare semplici applicazioni personalizzate che visualizzano lo stato dei servizi, ad esempio la pagina personalizzata visualizzata quando è stata illustrata la libreria [HealthChecks di ASP.NET Core](https://github.com/dotnet-architecture/HealthChecks). In alternativa è possibile usare strumenti più avanzati come Azure Application Insights per la generazione di avvisi in base al flusso di eventi.

Infine, se si archiviano tutti i flussi di eventi, per visualizzare i dati è possibile usare Microsoft Power BI o una soluzione alternativa quale Kibana o Splunk.

## <a name="additional-resources"></a>Risorse aggiuntive

- **ASP.NET Core HealthChecks** (versione sperimentale)\
  [*https://github.com/dotnet-architecture/HealthChecks/*](https://github.com/dotnet-architecture/HealthChecks/)

- **Introduzione al monitoraggio dell'integrità di Service Fabric**\
  [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](/azure/service-fabric/service-fabric-health-introduction)

- **Azure Application Insights**\
  [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

- **Microsoft Operations Management Suite**\
  [*https://www.microsoft.com/cloud-platform/operations-management-suite*](https://www.microsoft.com/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
>[Precedente](implement-circuit-breaker-pattern.md)
>[Successivo](../secure-net-microservices-web-applications/index.md)