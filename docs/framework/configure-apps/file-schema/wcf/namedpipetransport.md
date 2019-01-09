---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: bf9229411143345847247f36de07b5c014d3f259
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149600"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="5d55f-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="5d55f-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="5d55f-103">Definisce un trasporto che induce un canale a trasferire messaggi usando named pipe quando è incluso in un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5d55f-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="5d55f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5d55f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5d55f-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="5d55f-105">\<bindings></span></span>  
<span data-ttu-id="5d55f-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d55f-106">\<customBinding></span></span>  
<span data-ttu-id="5d55f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5d55f-107">\<binding></span></span>  
<span data-ttu-id="5d55f-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="5d55f-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d55f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d55f-109">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d55f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d55f-110">Attributes and Elements</span></span>  
<span data-ttu-id="5d55f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d55f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d55f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d55f-112">Attributes</span></span>  
<span data-ttu-id="5d55f-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5d55f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d55f-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d55f-114">Child Elements</span></span>  
  
|<span data-ttu-id="5d55f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d55f-115">Element</span></span>|<span data-ttu-id="5d55f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d55f-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d55f-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="5d55f-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="5d55f-118">Ottiene o imposta un <xref:System.TimeSpan> che determina il tempo massimo di un canale può trovarsi nello stato di inizializzazione prima della disconnessione.</span><span class="sxs-lookup"><span data-stu-id="5d55f-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="5d55f-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="5d55f-119">ConnectionBufferSize</span></span>|<span data-ttu-id="5d55f-120">Ottiene o imposta la dimensione del buffer utilizzato per trasmettere un blocco del messaggio serializzato in transito dal client o servizio.</span><span class="sxs-lookup"><span data-stu-id="5d55f-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="5d55f-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5d55f-121">hostNameComparisonMode</span></span>|<span data-ttu-id="5d55f-122">Ottiene o imposta un valore che indica se viene utilizzato il nome host per raggiungere il servizio in caso di corrispondenza dell'URI.</span><span class="sxs-lookup"><span data-stu-id="5d55f-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="5d55f-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="5d55f-123">manualAddressing</span></span>|<span data-ttu-id="5d55f-124">Ottiene o imposta un valore che indica se è richiesto l'indirizzamento manuale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d55f-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="5d55f-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5d55f-125">maxBufferPoolSize</span></span>|<span data-ttu-id="5d55f-126">Ottiene o imposta la dimensione massima, in byte, del pool di buffer utilizzati dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="5d55f-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="5d55f-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="5d55f-127">maxBufferSize</span></span>|<span data-ttu-id="5d55f-128">Ottiene o imposta la dimensione massima del buffer da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5d55f-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="5d55f-129">Per i messaggi trasmessi come flusso, questo valore deve essere uguale o superiore alla dimensione massima possibile delle intestazioni di messaggio, che vengono lette in modalità di memorizzazione nel buffer.</span><span class="sxs-lookup"><span data-stu-id="5d55f-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="5d55f-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="5d55f-130">maxOutputDelay</span></span>|<span data-ttu-id="5d55f-131">Ottiene o imposta l'intervallo di tempo massimo per cui un blocco di un messaggio o un messaggio intero può rimanere memorizzato nel buffer prima dell'invio.</span><span class="sxs-lookup"><span data-stu-id="5d55f-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="5d55f-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="5d55f-132">maxPendingAccepts</span></span>|<span data-ttu-id="5d55f-133">Ottiene o imposta il numero massimo di canali di che un servizio può avere in attesa di un listener per l'elaborazione delle connessioni in ingresso al servizio.</span><span class="sxs-lookup"><span data-stu-id="5d55f-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="5d55f-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="5d55f-134">maxPendingConnections</span></span>|<span data-ttu-id="5d55f-135">Ottiene o imposta il numero massimo di connessioni in attesa dell'invio nel servizio.</span><span class="sxs-lookup"><span data-stu-id="5d55f-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="5d55f-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5d55f-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="5d55f-137">Ottiene e imposta la dimensione massima consentita del messaggio, in byte, che possono essere ricevuti.</span><span class="sxs-lookup"><span data-stu-id="5d55f-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="5d55f-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="5d55f-138">transferMode</span></span>|<span data-ttu-id="5d55f-139">Ottiene o imposta un valore che indica se i messaggi vengono memorizzati nel buffer o trasmessi con il trasporto orientato alla connessione.</span><span class="sxs-lookup"><span data-stu-id="5d55f-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="5d55f-140">\<connectionPoolSettings > di \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="5d55f-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="5d55f-141">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="5d55f-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d55f-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d55f-142">Parent Elements</span></span>  
  
|<span data-ttu-id="5d55f-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d55f-143">Element</span></span>|<span data-ttu-id="5d55f-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d55f-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d55f-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="5d55f-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5d55f-146">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5d55f-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d55f-147">Note</span><span class="sxs-lookup"><span data-stu-id="5d55f-147">Remarks</span></span>  
<span data-ttu-id="5d55f-148">Questo trasporto usa URI nel formato "net.pipe://nomehost/percorso".</span><span class="sxs-lookup"><span data-stu-id="5d55f-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="5d55f-149">Gli altri componenti URI sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="5d55f-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="5d55f-150">L'elemento `namedPipeTransport` rappresenta il punto iniziale per la creazione di un'associazione personalizzata che implementa il protocollo di trasporto delle named pipe.</span><span class="sxs-lookup"><span data-stu-id="5d55f-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="5d55f-151">Questo trasporto viene usato per la comunicazione da computer con Windows Communication Foundation (WCF) a WCF.</span><span class="sxs-lookup"><span data-stu-id="5d55f-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d55f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d55f-152">See Also</span></span>  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
<span data-ttu-id="5d55f-153">[Trasporti](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="5d55f-153">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="5d55f-154">[Scelta di un trasporto](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="5d55f-154">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="5d55f-155">[associazioni](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5d55f-155">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="5d55f-156">[Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5d55f-156">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="5d55f-157">[Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="5d55f-157">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="5d55f-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d55f-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
