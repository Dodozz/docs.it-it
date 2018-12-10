---
title: Monitoraggio dell'integrità
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Monitoraggio dell'integrità
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 35f6d773d714878f56a5e9151320072ebcd51e06
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145975"
---
# <a name="health-monitoring"></a><span data-ttu-id="b54b2-103">Monitoraggio dell'integrità</span><span class="sxs-lookup"><span data-stu-id="b54b2-103">Health monitoring</span></span>

<span data-ttu-id="b54b2-104">Il monitoraggio dell'integrità consente di ottenere quasi in tempo reale informazioni sullo stato di contenitori e microservizi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-104">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="b54b2-105">Il monitoraggio dell'integrità è fondamentale per vari aspetti dei microservizi operativi ed è particolarmente importante quando gli agenti di orchestrazione eseguono aggiornamenti parziali dell'applicazione in fasi, come illustrato più avanti.</span><span class="sxs-lookup"><span data-stu-id="b54b2-105">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="b54b2-106">Le applicazioni basate su microservizi usano spesso heartbeat o controlli di integrità per consentire ai monitor di prestazioni, alle utilità di pianificazione e agli agenti di orchestrazione di tenere traccia dei numerosi servizi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-106">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="b54b2-107">Se i servizi non sono in grado di inviare, su richiesta o in base a una pianificazione, un segnale del tipo "Sono attivo", l'applicazione potrebbe essere esposta a rischi in fase di distribuzione degli aggiornamenti oppure potrebbe rilevare gli errori troppo tardi e non essere in grado di arrestare una catena di errori che potrebbe causare interruzioni significative.</span><span class="sxs-lookup"><span data-stu-id="b54b2-107">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="b54b2-108">Nel modello tipico, i servizi inviano report sul proprio stato e queste informazioni vengono aggregate per fornire una visualizzazione complessiva dello stato di integrità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b54b2-108">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="b54b2-109">Se si usa un agente di orchestrazione, è possibile fornire informazioni sull'integrità al cluster dell'agente di orchestrazione, in modo che il cluster possa agire di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="b54b2-109">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="b54b2-110">Investendo sulla creazione di report sull'integrità di alta qualità, personalizzati per l'applicazione, è possibile rilevare e risolvere molto più facilmente i problemi dell'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b54b2-110">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="b54b2-111">Implementazione dei controlli di integrità nei servizi ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b54b2-111">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="b54b2-112">Quando si sviluppa un'applicazione Web o un microservizio ASP.NET Core, è possibile usare una libreria fuori banda (non ufficiale in quanto parte di ASP.NETCore) denominata `HealthChecks` dal team di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b54b2-112">When developing an ASP.NET Core microservice or web application, you can use an out-of-band library (not official as part of ASP.NETCore) named `HealthChecks` from the ASP.NET team.</span></span> <span data-ttu-id="b54b2-113">È disponibile in questo [repository GitHub](https://github.com/dotnet-architecture/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="b54b2-113">It is available at this [GitHub repo](https://github.com/dotnet-architecture/HealthChecks).</span></span>

<span data-ttu-id="b54b2-114">Questa libreria è facile da usare e offre funzionalità che consentono di accertarsi del corretto funzionamento di qualsiasi risorsa specifica esterna necessaria per l'applicazione (ad esempio un database di SQL Server o un API remota).</span><span class="sxs-lookup"><span data-stu-id="b54b2-114">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="b54b2-115">Quando si usa questa libreria, è possibile anche decidere cosa si intende per integrità della risorsa, come illustrato più avanti.</span><span class="sxs-lookup"><span data-stu-id="b54b2-115">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="b54b2-116">Per usare questa libreria, è necessario usare prima la libreria presente nei microservizi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-116">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="b54b2-117">In secondo luogo, è necessaria un'applicazione front-end che esegua query per i report sull'integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-117">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="b54b2-118">Tale applicazione front-end potrebbe essere un'applicazione di creazione di report personalizzata oppure un agente di orchestrazione in grado di agire in base agli stati di integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-118">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="b54b2-119">Uso della libreria HealthChecks nei microservizi ASP.NET di back-end</span><span class="sxs-lookup"><span data-stu-id="b54b2-119">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="b54b2-120">È possibile verificare come viene usata la libreria HealthChecks nell'applicazione di esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b54b2-120">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="b54b2-121">Per iniziare, è necessario definire gli elementi che costituiscono uno stato integro per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-121">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="b54b2-122">Nell'applicazione di esempio, un microservizio è integro se la relativa API è accessibile tramite HTTP e se è disponibile anche il database SQL Server correlato.</span><span class="sxs-lookup"><span data-stu-id="b54b2-122">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="b54b2-123">In futuro, sarà possibile installare la libreria HealthChecks come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="b54b2-123">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="b54b2-124">Al momento della scrittura di questo articolo, tuttavia, è necessario scaricare e compilare il codice come parte della soluzione.</span><span class="sxs-lookup"><span data-stu-id="b54b2-124">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="b54b2-125">Clonare il codice disponibile in https://github.com/dotnet-architecture/HealthChecks e copiare le cartelle seguenti nella soluzione:</span><span class="sxs-lookup"><span data-stu-id="b54b2-125">Clone the code available at https://github.com/dotnet-architecture/HealthChecks and copy the following folders to your solution:</span></span>

  - <span data-ttu-id="b54b2-126">src/common</span><span class="sxs-lookup"><span data-stu-id="b54b2-126">src/common</span></span>
  - <span data-ttu-id="b54b2-127">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="b54b2-127">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="b54b2-128">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="b54b2-128">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="b54b2-129">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="b54b2-129">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="b54b2-130">È anche possibile usare controlli aggiuntivi, come quelli per Azure (Microsoft.Extensions.HealthChecks.AzureStorage), ma poiché questa versione di eShopOnContainers non presenta dipendenze da Azure, non è necessario.</span><span class="sxs-lookup"><span data-stu-id="b54b2-130">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="b54b2-131">Non sono necessari i controlli di integrità ASP.NET perché eShopOnContainers è basato su ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b54b2-131">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="b54b2-132">La figura 10-6 mostra la libreria HealthChecks in Visual Studio, pronta per essere usata come blocco predefinito da qualsiasi microservizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-132">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="b54b2-133">**Figura 10-6**.</span><span class="sxs-lookup"><span data-stu-id="b54b2-133">**Figure 10-6**.</span></span> <span data-ttu-id="b54b2-134">Codice sorgente della libreria HealthChecks di ASP.NET Core in una soluzione Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b54b2-134">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="b54b2-135">Come descritto in precedenza, la prima operazione da eseguire in ogni progetto di microservizio consiste nell'aggiunta di un riferimento alle tre librerie HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="b54b2-135">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="b54b2-136">Successivamente, occorre aggiungere le azioni di controllo di integrità che si vuole eseguire in tale microservizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-136">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="b54b2-137">Queste azioni sono fondamentalmente dipendenze da altri microservizi (HttpUrlCheck) o database (attualmente SqlCheck\* per i database SQL Server).</span><span class="sxs-lookup"><span data-stu-id="b54b2-137">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="b54b2-138">Aggiungere l'azione all'interno della classe di avvio di ogni microservizio ASP.NET o applicazione Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b54b2-138">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="b54b2-139">Ogni servizio o applicazione Web deve essere configurato tramite l'aggiunta di tutte le relative dipendenze HTTP o di database come unico metodo AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="b54b2-139">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="b54b2-140">Ad esempio, l'applicazione Web MVC da eShopOnContainers dipende da molti servizi, pertanto dispone di diversi metodi AddCheck aggiunti ai controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-140">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="b54b2-141">Nel codice seguente, ad esempio, è possibile notare come il microservizio del catalogo aggiunge una dipendenza dal proprio database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b54b2-141">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

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

<span data-ttu-id="b54b2-142">Tuttavia, l'applicazione Web MVC di eShopOnContainers presenta più dipendenze dai restanti microservizi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-142">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="b54b2-143">Di conseguenza chiama un solo metodo AddUrlCheck per ogni microservizio, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b54b2-143">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

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

<span data-ttu-id="b54b2-144">In tal modo, un microservizio non fornisce uno stato "integro" finché non risultano integri anche tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="b54b2-144">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="b54b2-145">Se il microservizio non ha una dipendenza da un servizio o SQL Server, è consigliabile aggiungere solo un controllo Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="b54b2-145">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="b54b2-146">Il codice seguente è tratto dal microservizio basket.api di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b54b2-146">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="b54b2-147">(Il microservizio basket usa la cache Redis, ma la libreria non include ancora un provider di controlli di integrità Redis).</span><span class="sxs-lookup"><span data-stu-id="b54b2-147">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="b54b2-148">Perché un servizio o un'applicazione Web esponga l'endpoint di controllo di integrità, deve abilitare il metodo di estensione UseHealthChecks(\[*url\_for\_health\_checks*\]).</span><span class="sxs-lookup"><span data-stu-id="b54b2-148">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="b54b2-149">Questo metodo si inserisce al livello di WebHostBuilder nel metodo principale della classe di programma dell'applicazione Web o servizio ASP.NET Core, subito dopo UseKestrel, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b54b2-149">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

<span data-ttu-id="b54b2-150">Il processo è simile al seguente: ogni microservizio espone l'endpoint /hc.</span><span class="sxs-lookup"><span data-stu-id="b54b2-150">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="b54b2-151">Tale endpoint viene creato dal middleware ASP.NET Core della libreria HealthChecks.</span><span class="sxs-lookup"><span data-stu-id="b54b2-151">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="b54b2-152">Quando l'endpoint viene richiamato, esegue tutti i controlli di integrità configurati nel metodo AddHealthChecks nella classe di avvio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-152">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="b54b2-153">Il metodo UseHealthChecks prevede una porta o un percorso.</span><span class="sxs-lookup"><span data-stu-id="b54b2-153">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="b54b2-154">Tale porta o percorso è l'endpoint da usare per controllare lo stato di integrità del servizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-154">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="b54b2-155">Ad esempio, il microservizio del catalogo usa il percorso /hc.</span><span class="sxs-lookup"><span data-stu-id="b54b2-155">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="b54b2-156">Memorizzazione nella cache delle risposte del controllo di integrità</span><span class="sxs-lookup"><span data-stu-id="b54b2-156">Caching health check responses</span></span>

<span data-ttu-id="b54b2-157">Poiché non si vuole causare un attacco Denial of Service (DoS) nei servizi, o semplicemente non si vuole compromettere le prestazioni del servizio con il controllo troppo frequente delle risorse, è possibile memorizzare nella cache i risultati e configurare una durata della cache per ogni controllo di integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-157">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="b54b2-158">Per impostazione predefinita, la durata della cache internamente è impostata su 5 minuti, ma è possibile modificare la durata della cache in ogni controllo di integrità, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b54b2-158">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="b54b2-159">Esecuzione di query sui microservizi per creare report sullo stato di integrità</span><span class="sxs-lookup"><span data-stu-id="b54b2-159">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="b54b2-160">Dopo aver configurato i controlli di integrità come descritto in questo articolo, quando il microservizio è in esecuzione in Docker, è possibile verificare se è integro direttamente da un browser.</span><span class="sxs-lookup"><span data-stu-id="b54b2-160">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="b54b2-161">Per eseguire questa operazione è necessario pubblicare la porta del contenitore esternamente all'host Docker in modo da poter accedere al contenitore tramite localhost o tramite l'IP dell'host Docker esterno. La figura 10-7 mostra una richiesta in un browser e la risposta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b54b2-161">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="b54b2-162">**Figura 10-7**.</span><span class="sxs-lookup"><span data-stu-id="b54b2-162">**Figure 10-7**.</span></span> <span data-ttu-id="b54b2-163">Verifica dello stato di integrità di un singolo servizio da un browser</span><span class="sxs-lookup"><span data-stu-id="b54b2-163">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="b54b2-164">In questo test, si può notare che il microservizio catalog.api (in esecuzione sulla porta 5101) è integro, restituendo lo stato HTTP 200 e le informazioni sullo stato in JSON.</span><span class="sxs-lookup"><span data-stu-id="b54b2-164">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="b54b2-165">Il servizio, inoltre, ha controllato internamente l'integrità dello stato della propria dipendenza dal database SQL Server e anche il controllo di integrità è stato rilevato come integro.</span><span class="sxs-lookup"><span data-stu-id="b54b2-165">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="b54b2-166">Uso di watchdog</span><span class="sxs-lookup"><span data-stu-id="b54b2-166">Using watchdogs</span></span>

<span data-ttu-id="b54b2-167">Un watchdog è un servizio separato in grado di controllare l'integrità e il carico tra servizi e segnalare l'integrità dei microservizi eseguendo una query con la libreria HealthChecks introdotta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b54b2-167">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="b54b2-168">Ciò consente di evitare gli errori che non verrebbero rilevati in base alla visualizzazione di un singolo servizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-168">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="b54b2-169">I watchdog possono anche contenere codice in grado di eseguire azioni correttive per condizioni note senza interazione da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b54b2-169">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="b54b2-170">L'esempio eShopOnContainers contiene una pagina Web che mostra report sul controllo di integrità di esempio, come illustrato nella figura 10-8.</span><span class="sxs-lookup"><span data-stu-id="b54b2-170">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="b54b2-171">Questo è il tipo watchdog più semplice possibile poiché si limita a mostrare lo stato dei microservizi e delle applicazioni Web in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b54b2-171">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="b54b2-172">In genere un watchdog esegue anche azioni quando rileva stati non integri.</span><span class="sxs-lookup"><span data-stu-id="b54b2-172">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="b54b2-173">**Figura 10-8**.</span><span class="sxs-lookup"><span data-stu-id="b54b2-173">**Figure 10-8**.</span></span> <span data-ttu-id="b54b2-174">Report di controllo di integrità di esempio in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="b54b2-174">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="b54b2-175">In breve, il middleware ASP.NET della libreria HealthChecks di ASP.NET Core fornisce un singolo endpoint di controllo di integrità per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-175">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="b54b2-176">In tal modo verranno eseguiti tutti i controlli di integrità definiti al suo interno e verrà restituito uno stato di integrità globale in base a tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="b54b2-176">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="b54b2-177">La libreria HealthChecks è estensibile tramite nuovi controlli di integrità delle risorse esterne future.</span><span class="sxs-lookup"><span data-stu-id="b54b2-177">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="b54b2-178">Ad esempio, si prevede che in futuro la libreria avrà controlli di integrità per la cache Redis e per altri database.</span><span class="sxs-lookup"><span data-stu-id="b54b2-178">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="b54b2-179">La libreria consente la creazione di report sull'integrità tramite dipendenze di più servizi o applicazioni ed è possibile eseguire azioni in base a tali controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-179">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="b54b2-180">Controlli di integrità quando si usano agenti di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="b54b2-180">Health checks when using orchestrators</span></span>

<span data-ttu-id="b54b2-181">Per monitorare la disponibilità dei microservizi, gli agenti di orchestrazione come Docker Swarm, Kubernetes e Service Fabric eseguono periodicamente controlli di integrità inviando richieste di esecuzione di test sui microservizi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-181">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="b54b2-182">Quando un agente di orchestrazione determina che un servizio o contenitore non è integro, interrompe il routing delle richieste a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="b54b2-182">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="b54b2-183">In genere crea anche una nuova istanza di tale contenitore.</span><span class="sxs-lookup"><span data-stu-id="b54b2-183">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="b54b2-184">Ad esempio, gran parte degli agenti di orchestrazione può usare controlli di integrità per gestire le distribuzioni senza tempi di inattività.</span><span class="sxs-lookup"><span data-stu-id="b54b2-184">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="b54b2-185">Solo quando lo stato di un servizio o contenitore diventa integro, l'agente di orchestrazione avvierà il routing del traffico alle istanze del servizio o contenitore.</span><span class="sxs-lookup"><span data-stu-id="b54b2-185">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="b54b2-186">Il monitoraggio dell'integrità è particolarmente importante quando un agente di orchestrazione esegue l'aggiornamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b54b2-186">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="b54b2-187">Alcuni agenti di orchestrazione (ad esempio Azure Service Fabric) aggiornano i servizi in fasi, ad esempio aggiornano un quinto della superficie di cluster per ogni aggiornamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b54b2-187">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="b54b2-188">Il set di nodi che viene aggiornato allo stesso tempo viene considerato un *dominio di aggiornamento*.</span><span class="sxs-lookup"><span data-stu-id="b54b2-188">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="b54b2-189">Quando un dominio di aggiornamento risulta aggiornato ed è disponibile agli utenti, deve superare i controlli di integrità prima che la distribuzione passi al dominio di aggiornamento successivo.</span><span class="sxs-lookup"><span data-stu-id="b54b2-189">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="b54b2-190">Un altro aspetto dell'integrità del servizio è la segnalazione delle metriche dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-190">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="b54b2-191">Si tratta di una funzionalità avanzata del modello di integrità di alcuni agenti di orchestrazione, ad esempio Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="b54b2-191">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="b54b2-192">Le metriche sono importanti quando si usa un agente di orchestrazione perché vengono usate per bilanciare l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b54b2-192">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="b54b2-193">Le metriche possono anche essere un indicatore dell'integrità del sistema.</span><span class="sxs-lookup"><span data-stu-id="b54b2-193">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="b54b2-194">Ad esempio, un'applicazione potrebbe disporre di molti microservizi e ogni istanza potrebbe segnalare una metrica di richieste al secondo (RPS).</span><span class="sxs-lookup"><span data-stu-id="b54b2-194">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="b54b2-195">Se un servizio usa più risorse (memoria, processore e così via) di un altro servizio, l'agente di orchestrazione potrebbe spostare le istanze del servizio all'interno del cluster per tentare di mantenere uniforme l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="b54b2-195">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="b54b2-196">Si noti che Azure Service Fabric fornisce il proprio [modello di monitoraggio dell'integrità](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), che è più avanzato rispetto ai semplici controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="b54b2-196">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="b54b2-197">Monitoraggio avanzato: visualizzazione, analisi e avvisi</span><span class="sxs-lookup"><span data-stu-id="b54b2-197">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="b54b2-198">La parte finale del monitoraggio è la visualizzazione del flusso di eventi, la generazione di report sulle prestazioni del servizio e l'invio di avvisi quando vengono rilevati problemi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-198">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="b54b2-199">È possibile usare diverse soluzioni per questo aspetto del monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b54b2-199">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="b54b2-200">È possibile usare semplici applicazioni personalizzate che mostrano lo stato dei servizi, ad esempio la pagina personalizzata mostrata quando è stato illustrata la libreria [HealthChecks di ASP.NET Core](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="b54b2-200">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="b54b2-201">In alternativa, è possibile usare strumenti più avanzati come Azure Application Insights e Operations Management Suite per la generazione di avvisi in base al flusso di eventi.</span><span class="sxs-lookup"><span data-stu-id="b54b2-201">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="b54b2-202">Infine, se sono stati archiviati tutti i flussi di eventi, è possibile usare Microsoft Power BI o una soluzione di terze parti, ad esempio Kibana o Splunk, per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="b54b2-202">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b54b2-203">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b54b2-203">Additional resources</span></span>

-   <span data-ttu-id="b54b2-204">**ASP.NET Core HealthChecks** (rilascio anticipato) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="b54b2-204">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="b54b2-205">**Introduzione al monitoraggio dell'integrità di Service Fabric**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="b54b2-205">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="b54b2-206">**Azure Application Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="b54b2-206">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="b54b2-207">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="b54b2-207">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b54b2-208">[Precedente](implement-circuit-breaker-pattern.md)
>[Successivo](../secure-net-microservices-web-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b54b2-208">[Previous](implement-circuit-breaker-pattern.md)
[Next](../secure-net-microservices-web-applications/index.md)</span></span>