---
title: <workflow> of WCF
ms.date: 03/30/2017
ms.assetid: c0443eba-d3b4-4fae-886e-9878daf77691
ms.openlocfilehash: 190e66096cf2dfa2028c95b22526fc3c84712ab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122070"
---
# <a name="workflow-of-wcf"></a><span data-ttu-id="fbd2b-102">\<flusso di lavoro > di WCF</span><span class="sxs-lookup"><span data-stu-id="fbd2b-102">\<workflow> of WCF</span></span>
<span data-ttu-id="fbd2b-103">Configurare un partecipante del rilevamento che ascolta i record di rilevamento generati direttamente durante la fase di esecuzione e li elabora in base alle impostazioni configurate.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="fbd2b-104">Tali impostazioni includono la scrittura in un output specifico, ad esempio file, console, ETW, l'elaborazione/aggregazione dei record o qualsiasi altra combinazione che potrebbe essere richiesta.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="fbd2b-105">Per altre informazioni sul rilevamento del flusso di lavoro e sui partecipanti di rilevamento, vedere [flusso di lavoro di rilevamento e traccia](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) e [partecipanti del rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="fbd2b-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="fbd2b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fbd2b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fbd2b-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fbd2b-107">\<tracking></span></span>  
<span data-ttu-id="fbd2b-108">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="fbd2b-108">\<participants></span></span>  
<span data-ttu-id="fbd2b-109">\<add></span><span class="sxs-lookup"><span data-stu-id="fbd2b-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbd2b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbd2b-110">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbd2b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fbd2b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fbd2b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbd2b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="fbd2b-113">Attributes</span></span>  
  
|<span data-ttu-id="fbd2b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbd2b-114">Element</span></span>|<span data-ttu-id="fbd2b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbd2b-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbd2b-116">name</span><span class="sxs-lookup"><span data-stu-id="fbd2b-116">name</span></span>|<span data-ttu-id="fbd2b-117">Stringa che specifica il nome di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-117">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="fbd2b-118">profileName</span><span class="sxs-lookup"><span data-stu-id="fbd2b-118">profileName</span></span>|<span data-ttu-id="fbd2b-119">Stringa che specifica il nome del profilo di rilevamento che definisce i record di rilevamento sottoscritti dal partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-119">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="fbd2b-120">tipo</span><span class="sxs-lookup"><span data-stu-id="fbd2b-120">type</span></span>|<span data-ttu-id="fbd2b-121">Stringa che specifica il tipo di un partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-121">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbd2b-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fbd2b-122">Child Elements</span></span>  
 <span data-ttu-id="fbd2b-123">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbd2b-124">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fbd2b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fbd2b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbd2b-125">Element</span></span>|<span data-ttu-id="fbd2b-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbd2b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbd2b-127">\<i partecipanti ></span><span class="sxs-lookup"><span data-stu-id="fbd2b-127">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="fbd2b-128">Elenco di partecipanti del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-128">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbd2b-129">Note</span><span class="sxs-lookup"><span data-stu-id="fbd2b-129">Remarks</span></span>  
 <span data-ttu-id="fbd2b-130">I partecipanti del rilevamento vengono usati per ottenere i dati di rilevamento generati dal flusso di lavoro e archiviarli in supporti differenti.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-130">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="fbd2b-131">Analogamente, è anche possibile eseguire qualsiasi operazione di post-elaborazione sui record di rilevamento all'interno del partecipante del rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-131">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="fbd2b-132">Più partecipanti del rilevamento possono usare simultaneamente gli eventi di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-132">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="fbd2b-133">Ogni partecipante del rilevamento può essere associato a un profilo di rilevamento diverso.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-133">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="fbd2b-134">Viene fornito un partecipante del rilevamento standard che scrive i record di rilevamento in una sessione ETW.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-134">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="fbd2b-135">Il partecipante viene configurato su un servizio flusso di lavoro aggiungendo un comportamento specifico del rilevamento in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-135">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="fbd2b-136">L'abilitazione di un partecipante del rilevamento ETW consente la visualizzazione dei record di rilevamento nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-136">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="fbd2b-137">Se tale partecipante non soddisfa i propri requisiti, è anche possibile scrivere un partecipante del rilevamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-137">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd2b-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbd2b-138">Example</span></span>  
 <span data-ttu-id="fbd2b-139">Nell'esempio di configurazione seguente viene mostrato il partecipante del rilevamento ETW standard configurato nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-139">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="fbd2b-140">L'ID del provider usato dal partecipante del rilevamento ETW per scrivere i record di rilevamento in ETW è definito nella sezione `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-140">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="fbd2b-141">Al partecipante di rilevamento è associato un profilo per specificare i record di rilevamento che ha sottoscritto.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-141">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="fbd2b-142">Tale profilo è definito dall'attributo `profileName` dell'elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-142">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="fbd2b-143">Dopo aver definito tali elementi, il partecipante del rilevamento viene aggiunto al comportamento del servizio `<etwTracking>`,</span><span class="sxs-lookup"><span data-stu-id="fbd2b-143">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="fbd2b-144">che aggiungerà i partecipanti del rilevamento selezionati alle estensioni dell'istanza del flusso di lavoro, in modo che inizino a ricevere i record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fbd2b-144">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="fbd2b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbd2b-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="fbd2b-146">Rilevamento e traccia del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fbd2b-146">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fbd2b-147">Partecipanti del rilevamento</span><span class="sxs-lookup"><span data-stu-id="fbd2b-147">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
