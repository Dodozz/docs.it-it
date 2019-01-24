---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 7b872d933d07af329601063b3d769bc43a22007c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568673"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="17984-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="17984-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="17984-103">Rappresenta una query usata per rilevare le modifiche al ciclo di vita delle attività che costituiscono un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="17984-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="17984-104">Ad esempio, è possibile tenere traccia di ogni volta che viene completata l'attività "Invia messaggio" all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="17984-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="17984-105">Questa query è necessaria affinché un partecipante del rilevamento sottoscriva gli oggetti record di stato.</span><span class="sxs-lookup"><span data-stu-id="17984-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="17984-106">Gli stati disponibili per la sottoscrizione sono specificati in ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="17984-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="17984-107">Per altre informazioni sulle query relative ai profili di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="17984-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="17984-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17984-108">\<system.serviceModel></span></span>  
<span data-ttu-id="17984-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="17984-109">\<tracking></span></span>  
<span data-ttu-id="17984-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="17984-110">\<trackingProfile></span></span>  
<span data-ttu-id="17984-111">\<flusso di lavoro ></span><span class="sxs-lookup"><span data-stu-id="17984-111">\<workflow></span></span>  
<span data-ttu-id="17984-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="17984-112">\<activityStateQueries></span></span>  
<span data-ttu-id="17984-113">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="17984-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17984-114">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17984-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17984-115">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="17984-115">Attributes and Elements</span></span>  
 <span data-ttu-id="17984-116">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="17984-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17984-117">Attributi</span><span class="sxs-lookup"><span data-stu-id="17984-117">Attributes</span></span>  
  
|<span data-ttu-id="17984-118">Attributo</span><span class="sxs-lookup"><span data-stu-id="17984-118">Attribute</span></span>|<span data-ttu-id="17984-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17984-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17984-120">activityName</span><span class="sxs-lookup"><span data-stu-id="17984-120">activityName</span></span>|<span data-ttu-id="17984-121">Stringa che specifica il nome dell'attività per la quale filtrare istanze di <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="17984-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17984-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="17984-122">Child Elements</span></span>  
  
|<span data-ttu-id="17984-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="17984-123">Element</span></span>|<span data-ttu-id="17984-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17984-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17984-125">\<argomenti ></span><span class="sxs-lookup"><span data-stu-id="17984-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="17984-126">Raccolta di argomenti associati a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="17984-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="17984-127">\<states></span><span class="sxs-lookup"><span data-stu-id="17984-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="17984-128">Raccolta di elementi di configurazione contenenti gli stati dell'attività sottoscritta per la quale deve essere generato un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="17984-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="17984-129">\<states></span><span class="sxs-lookup"><span data-stu-id="17984-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="17984-130">Raccolta di variabili associate a questa query di attività.</span><span class="sxs-lookup"><span data-stu-id="17984-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17984-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="17984-131">Parent Elements</span></span>  
  
|<span data-ttu-id="17984-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="17984-132">Element</span></span>|<span data-ttu-id="17984-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="17984-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17984-134">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="17984-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="17984-135">Rappresenta un elenco di elementi di configurazione usati per rilevare le richieste di annullamento di un'attività figlio da parte dell'attività padre.</span><span class="sxs-lookup"><span data-stu-id="17984-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="17984-136">La query è necessaria affinché un partecipante del rilevamento esegua la sottoscrizione per annullare oggetti record richiesti.</span><span class="sxs-lookup"><span data-stu-id="17984-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17984-137">Note</span><span class="sxs-lookup"><span data-stu-id="17984-137">Remarks</span></span>  
 <span data-ttu-id="17984-138">Una funzionalità univoca di un elemento ActivityStateQuery è rappresentata dalla possibilità di estrarre dati durante il rilevamento dell'esecuzione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="17984-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="17984-139">Tali dati offrono un contesto aggiuntivo quando si accede ai record di rilevamento durante la fase di post-esecuzione.</span><span class="sxs-lookup"><span data-stu-id="17984-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="17984-140">È possibile usare la [ \<argomenti >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) e [ \<stati >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementi da estrarre qualsiasi variabile o argomento da qualsiasi attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="17984-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="17984-141">Nell'esempio seguente viene mostrata una query sullo stato dell'attività che estrae variabili e argomenti quando viene creato il record di rilevamento dello stato `Closed` dell'attività.</span><span class="sxs-lookup"><span data-stu-id="17984-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="17984-142">Variabili e argomenti possono essere estratti solo con un ActivityStateRecord e quindi essere sottoscritti all'interno un rilevamento profilare mediante [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="17984-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17984-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17984-143">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="17984-144">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="17984-144">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="17984-145">Profili di rilevamento</span><span class="sxs-lookup"><span data-stu-id="17984-145">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
