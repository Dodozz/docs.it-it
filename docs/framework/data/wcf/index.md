---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: e203e872ac0dce10fa7119388bae2472cb7e6b44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588239"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="d9a94-102">WCF Data Services 4.5</span><span class="sxs-lookup"><span data-stu-id="d9a94-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="d9a94-103">WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente di .NET Framework che consente di creare servizi che usano il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre e utilizzare dati sul Web o su intranet tramite la semantica di [ (REST) Representational state transfer](https://go.microsoft.com/fwlink/?LinkId=113919).</span><span class="sxs-lookup"><span data-stu-id="d9a94-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="d9a94-104">In OData i dati vengono esposti come risorse indirizzabili tramite URI.</span><span class="sxs-lookup"><span data-stu-id="d9a94-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="d9a94-105">Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE.</span><span class="sxs-lookup"><span data-stu-id="d9a94-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="d9a94-106">OData utilizza le convenzioni entità-relazione del [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) per esporre risorse come set di entità correlate da associazioni.</span><span class="sxs-lookup"><span data-stu-id="d9a94-106">OData uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="d9a94-107">WCF Data Services utilizza il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d9a94-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="d9a94-108">In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporta OData.</span><span class="sxs-lookup"><span data-stu-id="d9a94-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="d9a94-109">OData consente di richiedere e scrivere dati nelle risorse utilizzando formati di trasferimento noti: Atom, un set di standard per lo scambio e l'aggiornamento dei dati come XML e JavaScript Object Notation (JSON), un formato di scambio dei dati basata su testo ampiamente usato nelle applicazioni AJAX.</span><span class="sxs-lookup"><span data-stu-id="d9a94-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>

<span data-ttu-id="d9a94-110">WCF Data Services può esporre dati provengono da varie origini come feed OData.</span><span class="sxs-lookup"><span data-stu-id="d9a94-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="d9a94-111">Strumenti di Visual Studio semplificano la creazione di un servizio basato su OData usando un modello di dati ADO.NET Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d9a94-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="d9a94-112">È anche possibile creare feed OData basate su classi common language runtime (CLR) e i dati anche con associazione tardiva o senza tipo.</span><span class="sxs-lookup"><span data-stu-id="d9a94-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="d9a94-113">WCF Data Services include inoltre un set di librerie client, una per le applicazioni client di .NET Framework generale e un'altra in modo specifico per le applicazioni basate su Silverlight.</span><span class="sxs-lookup"><span data-stu-id="d9a94-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="d9a94-114">Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali .NET Framework e Silverlight.</span><span class="sxs-lookup"><span data-stu-id="d9a94-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="d9a94-115">Da dove iniziare</span><span class="sxs-lookup"><span data-stu-id="d9a94-115">Where Should I Start?</span></span>

<span data-ttu-id="d9a94-116">In base ai tuoi interessi, prendere in considerazione Introduzione a WCF Data Services in uno degli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="d9a94-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="d9a94-117">Passare subito a...</span><span class="sxs-lookup"><span data-stu-id="d9a94-117">I want to jump right in...</span></span>

-   [<span data-ttu-id="d9a94-118">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="d9a94-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-119">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d9a94-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-120">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="d9a94-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="d9a94-121">Guida rapida di Silverlight per lo sviluppo per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d9a94-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="d9a94-122">Visualizzi un codice...</span><span class="sxs-lookup"><span data-stu-id="d9a94-122">Just show me some code...</span></span>

-   [<span data-ttu-id="d9a94-123">Guida rapida</span><span class="sxs-lookup"><span data-stu-id="d9a94-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-124">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="d9a94-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-125">Procedura: Associare dati a elementi Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="d9a94-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="d9a94-126">Si vuole conoscere ulteriori informazioni su OData...</span><span class="sxs-lookup"><span data-stu-id="d9a94-126">I want to know more about OData...</span></span>

 -   [<span data-ttu-id="d9a94-127">White paper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="d9a94-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="d9a94-128">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="d9a94-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [<span data-ttu-id="d9a94-129">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="d9a94-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [<span data-ttu-id="d9a94-130">OData: Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="d9a94-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="d9a94-131">Voglio vedere alcuni video...</span><span class="sxs-lookup"><span data-stu-id="d9a94-131">I want to watch some videos...</span></span>

-   [<span data-ttu-id="d9a94-132">Guida per i principianti di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [<span data-ttu-id="d9a94-133">Video per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [<span data-ttu-id="d9a94-134">OData: Sito Web degli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="d9a94-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="d9a94-135">Desidera vedere esempi end-to-end...</span><span class="sxs-lookup"><span data-stu-id="d9a94-135">I want to see end-to-end samples...</span></span>

-   [<span data-ttu-id="d9a94-136">Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="d9a94-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [<span data-ttu-id="d9a94-137">Altri esempi di WCF Data Services nella raccolta di esempi MSDN</span><span class="sxs-lookup"><span data-stu-id="d9a94-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [<span data-ttu-id="d9a94-138">OData: SDK</span><span class="sxs-lookup"><span data-stu-id="d9a94-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="d9a94-139">Integrazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9a94-139">How does it integrate with Visual Studio?</span></span>

-   [<span data-ttu-id="d9a94-140">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="d9a94-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-141">Creazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="d9a94-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [<span data-ttu-id="d9a94-142">Provider di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d9a94-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="d9a94-143">Attività possibili</span><span class="sxs-lookup"><span data-stu-id="d9a94-143">What can I do with it?</span></span>

-   [<span data-ttu-id="d9a94-144">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d9a94-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [<span data-ttu-id="d9a94-145">White paper: Introduzione a OData</span><span class="sxs-lookup"><span data-stu-id="d9a94-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="d9a94-146">Scenari di applicazione</span><span class="sxs-lookup"><span data-stu-id="d9a94-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

<span data-ttu-id="d9a94-147">Desidero utilizzare Silverlight...</span><span class="sxs-lookup"><span data-stu-id="d9a94-147">I want to use Silverlight...</span></span>

-   [<span data-ttu-id="d9a94-148">Guida rapida di Silverlight</span><span class="sxs-lookup"><span data-stu-id="d9a94-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="d9a94-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="d9a94-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [<span data-ttu-id="d9a94-150">Introduzione a Silverlight</span><span class="sxs-lookup"><span data-stu-id="d9a94-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="d9a94-151">Desidero utilizzare LINQ...</span><span class="sxs-lookup"><span data-stu-id="d9a94-151">I want to use LINQ...</span></span>

-   [<span data-ttu-id="d9a94-152">Esecuzione di query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="d9a94-152">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-153">Considerazioni su LINQ</span><span class="sxs-lookup"><span data-stu-id="d9a94-153">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [<span data-ttu-id="d9a94-154">Procedura: Eseguire query sul servizio dati</span><span class="sxs-lookup"><span data-stu-id="d9a94-154">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="d9a94-155">Devo ancora alcune informazioni...</span><span class="sxs-lookup"><span data-stu-id="d9a94-155">I still need some more information...</span></span>

-   [<span data-ttu-id="d9a94-156">Blog del team di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-156">WCF Data Services Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=150511)

-   [<span data-ttu-id="d9a94-157">Risorse</span><span class="sxs-lookup"><span data-stu-id="d9a94-157">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [<span data-ttu-id="d9a94-158">Centro per sviluppatori di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [<span data-ttu-id="d9a94-159">Sito Web Open Data Protocol</span><span class="sxs-lookup"><span data-stu-id="d9a94-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="d9a94-160">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d9a94-160">In This Section</span></span>

 [<span data-ttu-id="d9a94-161">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d9a94-161">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 <span data-ttu-id="d9a94-162">Fornisce una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="d9a94-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

 [<span data-ttu-id="d9a94-163">Novità in WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-163">What's New in WCF Data Services</span></span>](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 <span data-ttu-id="d9a94-164">Descrive le nuove funzionalità di WCF Data Services e il supporto per nuove funzionalità di OData.</span><span class="sxs-lookup"><span data-stu-id="d9a94-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

 [<span data-ttu-id="d9a94-165">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d9a94-165">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 <span data-ttu-id="d9a94-166">Viene descritto come esporre e utilizzare feed OData tramite WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="d9a94-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

 [<span data-ttu-id="d9a94-167">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-167">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 <span data-ttu-id="d9a94-168">Viene descritto come creare e configurare un servizio dati che espone feed OData.</span><span class="sxs-lookup"><span data-stu-id="d9a94-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

 [<span data-ttu-id="d9a94-169">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d9a94-169">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 <span data-ttu-id="d9a94-170">Viene descritto come usare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d9a94-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9a94-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9a94-171">See also</span></span>

- [<span data-ttu-id="d9a94-172">REST (Representational State Transfer)</span><span class="sxs-lookup"><span data-stu-id="d9a94-172">Representational State Transfer (REST)</span></span>](https://go.microsoft.com/fwlink/?LinkId=113919)
