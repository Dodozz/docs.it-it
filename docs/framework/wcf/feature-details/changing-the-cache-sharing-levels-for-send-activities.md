---
title: Modifica dei livelli di condivisione della cache per le attività Send
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: 079eb037f074155aec3ad5473480bbf5d4d341b2
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425164"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a><span data-ttu-id="70855-102">Modifica dei livelli di condivisione della cache per le attività Send</span><span class="sxs-lookup"><span data-stu-id="70855-102">Changing the Cache Sharing Levels for Send Activities</span></span>
<span data-ttu-id="70855-103">L'estensione <xref:System.ServiceModel.Activities.SendMessageChannelCache> consente di personalizzare i livelli di condivisione della cache, le impostazioni della cache della channel factory e della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint del servizio tramite le attività di messaggistica <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="70855-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension enables you to customize the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using <xref:System.ServiceModel.Activities.Send> messaging activities.</span></span> <span data-ttu-id="70855-104">Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="70855-104">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="70855-105">La cache della channel factory contiene gli oggetti <xref:System.ServiceModel.ChannelFactory%601> memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="70855-105">The channel factory cache contains cached <xref:System.ServiceModel.ChannelFactory%601> objects.</span></span> <span data-ttu-id="70855-106">La cache del canale contiene i canali memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="70855-106">The channel cache contains cached channels.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70855-107">I flussi di lavoro possono utilizzare le attività di messaggistica <xref:System.ServiceModel.Activities.Send> per inviare messaggi o parametri.</span><span class="sxs-lookup"><span data-stu-id="70855-107">Workflows can use <xref:System.ServiceModel.Activities.Send> messaging activities to send either messages or parameters.</span></span> <span data-ttu-id="70855-108">L'esecuzione del flusso di lavoro aggiunge channel factory alla cache che creano canali di tipo <xref:System.ServiceModel.Channels.IRequestChannel> quando si utilizza un'attività <xref:System.ServiceModel.Activities.ReceiveReply> con un'attività <xref:System.ServiceModel.Activities.Send> e un oggetto <xref:System.ServiceModel.Channels.IOutputChannel> quando si utilizza solo un'attività <xref:System.ServiceModel.Activities.Send> (nessuna attività <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="70855-108">The workflow runtime adds channel factories to the cache that create channels of type <xref:System.ServiceModel.Channels.IRequestChannel> when you use a <xref:System.ServiceModel.Activities.ReceiveReply> activity with a <xref:System.ServiceModel.Activities.Send> activity, and an <xref:System.ServiceModel.Channels.IOutputChannel> when just using a <xref:System.ServiceModel.Activities.Send> activity (no <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>  
  
## <a name="the-cache-sharing-levels"></a><span data-ttu-id="70855-109">Livelli di condivisione della cache</span><span class="sxs-lookup"><span data-stu-id="70855-109">The Cache Sharing Levels</span></span>  
 <span data-ttu-id="70855-110">Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache utilizzata dalle attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa da tutte le istanze del flusso di lavoro nell'oggetto <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host).</span><span class="sxs-lookup"><span data-stu-id="70855-110">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost> the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="70855-111">Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza).</span><span class="sxs-lookup"><span data-stu-id="70855-111">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="70855-112">La cache è disponibile solo per le attività <xref:System.ServiceModel.Activities.Send> che non utilizzano gli endpoint definiti nella configurazione, a meno che non sia abilitata la memorizzazione nella cache non sicura.</span><span class="sxs-lookup"><span data-stu-id="70855-112">The cache is only available for <xref:System.ServiceModel.Activities.Send> activities that do not use endpoints defined in configuration unless unsafe caching is enabled.</span></span>  
  
 <span data-ttu-id="70855-113">Di seguito sono riportati i diversi livelli di condivisione della cache disponibili per le attività <xref:System.ServiceModel.Activities.Send> in un flusso di lavoro e il relativo utilizzo consigliato:</span><span class="sxs-lookup"><span data-stu-id="70855-113">The following are the different cache sharing levels available for <xref:System.ServiceModel.Activities.Send> activities in a workflow and their recommended use:</span></span>  
  
- <span data-ttu-id="70855-114">**Livello host**: Nel livello di condivisione host, la cache è disponibile solo per le istanze del flusso di lavoro ospitate nell'host del servizio del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-114">**Host Level**: In the host sharing level, the cache is available only to the workflow instances hosted in the workflow service host.</span></span> <span data-ttu-id="70855-115">Una cache può essere condivisa anche tra host del servizio flusso di lavoro di una cache a livello di processo.</span><span class="sxs-lookup"><span data-stu-id="70855-115">A cache can also be shared between workflow service hosts in a process-wide cache.</span></span>  
  
- <span data-ttu-id="70855-116">**Livello di istanza**: Nell'istanza del livello di condivisione, la cache è disponibile per una particolare istanza tutta la sua durata ma la cache non è disponibile ad altre istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-116">**Instance Level**: In the instance sharing level, the cache is available to a particular workflow instance throughout its lifetime but the cache is not available to other workflow instances.</span></span>  
  
- <span data-ttu-id="70855-117">**Nessuna Cache**: La cache è disattivata per impostazione predefinita se si dispone di un flusso di lavoro che utilizza gli endpoint definiti nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="70855-117">**No Cache**: The cache is turned off by default if you have a workflow that uses endpoints defined in configuration.</span></span> <span data-ttu-id="70855-118">In questo caso, è consigliabile mantenere disattivata la cache anche perché l'attivazione potrebbe risultare non sicura,</span><span class="sxs-lookup"><span data-stu-id="70855-118">It is also recommended to keep the cache turned off in this case because turning it on could be unsecure.</span></span> <span data-ttu-id="70855-119">ad esempio, se per ogni invio è necessaria un'identità diversa (credenziali diverse o utilizzo della rappresentazione).</span><span class="sxs-lookup"><span data-stu-id="70855-119">For example, if a different identity (different credentials or using impersonation) is required for each send.</span></span>  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a><span data-ttu-id="70855-120">Modifica del livello di condivisione della cache per un flusso di lavoro client</span><span class="sxs-lookup"><span data-stu-id="70855-120">Changing the Cache Sharing Level for a Client Workflow</span></span>  
 <span data-ttu-id="70855-121">Per impostare la condivisione della cache in un flusso di lavoro client, aggiungere un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> come estensione al set desiderato di istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-121">To set the cache sharing in a client workflow, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to the desired set of workflow instances.</span></span> <span data-ttu-id="70855-122">In questo modo la cache viene condivisa in tutte le istanze del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-122">This results in sharing the cache across all the workflow instances.</span></span> <span data-ttu-id="70855-123">Negli esempi di codice seguenti viene mostrato come eseguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="70855-123">The following code examples show how to perform these steps.</span></span>  
  
 <span data-ttu-id="70855-124">Innanzitutto, dichiarare un'istanza di tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="70855-124">First, declare an instance of type <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span></span>  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 <span data-ttu-id="70855-125">Successivamente, aggiungere l'estensione della cache a ogni istanza del flusso di lavoro client.</span><span class="sxs-lookup"><span data-stu-id="70855-125">Next, add the cache extension to each client workflow instance.</span></span>  
  
```csharp 
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object   
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a><span data-ttu-id="70855-126">Modifica del livello di condivisione della cache per un servizio di flusso di lavoro ospitato</span><span class="sxs-lookup"><span data-stu-id="70855-126">Changing the Cache Sharing Level for a Hosted Workflow Service</span></span>  
 <span data-ttu-id="70855-127">Per impostare la condivisione della cache in un servizio di flusso di lavoro ospitato, aggiungere un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> come estensione a tutti gli host del servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-127">To set the cache sharing in a hosted workflow service, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to all the workflow service hosts.</span></span> <span data-ttu-id="70855-128">In questo modo la cache viene condivisa in tutti gli host del servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-128">This results in sharing the cache across all the workflow service hosts.</span></span> <span data-ttu-id="70855-129">Negli esempi di codice seguenti viene mostrato come eseguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="70855-129">The following code examples show to perform these steps.</span></span>  
  
 <span data-ttu-id="70855-130">Innanzitutto, dichiarare un'istanza di tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache> a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="70855-130">First, declare an instance  of type <xref:System.ServiceModel.Activities.SendMessageChannelCache> at the class level.</span></span>  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 <span data-ttu-id="70855-131">Successivamente, aggiungere l'estensione della cache statica a ogni host del servizio di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-131">Next, add the static cache extension to each workflow service host.</span></span>  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 <span data-ttu-id="70855-132">Per impostare la divisione della cache in un servizio flusso di lavoro ospitato a livello di istanza, aggiungere un delegato `Func<SendMessageChannelCache>` come estensione all'host del servizio flusso di lavoro e assegnare questo delegato al codice che crea una nuova istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="70855-132">To set the cache sharing in a hosted workflow service to the instance level, add a `Func<SendMessageChannelCache>` delegate as an extension to the workflow service host and assign this delegate to the code that instantiates a new instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class.</span></span> <span data-ttu-id="70855-133">Ciò comporta una cache diversa per ogni singola istanza del flusso di lavoro, anziché una sola cache condivisa da tutte le istanze del flusso di lavoro nell'host del servizio flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-133">This results in a different cache for each individual workflow instance, instead of a single cache shared by all workflow instances in the workflow service host.</span></span> <span data-ttu-id="70855-134">Nell'esempio di codice seguente viene mostrato come eseguire questa operazione tramite un'espressione lambda per definire direttamente l'estensione <xref:System.ServiceModel.Activities.SendMessageChannelCache> a cui il delegato fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="70855-134">The following code example shows how to achieve this by using a lambda expression to directly define the <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension that the delegate points to.</span></span>  
  
```csharp 
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings   
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings   
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a><span data-ttu-id="70855-135">Personalizzazione delle impostazioni della cache</span><span class="sxs-lookup"><span data-stu-id="70855-135">Customizing Cache Settings</span></span>  
 <span data-ttu-id="70855-136">È possibile personalizzare le impostazioni della cache della channel factory e del canale.</span><span class="sxs-lookup"><span data-stu-id="70855-136">You can customize the cache settings for the channel factory cache and the channel cache.</span></span> <span data-ttu-id="70855-137">Le impostazioni della cache sono definite nella classe <xref:System.ServiceModel.Activities.ChannelCacheSettings>.</span><span class="sxs-lookup"><span data-stu-id="70855-137">The cache settings are defined in the <xref:System.ServiceModel.Activities.ChannelCacheSettings> class.</span></span> <span data-ttu-id="70855-138">La classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> definisce le impostazioni predefinite per la cache della channel factory e del canale nel costruttore predefinito.</span><span class="sxs-lookup"><span data-stu-id="70855-138">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> class defines default cache settings for the channel factory cache and the channel cache in its default constructor.</span></span> <span data-ttu-id="70855-139">Nella tabella seguente vengono elencati i valori predefiniti di queste impostazioni per ogni tipo di cache.</span><span class="sxs-lookup"><span data-stu-id="70855-139">The following table lists the default values of these cache settings for each type of cache.</span></span>  
  
|<span data-ttu-id="70855-140">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="70855-140">Settings</span></span>|<span data-ttu-id="70855-141">LeaseTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="70855-141">LeaseTimeout (min)</span></span>|<span data-ttu-id="70855-142">IdleTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="70855-142">IdleTimeout (min)</span></span>|<span data-ttu-id="70855-143">MaxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="70855-143">MaxItemsInCache</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="70855-144">Valore predefinito della cache della factory</span><span class="sxs-lookup"><span data-stu-id="70855-144">Factory Cache Default</span></span>|<span data-ttu-id="70855-145">TimeSpan.MaxValue</span><span class="sxs-lookup"><span data-stu-id="70855-145">TimeSpan.MaxValue</span></span>|<span data-ttu-id="70855-146">2</span><span class="sxs-lookup"><span data-stu-id="70855-146">2</span></span>|<span data-ttu-id="70855-147">16</span><span class="sxs-lookup"><span data-stu-id="70855-147">16</span></span>|  
|<span data-ttu-id="70855-148">Valore predefinito della cache del canale</span><span class="sxs-lookup"><span data-stu-id="70855-148">Channel Cache Default</span></span>|<span data-ttu-id="70855-149">5</span><span class="sxs-lookup"><span data-stu-id="70855-149">5</span></span>|<span data-ttu-id="70855-150">2</span><span class="sxs-lookup"><span data-stu-id="70855-150">2</span></span>|<span data-ttu-id="70855-151">16</span><span class="sxs-lookup"><span data-stu-id="70855-151">16</span></span>|  
  
 <span data-ttu-id="70855-152">Per personalizzare le impostazioni della cache della factory e del canale, creare un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> utilizzando il costruttore con parametri <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> e passare una nuova istanza dell'oggetto <xref:System.ServiceModel.Activities.ChannelCacheSettings> con valori personalizzati a ognuno dei parametri `factorySettings` e `channelSettings`.</span><span class="sxs-lookup"><span data-stu-id="70855-152">To customize the factory cache and channel cache settings, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> and pass a new instance of the <xref:System.ServiceModel.Activities.ChannelCacheSettings> with custom values to each of the `factorySettings` and `channelSettings` parameters.</span></span> <span data-ttu-id="70855-153">Successivamente aggiungere la nuova istanza di questa classe come estensione a un host del servizio di flusso di lavoro o a un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-153">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="70855-154">Nell'esempio di codice seguente viene mostrato come eseguire questi passaggi per un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-154">The following code example shows how to perform these steps for a workflow instance.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,   
                        IdleTimeout = TimeSpan.FromMinutes(5),   
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,   
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="70855-155">Per abilitare la memorizzazione nella cache quando il servizio di flusso di lavoro dispone di endpoint definiti nella configurazione, creare un'istanza della classe <xref:System.ServiceModel.Activities.SendMessageChannelCache> utilizzando il costruttore con parametri <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> con il parametro `allowUnsafeCaching` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="70855-155">To enable caching when your workflow service has endpoints defined in configuration, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> with the `allowUnsafeCaching` parameter set to `true`.</span></span> <span data-ttu-id="70855-156">Successivamente aggiungere la nuova istanza di questa classe come estensione a un host del servizio di flusso di lavoro o a un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-156">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="70855-157">Nell'esempio di codice seguente viene mostrato come abilitare la memorizzazione nella cache per un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="70855-157">The following code example shows how to enable caching for a workflow instance.</span></span>  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="70855-158">Per disabilitare completamente la cache per le channel factory e i canali, disabilitare la cache della channel factory.</span><span class="sxs-lookup"><span data-stu-id="70855-158">To disable the cache completely for the channel factories and the channels, disable the channel factory cache.</span></span> <span data-ttu-id="70855-159">In questo modo viene disattivata anche la cache del canale poiché i canali appartengono alle channel factory corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="70855-159">Doing so also turns off the channel cache as the channels are owned by their corresponding channel factories.</span></span> <span data-ttu-id="70855-160">Per disabilitare la cache della channel factory, passare il parametro `factorySettings` al costruttore <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inizializzato su un'istanza <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valore <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> pari a 0.</span><span class="sxs-lookup"><span data-stu-id="70855-160">To disable the channel factory cache, pass the `factorySettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="70855-161">Nell'esempio di codice seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="70855-161">The following code example shows this.</span></span>  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="70855-162">È possibile scegliere di utilizzare solo la cache della channel factory e disabilitare la cache del canale passando il parametro `channelSettings` al costruttore <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inizializzato su un'istanza <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valore <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> pari a 0.</span><span class="sxs-lookup"><span data-stu-id="70855-162">You can choose to use only the channel factory cache and disable the channel cache by passing the `channelSettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="70855-163">Nell'esempio di codice seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="70855-163">The following code example shows this.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =   
    new SendMessageChannelCache(factorySettings, channelSettings);   
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="70855-164">In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="70855-164">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="70855-165">A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio.</span><span class="sxs-lookup"><span data-stu-id="70855-165">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="70855-166">L'esempio seguente mostra il contenuto del file di configurazione che contiene il `MyChannelCacheBehavior` comportamento del servizio con le impostazioni della cache factory personalizzata della cache e del canale.</span><span class="sxs-lookup"><span data-stu-id="70855-166">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="70855-167">Questo comportamento viene aggiunto al servizio tramite il `behaviorConfiguration` attributo.</span><span class="sxs-lookup"><span data-stu-id="70855-167">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
