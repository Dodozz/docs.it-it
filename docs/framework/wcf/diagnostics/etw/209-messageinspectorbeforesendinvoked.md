---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 24184c24b9affdf3a56d7968c02cf5354d690749
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781881"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="43f07-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="43f07-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="43f07-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="43f07-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="43f07-104">Id</span><span class="sxs-lookup"><span data-stu-id="43f07-104">ID</span></span>|<span data-ttu-id="43f07-105">209</span><span class="sxs-lookup"><span data-stu-id="43f07-105">209</span></span>|  
|<span data-ttu-id="43f07-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="43f07-106">Keywords</span></span>|<span data-ttu-id="43f07-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="43f07-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="43f07-108">Livello</span><span class="sxs-lookup"><span data-stu-id="43f07-108">Level</span></span>|<span data-ttu-id="43f07-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="43f07-109">Information</span></span>|  
|<span data-ttu-id="43f07-110">Canale</span><span class="sxs-lookup"><span data-stu-id="43f07-110">Channel</span></span>|<span data-ttu-id="43f07-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="43f07-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="43f07-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43f07-112">Description</span></span>  
 <span data-ttu-id="43f07-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeSend` su un controllo dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="43f07-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="43f07-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="43f07-114">Message</span></span>  
 <span data-ttu-id="43f07-115">'BeforeSendRequest' richiamato dal dispatcher in un elemento MessageInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="43f07-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="43f07-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="43f07-116">Details</span></span>  
  
|<span data-ttu-id="43f07-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="43f07-117">Data Item Name</span></span>|<span data-ttu-id="43f07-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="43f07-118">Data Item Type</span></span>|<span data-ttu-id="43f07-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="43f07-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="43f07-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="43f07-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="43f07-121">Nome completo CLR del tipo dell'elemento `MessageInspector` richiamato.</span><span class="sxs-lookup"><span data-stu-id="43f07-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="43f07-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="43f07-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="43f07-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="43f07-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="43f07-124">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="43f07-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="43f07-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="43f07-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="43f07-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="43f07-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="43f07-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="43f07-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
