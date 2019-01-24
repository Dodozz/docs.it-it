---
title: Definizione di WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: ac75f5fd91f68d9403dc7b42325bf8970f0c6794
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512295"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="0aa29-102">Definizione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0aa29-102">Defining WCF Data Services</span></span>

<span data-ttu-id="0aa29-103">Questa sezione descrive come creare e configurare WCF Data Services per esporre i dati come un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span><span class="sxs-lookup"><span data-stu-id="0aa29-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="0aa29-104">Per altre informazioni sui passaggi di base necessarie per creare un servizio dati, vedere [esponendo i tuoi dati come servizio](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0aa29-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0aa29-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0aa29-105">In This Section</span></span>

 [<span data-ttu-id="0aa29-106">Configurazione del servizio dati</span><span class="sxs-lookup"><span data-stu-id="0aa29-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="0aa29-107">Descrive le opzioni di configurazione del servizio dati fornite da WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="0aa29-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="0aa29-108">Provider di servizi dati</span><span class="sxs-lookup"><span data-stu-id="0aa29-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

 <span data-ttu-id="0aa29-109">Vengono descritti i modelli di provider per l'esposizione di dati come servizio dati.</span><span class="sxs-lookup"><span data-stu-id="0aa29-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="0aa29-110">Operazioni di servizio</span><span class="sxs-lookup"><span data-stu-id="0aa29-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

 <span data-ttu-id="0aa29-111">Viene illustrato come definire le operazioni di servizio che espongono i metodi sul server.</span><span class="sxs-lookup"><span data-stu-id="0aa29-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="0aa29-112">Personalizzazione feed</span><span class="sxs-lookup"><span data-stu-id="0aa29-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)

 <span data-ttu-id="0aa29-113">Viene illustrato come creare un mapping tra le entità del modello di dati definito dal provider del servizio dati e gli elementi del feed di dati.</span><span class="sxs-lookup"><span data-stu-id="0aa29-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="0aa29-114">Intercettori</span><span class="sxs-lookup"><span data-stu-id="0aa29-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

 <span data-ttu-id="0aa29-115">Viene illustrato come definire i metodi intercettore per eseguire la logica di business personalizzata nelle richieste al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="0aa29-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="0aa29-116">Sviluppo e distribuzione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0aa29-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="0aa29-117">Viene descritto come sviluppare e distribuire un servizio dati tramite Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0aa29-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="0aa29-118">Protezione di WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0aa29-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)

 <span data-ttu-id="0aa29-119">Vengono descritte l'autenticazione e l'autorizzazione per il servizio dati e altre considerazioni sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0aa29-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="0aa29-120">Hosting del servizio dati</span><span class="sxs-lookup"><span data-stu-id="0aa29-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="0aa29-121">Viene descritto come selezionare un host per il servizio dati.</span><span class="sxs-lookup"><span data-stu-id="0aa29-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="0aa29-122">Controllo delle versioni del servizio dati</span><span class="sxs-lookup"><span data-stu-id="0aa29-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="0aa29-123">Viene descritto come lavorare con diverse versioni di OData.</span><span class="sxs-lookup"><span data-stu-id="0aa29-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="0aa29-124">Dettagli di implementazione del protocollo WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0aa29-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="0aa29-125">Descrive le funzionalità facoltative del protocollo OData che non sono attualmente implementate da WCF Data Services.</span><span class="sxs-lookup"><span data-stu-id="0aa29-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="0aa29-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa29-126">See also</span></span>

- [<span data-ttu-id="0aa29-127">Libreria client WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0aa29-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="0aa29-128">Accesso alle risorse di un servizio dati</span><span class="sxs-lookup"><span data-stu-id="0aa29-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="0aa29-129">Introduzione</span><span class="sxs-lookup"><span data-stu-id="0aa29-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
