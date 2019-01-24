---
title: '&lt;sendMessageChannelCache&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: dce81dec9067c25fc85b62cc4aa5860499347ab2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657350"
---
# <a name="ltsendmessagechannelcachegt"></a><span data-ttu-id="96538-102">&lt;sendMessageChannelCache&gt;</span><span class="sxs-lookup"><span data-stu-id="96538-102">&lt;sendMessageChannelCache&gt;</span></span>
<span data-ttu-id="96538-103">Comportamento del servizio che consente la personalizzazione della cache di condivisione a livelli, le impostazioni della cache della channel factory e le impostazioni della cache del canale per flussi di lavoro che inviano messaggi agli endpoint di servizio usando attività della messaggistica di invio.</span><span class="sxs-lookup"><span data-stu-id="96538-103">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="96538-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="96538-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="96538-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="96538-105">\<behaviors></span></span>  
<span data-ttu-id="96538-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="96538-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="96538-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="96538-107">\<behavior></span></span>  
<span data-ttu-id="96538-108">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="96538-108">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96538-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96538-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96538-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="96538-110">Attributes and Elements</span></span>  
 <span data-ttu-id="96538-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="96538-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96538-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="96538-112">Attributes</span></span>  
  
|<span data-ttu-id="96538-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="96538-113">Attribute</span></span>|<span data-ttu-id="96538-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96538-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="96538-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="96538-115">allowUnsafeCaching</span></span>|<span data-ttu-id="96538-116">Valore booleano che indica se attivare la memorizzazione nella cache.</span><span class="sxs-lookup"><span data-stu-id="96538-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="96538-117">Se il servizio flusso di lavoro dispone di associazioni o comportamenti personalizzati, la memorizzazione nella cache potrebbe non essere sicura e pertanto essere disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="96538-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="96538-118">Tuttavia, se si desidera attivare la memorizzazione nella cache, impostare questa proprietà **true**.</span><span class="sxs-lookup"><span data-stu-id="96538-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96538-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="96538-119">Child Elements</span></span>  
  
|<span data-ttu-id="96538-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="96538-120">Element</span></span>|<span data-ttu-id="96538-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96538-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96538-122">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="96538-122">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="96538-123">Specifica le impostazioni della cache del canale.</span><span class="sxs-lookup"><span data-stu-id="96538-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="96538-124">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="96538-124">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="96538-125">Specifica le impostazioni della cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="96538-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96538-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="96538-126">Parent Elements</span></span>  
  
|<span data-ttu-id="96538-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="96538-127">Element</span></span>|<span data-ttu-id="96538-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96538-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96538-129">\<comportamento > di \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="96538-129">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="96538-130">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="96538-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96538-131">Note</span><span class="sxs-lookup"><span data-stu-id="96538-131">Remarks</span></span>  
 <span data-ttu-id="96538-132">Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="96538-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="96538-133">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="96538-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="96538-134">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="96538-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="96538-135">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="96538-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="96538-136">Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="96538-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="96538-137">Per altre informazioni su come modificare la cache predefinita condivisione a livelli e le impostazioni della cache per la channel factory e cache del canale, vedere [modifica dei livelli di condivisione della Cache per le attività Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="96538-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96538-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="96538-138">Example</span></span>  
 <span data-ttu-id="96538-139">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96538-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="96538-140">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="96538-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="96538-141">L'esempio seguente mostra il contenuto del file di configurazione che contiene il **MyChannelCacheBehavior** comportamento del servizio con le impostazioni della cache factory personalizzata della cache e del canale.</span><span class="sxs-lookup"><span data-stu-id="96538-141">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="96538-142">Questo comportamento viene aggiunto al servizio tramite il **behaviorConfiguarion** attributo.</span><span class="sxs-lookup"><span data-stu-id="96538-142">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96538-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96538-143">See also</span></span>
- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="96538-144">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="96538-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
