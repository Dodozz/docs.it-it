---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 0b782b5ac0527b5acb3ebf0bf11c117563042495
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61595779"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="e1fd4-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="e1fd4-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="e1fd4-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="e1fd4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1fd4-104">Id</span><span class="sxs-lookup"><span data-stu-id="e1fd4-104">ID</span></span>|<span data-ttu-id="e1fd4-105">303</span><span class="sxs-lookup"><span data-stu-id="e1fd4-105">303</span></span>|  
|<span data-ttu-id="e1fd4-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e1fd4-106">Keywords</span></span>|<span data-ttu-id="e1fd4-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="e1fd4-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="e1fd4-108">Livello</span><span class="sxs-lookup"><span data-stu-id="e1fd4-108">Level</span></span>|<span data-ttu-id="e1fd4-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="e1fd4-109">Information</span></span>|  
|<span data-ttu-id="e1fd4-110">Canale</span><span class="sxs-lookup"><span data-stu-id="e1fd4-110">Channel</span></span>|<span data-ttu-id="e1fd4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e1fd4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1fd4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1fd4-112">Description</span></span>  
 <span data-ttu-id="e1fd4-113">Questo evento viene generato dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-113">This event is emitted from user code.</span></span> <span data-ttu-id="e1fd4-114">Gli sviluppatori possono generare questo evento nel caso in cui si verifichi un evento informativo definito dal cliente nel servizio.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="e1fd4-115">A tale scopo utilizzare le interfacce API <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="e1fd4-116">È inoltre disponibile un esempio WCF che esegue il wrapping dell'interfaccia API e illustra come generare correttamente questo evento.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1fd4-117">Messaggio</span><span class="sxs-lookup"><span data-stu-id="e1fd4-117">Message</span></span>  
 <span data-ttu-id="e1fd4-118">Nome:'%1', riferimento:'%2', payload:%3</span><span class="sxs-lookup"><span data-stu-id="e1fd4-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1fd4-119">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e1fd4-119">Details</span></span>  
  
|<span data-ttu-id="e1fd4-120">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="e1fd4-120">Data Item Name</span></span>|<span data-ttu-id="e1fd4-121">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="e1fd4-121">Data Item Type</span></span>|<span data-ttu-id="e1fd4-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1fd4-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1fd4-123">Nome</span><span class="sxs-lookup"><span data-stu-id="e1fd4-123">Name</span></span>|`xs:string`|<span data-ttu-id="e1fd4-124">Nome dell'evento definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="e1fd4-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="e1fd4-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e1fd4-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="e1fd4-126">Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e1fd4-127">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e1fd4-128">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e1fd4-129">Payload</span><span class="sxs-lookup"><span data-stu-id="e1fd4-129">Payload</span></span>|`xs:string`|<span data-ttu-id="e1fd4-130">Payload dell'evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e1fd4-130">The user-defined payload of the event.</span></span>|
