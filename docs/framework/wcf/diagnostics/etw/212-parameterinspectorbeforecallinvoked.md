---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.date: 03/30/2017
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
ms.openlocfilehash: 02d4a4ed1e96983e132a1943dd39f9f885e5596a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781849"
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="0db19-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="0db19-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="0db19-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0db19-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0db19-104">Id</span><span class="sxs-lookup"><span data-stu-id="0db19-104">ID</span></span>|<span data-ttu-id="0db19-105">212</span><span class="sxs-lookup"><span data-stu-id="0db19-105">212</span></span>|  
|<span data-ttu-id="0db19-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="0db19-106">Keywords</span></span>|<span data-ttu-id="0db19-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0db19-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0db19-108">Livello</span><span class="sxs-lookup"><span data-stu-id="0db19-108">Level</span></span>|<span data-ttu-id="0db19-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="0db19-109">Information</span></span>|  
|<span data-ttu-id="0db19-110">Canale</span><span class="sxs-lookup"><span data-stu-id="0db19-110">Channel</span></span>|<span data-ttu-id="0db19-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0db19-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0db19-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db19-112">Description</span></span>  
 <span data-ttu-id="0db19-113">Questo evento viene generato dopo che il modello di servizi ha richiamato il metodo `BeforeCall` su un `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="0db19-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0db19-114">Messaggio</span><span class="sxs-lookup"><span data-stu-id="0db19-114">Message</span></span>  
 <span data-ttu-id="0db19-115">Il dispatcher ha richiamato 'BeforeCall' in un ParameterInspector di tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="0db19-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0db19-116">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0db19-116">Details</span></span>  
  
|<span data-ttu-id="0db19-117">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="0db19-117">Data Item Name</span></span>|<span data-ttu-id="0db19-118">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="0db19-118">Data Item Type</span></span>|<span data-ttu-id="0db19-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0db19-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0db19-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0db19-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0db19-121">Nome completo CLR del tipo di controllo richiamato.</span><span class="sxs-lookup"><span data-stu-id="0db19-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="0db19-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0db19-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0db19-123">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="0db19-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0db19-124">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="0db19-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0db19-125">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0db19-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0db19-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0db19-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0db19-127">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0db19-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
