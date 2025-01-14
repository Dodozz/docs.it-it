---
title: Introduzione a Docker
description: Questo articolo fornisce un'introduzione e una panoramica di Docker nel contesto di un'applicazione .NET Core.
ms.date: 03/20/2019
ms.custom: mvc, seodec18
ms.openlocfilehash: d0bce09d7acdcf474fbb8849c8fc82dae4a69598
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753304"
---
# <a name="introduction-to-net-and-docker"></a>Introduzione a .NET e Docker

.NET Core può essere eseguito facilmente in un contenitore Docker. I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host, condividendo solo il kernel e usando le risorse assegnate all'applicazione. Se non si ha familiarità con Docker, è consigliabile leggere la [documentazione introduttiva](https://docs.docker.com/engine/docker-overview/) a Docker.

Per altre informazioni su come installare Docker, vedere la pagina di download per [Docker Desktop: Community Edition](https://www.docker.com/products/docker-desktop).

## <a name="docker-basics"></a>Concetti di base su Docker

Questa sezione illustra alcuni concetti che è necessario conoscere. Il client di Docker ha un programma di interfaccia della riga di comando che consente di gestire immagini e contenitori. Come già suggerito, è consigliabile dedicare del tempo alla lettura della documentazione [introduttiva a Docker](https://docs.docker.com/engine/docker-overview/). 

### <a name="images"></a>Immagini

Un'immagine è una raccolta ordinata di modifiche del file system che formano la base di un contenitore. L'immagine non ha uno stato ed è di sola lettura. Nella maggior parte dei casi, un'immagine è basata su un'altra immagine, ma con alcune personalizzazioni. Ad esempio, quando si crea una nuova immagine per un'applicazione, si sceglie in genere di basarla su un'immagine esistente che contiene già il runtime di .NET Core.

Poiché i contenitori vengono creati a partire dalle immagini, queste hanno un set di parametri di esecuzione (ad esempio un file eseguibile di avvio) che vengono impostati all'avvio del contenitore.

### <a name="containers"></a>Contenitori

Un contenitore è un'istanza eseguibile di un'immagine. Quando si compila un'immagine, si distribuisce l'applicazione con le relative dipendenze. È quindi possibile creare istanze per più contenitori, isolati l'uno dall'altro. Ogni istanza di contenitore ha un proprio file system, una memoria e un'interfaccia di rete.

### <a name="registries"></a>Registri

I registri contenitori sono una raccolta di repository di immagini. È possibile basare le immagini su un'immagine di registro e anche creare contenitori direttamente da un'immagine in un registro. La [relazione tra contenitori, immagini e registri Docker](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) è un concetto importante per l'[architettura e la compilazione di applicazioni o microservizi inclusi in contenitori](../../standard/microservices-architecture/architect-microservice-container-applications/index.md). Questo approccio riduce considerevolmente il tempo che intercorre tra lo sviluppo e la distribuzione.

Docker ha un registro pubblico ospitato nell'[hub Docker](https://hub.docker.com/) che è possibile usare. Nell'hub Docker sono elencate le [immagini correlate a .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/). 

La fonte ufficiale delle immagini di contenitore fornite da Microsoft è il Registro Container. Questo registro si basa sulla rete CDN di Azure per fornire immagini replicate a livello globale. Il Registro Container di Microsoft, tuttavia, non dispone di un sito Web pubblico e il metodo principale per ottenere informazioni sulle immagini di contenitore fornite da Microsoft è quello di visitare le [pagine corrispondenti nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).

### <a name="dockerfile"></a>Dockerfile

Un **Dockerfile** è un file in cui è definito un set di istruzioni per la creazione di un'immagine. Ogni istruzione nel **Dockerfile** crea un livello nell'immagine. Nella maggior parte dei casi, quando si compila una nuova immagine vengono ricompilati solo i livelli che sono stati modificati. Il **Dockerfile** può essere distribuito ad altri e consente di creare una nuova immagine esattamente come l'originale. In questo modo è possibile distribuire le *istruzioni* su come creare l'immagine, ma il metodo principale per distribuire un'immagine consiste nel pubblicarla in un registro.

## <a name="net-core-images"></a>Immagini di .NET Core

Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare. 

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

## <a name="azure-services"></a>Servizi di Azure

Diversi servizi di Azure consentono l'uso di contenitori. È possibile creare un'immagine Docker per un'applicazione e distribuirla in uno dei servizi seguenti:

* [Servizio Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/)\
Consente di ridimensionare e orchestrare contenitori Linux usando Kubernetes.

* [Servizio app di Azure](https://azure.microsoft.com/services/app-service/containers/)\
Consente di distribuire API o app Web usando contenitori Linux in un ambiente PaaS.

* [Istanze di Azure Container](https://azure.microsoft.com/services/container-instances/)\
Consentono di ospitare il contenitore nel cloud senza servizi di gestione di livello superiore.

* [Azure Batch](https://azure.microsoft.com/services/batch/)\
Consente di eseguire processi di calcolo ripetitivi usando contenitori.

* [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)\
Consente di trasferire in modalità lift-and-shift e modernizzare le applicazioni .NET trasformandole in microservizi tramite contenitori di Windows Server.

* [Registro Azure Container](https://azure.microsoft.com/services/container-registry/)\
Consente di archiviare e gestire immagini dei contenitori per tutti i tipi di distribuzioni di Azure.

## <a name="next-steps"></a>Passaggi successivi

* [Vedere le informazioni su come distribuire un'applicazione .NET Core in un contenitore.](build-docker-netcore-container.md)
* [Vedere le informazioni su come distribuire un'applicazione ASP.NET Core in un contenitore.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
* [Provare l'esercitazione sulla creazione di microservizi ASP.NET Core.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [Vedere informazioni sugli strumenti per contenitori in Visual Studio](/visualstudio/containers/overview)
