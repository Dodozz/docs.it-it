---
title: '&lt;activityStateQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: bfd19e00e79a95eb717ca9131e92b5ff5c600d5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511982"
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="b6825-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="b6825-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="b6825-103">Rappresenta una raccolta di query usate per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b6825-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b6825-104">Ad esempio, è possibile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b6825-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b6825-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="b6825-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="b6825-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="b6825-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="b6825-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b6825-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b6825-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6825-108">\<system.serviceModel></span></span>  
<span data-ttu-id="b6825-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b6825-109">\<tracking></span></span>  
<span data-ttu-id="b6825-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b6825-110">\<trackingProfile></span></span>  
<span data-ttu-id="b6825-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="b6825-111">\<workflow></span></span>  
<span data-ttu-id="b6825-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b6825-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6825-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6825-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6825-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b6825-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b6825-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b6825-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6825-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="b6825-116">Attributes</span></span>  
 <span data-ttu-id="b6825-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b6825-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6825-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b6825-118">Child Elements</span></span>  
  
|<span data-ttu-id="b6825-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6825-119">Element</span></span>|<span data-ttu-id="b6825-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6825-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6825-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b6825-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="b6825-122">Query usata per rilevare la gestione degli errori che si verificano all'interno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="b6825-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b6825-123">Questo evento si verifica ogni volta che un FaultHandler elabora un errore.</span><span class="sxs-lookup"><span data-stu-id="b6825-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6825-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b6825-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b6825-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6825-125">Element</span></span>|<span data-ttu-id="b6825-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6825-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6825-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b6825-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b6825-128">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="b6825-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6825-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6825-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b6825-130">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b6825-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b6825-131">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="b6825-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
