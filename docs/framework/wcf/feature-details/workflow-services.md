---
title: Servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: e7295041fe4b17e7e2b1560704badf20992d4b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929701"
---
# <a name="workflow-services"></a><span data-ttu-id="f4c97-102">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c97-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="f4c97-103">consente di descrivere in modo completo e dichiarativo un servizio basato sul flusso di lavoro in XAML.</span><span class="sxs-lookup"><span data-stu-id="f4c97-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="f4c97-104">È possibile definire un flusso di lavoro che implementa il servizio e descrivere l'endpoint esposto dal servizio, il tutto in XAML.</span><span class="sxs-lookup"><span data-stu-id="f4c97-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="f4c97-105">Negli argomenti di questa sezione viene descritto in dettaglio il modello di programmazione che supporta la scrittura dei servizi in modo dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="f4c97-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4c97-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f4c97-106">In This Section</span></span>  
 [<span data-ttu-id="f4c97-107">Panoramica dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c97-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="f4c97-108">Descrive i componenti coinvolti nella creazione e nell'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f4c97-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="f4c97-109">Attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="f4c97-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="f4c97-110">Descrive le attività che consentono ai flussi di lavoro di inviare e ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="f4c97-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="f4c97-111">Procedura: Creare un servizio del flusso di lavoro con attività di messaggistica</span><span class="sxs-lookup"><span data-stu-id="f4c97-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="f4c97-112">Descrive come utilizzare le attività di messaggistica per creare un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f4c97-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="f4c97-113">Procedura: Accedere a un servizio da un'applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c97-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="f4c97-114">Descrive come chiamare un servizio da un'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f4c97-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="f4c97-115">Correlazione</span><span class="sxs-lookup"><span data-stu-id="f4c97-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="f4c97-116">Descrive come la correlazione esegue il mapping di un messaggio a un altro e a un'istanza.</span><span class="sxs-lookup"><span data-stu-id="f4c97-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="f4c97-117">Elaborazione di messaggi in ordine non corretto</span><span class="sxs-lookup"><span data-stu-id="f4c97-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="f4c97-118">Descrive la configurazione di un servizio per accettare messaggi non ordinati.</span><span class="sxs-lookup"><span data-stu-id="f4c97-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="f4c97-119">Sviluppo del servizio del flusso di lavoro con priorità al contratto ("contract-first")</span><span class="sxs-lookup"><span data-stu-id="f4c97-119">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="f4c97-120">Viene descritta la creazione di un servizio di flusso di lavoro basato su un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="f4c97-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="f4c97-121">Procedura: Creare un servizio del flusso di lavoro che utilizza un contratto di servizio esistente</span><span class="sxs-lookup"><span data-stu-id="f4c97-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="f4c97-122">Fornisce un esempio dettagliato di creazione di un servizio di flusso di lavoro tramite un contratto di servizio esistente.</span><span class="sxs-lookup"><span data-stu-id="f4c97-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="f4c97-123">Panoramica dell'hosting dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c97-123">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="f4c97-124">Descrive i vari aspetti legati all'hosting di un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f4c97-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="f4c97-125">Uso di contratti nel flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f4c97-125">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="f4c97-126">Descrive i vari tipi di contratti e l'inferenza del contratto.</span><span class="sxs-lookup"><span data-stu-id="f4c97-126">Describes the different types of contracts and contract inference.</span></span>
