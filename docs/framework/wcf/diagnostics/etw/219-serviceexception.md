---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: eb4289c0346c9e1d9481347d69db8c5f007e4325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781732"
---
# <a name="219---serviceexception"></a><span data-ttu-id="37e33-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="37e33-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="37e33-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="37e33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37e33-104">Id</span><span class="sxs-lookup"><span data-stu-id="37e33-104">ID</span></span>|<span data-ttu-id="37e33-105">219</span><span class="sxs-lookup"><span data-stu-id="37e33-105">219</span></span>|  
|<span data-ttu-id="37e33-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="37e33-106">Keywords</span></span>|<span data-ttu-id="37e33-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37e33-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="37e33-108">Livello</span><span class="sxs-lookup"><span data-stu-id="37e33-108">Level</span></span>|<span data-ttu-id="37e33-109">Error</span><span class="sxs-lookup"><span data-stu-id="37e33-109">Error</span></span>|  
|<span data-ttu-id="37e33-110">Canale</span><span class="sxs-lookup"><span data-stu-id="37e33-110">Channel</span></span>|<span data-ttu-id="37e33-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="37e33-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="37e33-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37e33-112">Description</span></span>  
 <span data-ttu-id="37e33-113">Questo evento viene generato quando un servizio WCF incontra un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="37e33-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="37e33-114">Include eccezioni non gestite durante l'attivazione, durante l'elaborazione dei messaggi e nel codice utente.</span><span class="sxs-lookup"><span data-stu-id="37e33-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="37e33-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="37e33-115">Message</span></span>  
 <span data-ttu-id="37e33-116">Riscontrata un'eccezione non gestita di tipo '%2' durante l'elaborazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="37e33-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="37e33-117">ToString completo dell'eccezione: %1.</span><span class="sxs-lookup"><span data-stu-id="37e33-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="37e33-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37e33-118">Details</span></span>  
  
|<span data-ttu-id="37e33-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="37e33-119">Data Item Name</span></span>|<span data-ttu-id="37e33-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="37e33-120">Data Item Type</span></span>|<span data-ttu-id="37e33-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37e33-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="37e33-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="37e33-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="37e33-123">Risultato della chiamata di `ToString`() all'eccezione CLR.</span><span class="sxs-lookup"><span data-stu-id="37e33-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="37e33-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="37e33-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="37e33-125">Nome completo CLR del tipo di eccezione.</span><span class="sxs-lookup"><span data-stu-id="37e33-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="37e33-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="37e33-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="37e33-127">Per i servizi ospitati su Web, questo campo identifica in modo univoco il servizio nella gerarchia Web.</span><span class="sxs-lookup"><span data-stu-id="37e33-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="37e33-128">Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="37e33-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="37e33-129">Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="37e33-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="37e33-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="37e33-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="37e33-131">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="37e33-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
