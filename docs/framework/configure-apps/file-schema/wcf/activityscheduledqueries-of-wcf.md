---
title: '&lt;activityScheduledQueries&gt; di WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 35bcb0dc0c33d30eee566869579edb32f131f495
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452696"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="d7bd3-102">&lt;activityScheduledQueries&gt; di WCF</span><span class="sxs-lookup"><span data-stu-id="d7bd3-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="d7bd3-103">Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d7bd3-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d7bd3-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d7bd3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d7bd3-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d7bd3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d7bd3-107">\<rilevamento ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-107">\<tracking></span></span>  
<span data-ttu-id="d7bd3-108">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-108">\<profiles></span></span>  
<span data-ttu-id="d7bd3-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d7bd3-109">\<trackingProfile></span></span>  
<span data-ttu-id="d7bd3-110">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-110">\<workflow></span></span>  
<span data-ttu-id="d7bd3-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7bd3-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7bd3-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d7bd3-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d7bd3-113">Attributes and elements</span></span>  

<span data-ttu-id="d7bd3-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d7bd3-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="d7bd3-115">Attributes</span></span>  

<span data-ttu-id="d7bd3-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d7bd3-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d7bd3-117">Child elements</span></span>  
  
|<span data-ttu-id="d7bd3-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7bd3-118">Element</span></span>|<span data-ttu-id="d7bd3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7bd3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7bd3-120">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="d7bd3-121">Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d7bd3-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d7bd3-122">Parent elements</span></span>  
  
|<span data-ttu-id="d7bd3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d7bd3-123">Element</span></span>|<span data-ttu-id="d7bd3-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7bd3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d7bd3-125">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="d7bd3-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d7bd3-126">Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="d7bd3-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7bd3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7bd3-127">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d7bd3-128">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="d7bd3-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d7bd3-129">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d7bd3-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
