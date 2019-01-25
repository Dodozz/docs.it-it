---
title: '&lt;udpAnnoucementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 5b3fa9c5-f372-4df9-a9d6-1e426063b721
ms.openlocfilehash: ab0e786ec4b21f25682c52fb7609d24e901f6eac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582435"
---
# <a name="ltudpannoucementendpointgt"></a><span data-ttu-id="83766-102">&lt;udpAnnoucementEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="83766-102">&lt;udpAnnoucementEndpoint&gt;</span></span>
<span data-ttu-id="83766-103">Questo elemento di configurazione definisce un endpoint standard usato dai servizi per inviare messaggi di annuncio su un'associazione UDP.</span><span class="sxs-lookup"><span data-stu-id="83766-103">This configuration element defines a standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span> <span data-ttu-id="83766-104">Dispone di un contratto fisso e supporta due versioni di individuazione.</span><span class="sxs-lookup"><span data-stu-id="83766-104">It has a fixed contract and supports two discovery versions.</span></span> <span data-ttu-id="83766-105">Dispone inoltre di un'associazione UDP fissa e di un valore dell'indirizzo predefinito come indicato nelle specifiche WS-Discovery (WS-Discovery aprile 2005 o versione WS-Discovery 1.1).</span><span class="sxs-lookup"><span data-stu-id="83766-105">In addition it has a fixed UDP binding and a default address value as specified in the WS-Discovery specifications (WS-Discovery April 2005 or WS-Discovery version 1.1).</span></span> <span data-ttu-id="83766-106">È possibile specificare l'indirizzo multicast da usare per l'invio e la ricezione dei messaggi di annuncio.</span><span class="sxs-lookup"><span data-stu-id="83766-106">You can specify the multicast address to use for sending and receiving the announcement messages.</span></span>  
  
<span data-ttu-id="83766-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="83766-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="83766-108">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="83766-108">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83766-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83766-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83766-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="83766-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83766-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="83766-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83766-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="83766-112">Attributes</span></span>  
  
|<span data-ttu-id="83766-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="83766-113">Attribute</span></span>|<span data-ttu-id="83766-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83766-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83766-115">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="83766-115">discoveryVersion</span></span>|<span data-ttu-id="83766-116">Stringa che specifica una delle due versioni del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="83766-116">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="83766-117">I valori validi sono WSDiscovery11 e WSDiscoveryApril2005.</span><span class="sxs-lookup"><span data-stu-id="83766-117">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="83766-118">Questo valore è di tipo <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span><span class="sxs-lookup"><span data-stu-id="83766-118">This value is of type <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.</span></span>|  
|<span data-ttu-id="83766-119">maxAnnouncementDelay</span><span class="sxs-lookup"><span data-stu-id="83766-119">maxAnnouncementDelay</span></span>|<span data-ttu-id="83766-120">Valore TimeSpan che specifica il valore massimo per il tempo di attesa del protocollo di individuazione prima dell'invio di un messaggio Hello.</span><span class="sxs-lookup"><span data-stu-id="83766-120">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending a Hello message.</span></span> <span data-ttu-id="83766-121">Prima dell'invio dei messaggi, trascorrerà un periodo di attesa il cui valore casuale è compreso tra 0 e il valore di questo attributo.</span><span class="sxs-lookup"><span data-stu-id="83766-121">The messages will wait for a random time value between 0 and the value of this attribute before being sent.</span></span> <span data-ttu-id="83766-122">Questo attributo viene usato per impostare un ritardo casuale limitato che consente di evitare problemi di rete quando la rete si arresta e tutti i servizi ritornano online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="83766-122">This attribute is used to set a small, random delay to prevent network storms when a network goes out and all services come back online at the same time.</span></span>|  
|<span data-ttu-id="83766-123">multicastAddress</span><span class="sxs-lookup"><span data-stu-id="83766-123">multicastAddress</span></span>|<span data-ttu-id="83766-124">URI che specifica un indirizzo multicast da usare per l'invio e la ricezione dei messaggi di individuazione.</span><span class="sxs-lookup"><span data-stu-id="83766-124">A URI that specifies a multicast address to use for sending and receiving the discovery messages.</span></span> <span data-ttu-id="83766-125">Il valore predefinito è l'indirizzo multicast conforme alla specifica del protocollo.</span><span class="sxs-lookup"><span data-stu-id="83766-125">The default value is the multicast address as conformant to the protocol specification.</span></span>|  
|<span data-ttu-id="83766-126">name</span><span class="sxs-lookup"><span data-stu-id="83766-126">name</span></span>|<span data-ttu-id="83766-127">Stringa che specifica il nome della configurazione dell'endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="83766-127">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="83766-128">Il nome viene usato nell'attributo `endpointConfiguration` dell'endpoint del servizio per collegare un endpoint standard alla relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="83766-128">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83766-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="83766-129">Child Elements</span></span>  
  
|<span data-ttu-id="83766-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="83766-130">Element</span></span>|<span data-ttu-id="83766-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83766-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83766-132">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="83766-132">\<udpTransportSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|<span data-ttu-id="83766-133">Raccolta di impostazioni che consentono di configurare il trasporto UDP per l'endpoint UDP.</span><span class="sxs-lookup"><span data-stu-id="83766-133">A collection of settings that allow you to configure UDP transport for the UDP endpoint.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83766-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="83766-134">Parent Elements</span></span>  
  
|<span data-ttu-id="83766-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="83766-135">Element</span></span>|<span data-ttu-id="83766-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83766-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83766-137">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="83766-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="83766-138">Raccolta di endpoint standard rappresentati da endpoint predefiniti con una o più delle relative proprietà (indirizzo, associazione, contratto) fisse.</span><span class="sxs-lookup"><span data-stu-id="83766-138">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83766-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="83766-139">Example</span></span>  
 <span data-ttu-id="83766-140">Nell'esempio seguente viene illustrato un client in ascolto di un annuncio su un trasporto multicast UDP con indirizzo multicast predefinito e trasporto multicast UDP con indirizzo multicast specificato.</span><span class="sxs-lookup"><span data-stu-id="83766-140">The following example demonstrates a client listening for announcement over a UDP multicast transport with default multicast address, and UDP multicast transport with specified multicast address.</span></span>  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="udpAnnouncementEndpointStandard"
              kind="udpAnnouncementEndpoint"
              bindingConfiguration="..." />
    <endpoint name="udpAnnouncementEndpoint2"
              kind="udpAnnouncementEndpoint"
              endpointConfiguration="AnnouncementConfiguration3702"
              bindingConfiguration="..." />
    ...
  </service>
</services>
<standardEndpoints>
  <udpAnnouncementEndpoint>
    <standardEndpoint name="AnnouncementConfiguration2"
                      version="WSDiscoveryApril2005"
                      multicastAddress="soap.udp://239.255.255.250:3703"/>
  </udpAnnouncementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a><span data-ttu-id="83766-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83766-141">See also</span></span>
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>
