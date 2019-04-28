---
title: <workflowInstanceQuery> di WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 726d4db3bad9f57663790e2bb4e081faba28f1ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672965"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="4d088-102">\<workflowInstanceQuery > di WCF</span><span class="sxs-lookup"><span data-stu-id="4d088-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="4d088-103">Rappresenta una query che rileva modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="4d088-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="4d088-104">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4d088-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4d088-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4d088-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4d088-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4d088-106">\<tracking></span></span>  
<span data-ttu-id="4d088-107">\<i profili ></span><span class="sxs-lookup"><span data-stu-id="4d088-107">\<profiles></span></span>  
<span data-ttu-id="4d088-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4d088-108">\<trackingProfile></span></span>  
<span data-ttu-id="4d088-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="4d088-109">\<workflow></span></span>  
<span data-ttu-id="4d088-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="4d088-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="4d088-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="4d088-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d088-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d088-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d088-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d088-113">Attributes and elements</span></span>  

<span data-ttu-id="4d088-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d088-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d088-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d088-115">Attributes</span></span>  

<span data-ttu-id="4d088-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d088-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4d088-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d088-117">Child elements</span></span>  
  
|<span data-ttu-id="4d088-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d088-118">Element</span></span>|<span data-ttu-id="4d088-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d088-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d088-120">\<states></span><span class="sxs-lookup"><span data-stu-id="4d088-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="4d088-121">Raccolta di stati sottoscritti dell'istanza del flusso di lavoro rilevata che si riferiscono alla fase di creazione dei record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="4d088-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d088-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d088-122">Parent elements</span></span>  
  
|<span data-ttu-id="4d088-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d088-123">Element</span></span>|<span data-ttu-id="4d088-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d088-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d088-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="4d088-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="4d088-126">Rappresenta una raccolta di elementi di configurazione che rilevano modifiche del ciclo di vita dell'istanza del flusso di lavoro, come l'avvio o il completamento di un evento.</span><span class="sxs-lookup"><span data-stu-id="4d088-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d088-127">Note</span><span class="sxs-lookup"><span data-stu-id="4d088-127">Remarks</span></span>  

<span data-ttu-id="4d088-128">L'oggetto <xref:System.Activities.Tracking.WorkflowInstanceQuery> viene usato per sottoscrivere gli oggetti <xref:System.Activities.Tracking.TrackingRecord> seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d088-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="4d088-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d088-129">Example</span></span>  

<span data-ttu-id="4d088-130">La configurazione seguente sottoscrive i record di rilevamento a livello di istanza del flusso di lavoro per lo stato dell'istanza `Started` usando questa query.</span><span class="sxs-lookup"><span data-stu-id="4d088-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="4d088-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d088-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4d088-132">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="4d088-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4d088-133">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4d088-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
