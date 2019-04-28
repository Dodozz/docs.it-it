---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924189"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="f3c4a-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="f3c4a-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="f3c4a-103">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f3c4a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3c4a-104">Id</span><span class="sxs-lookup"><span data-stu-id="f3c4a-104">ID</span></span>|<span data-ttu-id="f3c4a-105">1041</span><span class="sxs-lookup"><span data-stu-id="f3c4a-105">1041</span></span>|  
|<span data-ttu-id="f3c4a-106">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f3c4a-106">Keywords</span></span>|<span data-ttu-id="f3c4a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f3c4a-107">WFRuntime</span></span>|  
|<span data-ttu-id="f3c4a-108">Livello</span><span class="sxs-lookup"><span data-stu-id="f3c4a-108">Level</span></span>|<span data-ttu-id="f3c4a-109">Informazioni</span><span class="sxs-lookup"><span data-stu-id="f3c4a-109">Information</span></span>|  
|<span data-ttu-id="f3c4a-110">Canale</span><span class="sxs-lookup"><span data-stu-id="f3c4a-110">Channel</span></span>|<span data-ttu-id="f3c4a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f3c4a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f3c4a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3c4a-112">Description</span></span>  
 <span data-ttu-id="f3c4a-113">Indica che un'applicazione flusso di lavoro è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="f3c4a-114">L'applicazione flusso di lavoro verrà resa inattiva o persistente.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f3c4a-115">Messaggio</span><span class="sxs-lookup"><span data-stu-id="f3c4a-115">Message</span></span>  
 <span data-ttu-id="f3c4a-116">Workflowapplication con Id: '%1' è inattiva e persistente.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="f3c4a-117">Le seguenti azioni vengono intraprese: %2.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f3c4a-118">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f3c4a-118">Details</span></span>  
  
|<span data-ttu-id="f3c4a-119">Nome elemento dati</span><span class="sxs-lookup"><span data-stu-id="f3c4a-119">Data Item Name</span></span>|<span data-ttu-id="f3c4a-120">Tipo elemento dati</span><span class="sxs-lookup"><span data-stu-id="f3c4a-120">Data Item Type</span></span>|<span data-ttu-id="f3c4a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3c4a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f3c4a-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="f3c4a-122">WorkflowApplicationId</span></span>|<span data-ttu-id="f3c4a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3c4a-123">xs:string</span></span>|<span data-ttu-id="f3c4a-124">ID applicazione flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="f3c4a-124">The workflow application id</span></span>|  
|<span data-ttu-id="f3c4a-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="f3c4a-125">ActionTaken</span></span>|<span data-ttu-id="f3c4a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3c4a-126">xs:string</span></span>|<span data-ttu-id="f3c4a-127">L'azione che verrà intrapresa sull'applicazione flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="f3c4a-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f3c4a-128">AppDomain</span></span>|<span data-ttu-id="f3c4a-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3c4a-129">xs:string</span></span>|<span data-ttu-id="f3c4a-130">Stringa restituita da AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f3c4a-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
