---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 757bbe500ec3edccef465b7ff23b2c974e4a5011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598841"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="54b1e-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="54b1e-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="54b1e-103">Rappresenta una raccolta di query usate per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="54b1e-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="54b1e-104">La query è necessaria affinché un partecipante del rilevamento sottoscriva i record di rilevamento personalizzati.</span><span class="sxs-lookup"><span data-stu-id="54b1e-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="54b1e-105">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="54b1e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="54b1e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="54b1e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="54b1e-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="54b1e-107">\<tracking></span></span>  
<span data-ttu-id="54b1e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="54b1e-108">\<trackingProfile></span></span>  
<span data-ttu-id="54b1e-109">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="54b1e-109">\<workflow></span></span>  
<span data-ttu-id="54b1e-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="54b1e-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54b1e-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54b1e-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54b1e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="54b1e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="54b1e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="54b1e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54b1e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="54b1e-114">Attributes</span></span>  
 <span data-ttu-id="54b1e-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="54b1e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="54b1e-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="54b1e-116">Child Elements</span></span>  
  
|<span data-ttu-id="54b1e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="54b1e-117">Element</span></span>|<span data-ttu-id="54b1e-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54b1e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54b1e-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="54b1e-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="54b1e-120">Query usata per rilevare gli eventi definiti nelle attività del codice.</span><span class="sxs-lookup"><span data-stu-id="54b1e-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54b1e-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="54b1e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="54b1e-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="54b1e-122">Element</span></span>|<span data-ttu-id="54b1e-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54b1e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="54b1e-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="54b1e-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="54b1e-125">Un elemento di configurazione che contiene tutte le query per un flusso di lavoro specifico identificato dal **activityDefinitionId** proprietà.</span><span class="sxs-lookup"><span data-stu-id="54b1e-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54b1e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54b1e-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="54b1e-127">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="54b1e-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="54b1e-128">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="54b1e-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
