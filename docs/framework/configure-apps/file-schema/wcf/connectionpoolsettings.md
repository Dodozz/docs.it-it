---
title: '&lt;connectionPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 2d79b3e28d1a80011cba7c515d979ae0037785a5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149527"
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="1385e-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="1385e-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="1385e-103">Specifica impostazioni aggiuntive del pool di connessioni per un'associazione con named pipe.</span><span class="sxs-lookup"><span data-stu-id="1385e-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="1385e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1385e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1385e-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1385e-105">\<bindings></span></span>  
<span data-ttu-id="1385e-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1385e-106">\<customBinding></span></span>  
<span data-ttu-id="1385e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1385e-107">\<binding></span></span>  
<span data-ttu-id="1385e-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="1385e-108">\<namePipeTransport></span></span>  
<span data-ttu-id="1385e-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="1385e-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1385e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1385e-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1385e-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1385e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1385e-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1385e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1385e-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1385e-113">Attributes</span></span>  
  
|<span data-ttu-id="1385e-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1385e-114">Attribute</span></span>|<span data-ttu-id="1385e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1385e-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="1385e-116">Stringa che definisce il nome del pool di connessioni usato per canali in uscita.</span><span class="sxs-lookup"><span data-stu-id="1385e-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="1385e-117">In modalità di invio nel flusso, le connessioni non sono condivise, pertanto il pool di connessioni è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1385e-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="1385e-118">Il valore predefinito è una stringa "default".</span><span class="sxs-lookup"><span data-stu-id="1385e-118">The default is a "default" string.</span></span> <span data-ttu-id="1385e-119">È possibile modificare questo valore per isolare le connessioni per un particolare client in gruppi separati.</span><span class="sxs-lookup"><span data-stu-id="1385e-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="1385e-120">Elemento <xref:System.TimeSpan> positivo che specifica il periodo massimo di inattività della connessione prima che venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="1385e-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="1385e-121">L'impostazione predefinita è 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="1385e-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="1385e-122">Numero intero positivo che specifica il numero massimo di connessioni a un endpoint remoto iniziate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="1385e-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="1385e-123">Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito.</span><span class="sxs-lookup"><span data-stu-id="1385e-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="1385e-124">`idleTimeout` limita il periodo di tempo entro il quale le connessioni rimangono in coda prima che venga generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1385e-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="1385e-125">Il valore predefinito è 10.</span><span class="sxs-lookup"><span data-stu-id="1385e-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="1385e-126">Questo attributo limita il numero di connessioni attive simultanee dal client a un particolare endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="1385e-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="1385e-127">Se questo valore viene superato a causa di un numero maggiore di connessioni client attive, può risultare che il servizio non risponda al client.</span><span class="sxs-lookup"><span data-stu-id="1385e-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="1385e-128">In questo caso, il valore deve essere regolato in modo da superare il numero massimo di connessioni client simultanee previste a un endpoint specifico.</span><span class="sxs-lookup"><span data-stu-id="1385e-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1385e-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1385e-129">Child Elements</span></span>  
 <span data-ttu-id="1385e-130">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1385e-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1385e-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1385e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="1385e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="1385e-132">Element</span></span>|<span data-ttu-id="1385e-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1385e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1385e-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="1385e-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="1385e-135">Definisce un trasporto che fa in modo che un canale trasferisca messaggi usando named pipe.</span><span class="sxs-lookup"><span data-stu-id="1385e-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1385e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1385e-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="1385e-137">Trasporti</span><span class="sxs-lookup"><span data-stu-id="1385e-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="1385e-138">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="1385e-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="1385e-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1385e-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1385e-140">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1385e-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1385e-141">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1385e-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1385e-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1385e-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
