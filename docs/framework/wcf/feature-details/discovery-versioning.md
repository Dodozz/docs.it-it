---
title: Controllo delle versioni per l'individuazione
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 18c160e5e08ed9b6733bed9d5e40a4dde00dfd1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61856648"
---
# <a name="discovery-versioning"></a><span data-ttu-id="64432-102">Controllo delle versioni per l'individuazione</span><span class="sxs-lookup"><span data-stu-id="64432-102">Discovery Versioning</span></span>
<span data-ttu-id="64432-103">In questo argomento viene fornita una breve panoramica dell'implementazione di alcune nuove funzionalità di individuazione.</span><span class="sxs-lookup"><span data-stu-id="64432-103">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="64432-104">Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.</span><span class="sxs-lookup"><span data-stu-id="64432-104">It also gives an overview on how to select the discovery version to use.</span></span>  
  
## <a name="discovery-versioning"></a><span data-ttu-id="64432-105">Controllo delle versioni per l'individuazione</span><span class="sxs-lookup"><span data-stu-id="64432-105">Discovery Versioning</span></span>  
 <span data-ttu-id="64432-106">La funzionalità di individuazione include il supporto per tre versioni del protocollo WS_Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-106">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="64432-107">Le interfacce API di individuazione consentono di selezionare la versione del protocollo che si desidera usare.</span><span class="sxs-lookup"><span data-stu-id="64432-107">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="64432-108">Questo documento contiene brevi descrizioni sulle impostazioni correlate al controllo delle versioni.</span><span class="sxs-lookup"><span data-stu-id="64432-108">This document briefly describes the versioning-related settings.</span></span>  
  
 <span data-ttu-id="64432-109">Le classi di individuazione seguenti dispongo ora di una proprietà <xref:System.ServiceModel.Discovery.DiscoveryVersion> e usano un argomento <xref:System.ServiceModel.Discovery.DiscoveryVersion> nei propri costruttori:</span><span class="sxs-lookup"><span data-stu-id="64432-109">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>  
  
-   <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="64432-110">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="64432-110">DiscoveryVersion.WSDiscoveryApril2005</span></span>  
 <span data-ttu-id="64432-111">Fornendo <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> come costruttore di parametro, l'implementazione utilizzerà la versione April2005 del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-111">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="64432-112">Questa versione corrisponde alla versione pubblicata della specifica del protocollo di WS-Discovery</span><span class="sxs-lookup"><span data-stu-id="64432-112">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="64432-113">e deve essere usata per interoperare con l'applicazione legacy che usa la versione April2005 di WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-113">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>  
  
### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="64432-114">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="64432-114">DiscoveryVersion.WSDiscovery11</span></span>  
 <span data-ttu-id="64432-115">La versione di individuazione predefinita usata per le API è <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span><span class="sxs-lookup"><span data-stu-id="64432-115">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="64432-116">Si tratta della versione standardizzata corrente del protocollo di WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-116">This is the current standardized version of the WS-Discovery protocol.</span></span>  
  
## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="64432-117">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="64432-117">DiscoveryVersion.WSDiscoveryCD1</span></span>  
 <span data-ttu-id="64432-118">Se viene fornito <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> come parametro costruttore, l'implementazione utilizzerà la versione 1 della bozza del comitato del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-118">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="64432-119">Questa versione del protocollo deve essere usata per interoperare con le implementazioni che eseguono la versione CD1 del protocollo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="64432-119">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="64432-120">Supporto di più endpoint di individuazione UDP per varie versioni per l'individuazione su un solo host del servizio</span><span class="sxs-lookup"><span data-stu-id="64432-120">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>  
 <span data-ttu-id="64432-121">Potrebbe risultare opportuno esporre più endpoint di individuazione UDP per varie versioni per l'individuazione su un solo host del servizio.</span><span class="sxs-lookup"><span data-stu-id="64432-121">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="64432-122">A tale scopo è necessario specificare un indirizzo univoco per ogni endpoint di individuazione UDP.</span><span class="sxs-lookup"><span data-stu-id="64432-122">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="64432-123">Nell'esempio seguente viene illustrato come effettuare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="64432-123">The following example shows how to do this.</span></span>  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
