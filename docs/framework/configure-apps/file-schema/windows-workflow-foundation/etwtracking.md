---
title: '&lt;etwTracking&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: f9d1acd5dafb9df181b036db9d3ad783ca618874
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684326"
---
# <a name="ltetwtrackinggt"></a><span data-ttu-id="8918a-102">&lt;etwTracking&gt;</span><span class="sxs-lookup"><span data-stu-id="8918a-102">&lt;etwTracking&gt;</span></span>
<span data-ttu-id="8918a-103">Comportamento del servizio che consente a un servizio utilizzare rilevamento ETW mediante un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="8918a-103">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="8918a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8918a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8918a-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8918a-105">\<behaviors></span></span>  
<span data-ttu-id="8918a-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8918a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8918a-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8918a-107">\<behavior></span></span>  
<span data-ttu-id="8918a-108">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="8918a-108">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8918a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8918a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8918a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8918a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8918a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8918a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8918a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8918a-112">Attributes</span></span>  
  
|<span data-ttu-id="8918a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8918a-113">Attribute</span></span>|<span data-ttu-id="8918a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8918a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8918a-115">profileName</span><span class="sxs-lookup"><span data-stu-id="8918a-115">profileName</span></span>|<span data-ttu-id="8918a-116">Stringa che specifica il nome del profilo di rilevamento associato a questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="8918a-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8918a-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8918a-117">Child Elements</span></span>  
 <span data-ttu-id="8918a-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8918a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8918a-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8918a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8918a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8918a-120">Element</span></span>|<span data-ttu-id="8918a-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8918a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8918a-122">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8918a-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="8918a-123">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="8918a-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8918a-124">Note</span><span class="sxs-lookup"><span data-stu-id="8918a-124">Remarks</span></span>  
 <span data-ttu-id="8918a-125">Quando viene aggiunto alla configurazione del comportamento del servizio, questo elemento di configurazione configura un partecipante del rilevamento su un servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8918a-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="8918a-126">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="8918a-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="8918a-127">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8918a-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8918a-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="8918a-128">Example</span></span>  
 <span data-ttu-id="8918a-129">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="8918a-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="8918a-130">L'Id del Provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nel  **\<diagnostica >** sezione.</span><span class="sxs-lookup"><span data-stu-id="8918a-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="8918a-131">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="8918a-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="8918a-132">Ciò viene definito dal **profileName** attributo il  **\<aggiungere >** elemento.</span><span class="sxs-lookup"><span data-stu-id="8918a-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="8918a-133">Dopo aver definito tali elementi, viene aggiunto il partecipante di rilevamento per il  **\<etwTracking >** comportamento del servizio.</span><span class="sxs-lookup"><span data-stu-id="8918a-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="8918a-134">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="8918a-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8918a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8918a-135">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="8918a-136">Rilevamento e analisi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="8918a-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8918a-137">Partecipanti di rilevamento</span><span class="sxs-lookup"><span data-stu-id="8918a-137">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
