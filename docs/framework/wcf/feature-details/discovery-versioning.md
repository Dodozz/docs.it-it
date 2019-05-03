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
# <a name="discovery-versioning"></a>Controllo delle versioni per l'individuazione
In questo argomento viene fornita una breve panoramica dell'implementazione di alcune nuove funzionalità di individuazione. Vengono inoltre forniti cenni preliminari sulla scelta della versione dell'individuazione da usare.  
  
## <a name="discovery-versioning"></a>Controllo delle versioni per l'individuazione  
 La funzionalità di individuazione include il supporto per tre versioni del protocollo WS_Discovery. Le interfacce API di individuazione consentono di selezionare la versione del protocollo che si desidera usare. Questo documento contiene brevi descrizioni sulle impostazioni correlate al controllo delle versioni.  
  
 Le classi di individuazione seguenti dispongo ora di una proprietà <xref:System.ServiceModel.Discovery.DiscoveryVersion> e usano un argomento <xref:System.ServiceModel.Discovery.DiscoveryVersion> nei propri costruttori:  
  
-   <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
-   <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a>DiscoveryVersion.WSDiscoveryApril2005  
 Fornendo <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> come costruttore di parametro, l'implementazione utilizzerà la versione April2005 del protocollo WS-Discovery. Questa versione corrisponde alla versione pubblicata della specifica del protocollo di WS-Discovery e deve essere usata per interoperare con l'applicazione legacy che usa la versione April2005 di WS-Discovery.  
  
### <a name="discoveryversionwsdiscovery11"></a>DiscoveryVersion.WSDiscovery11  
 La versione di individuazione predefinita usata per le API è <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>. Si tratta della versione standardizzata corrente del protocollo di WS-Discovery.  
  
## <a name="discoveryversionwsdiscoverycd1"></a>DiscoveryVersion.WSDiscoveryCD1  
 Se viene fornito <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> come parametro costruttore, l'implementazione utilizzerà la versione 1 della bozza del comitato del protocollo WS-Discovery. Questa versione del protocollo deve essere usata per interoperare con le implementazioni che eseguono la versione CD1 del protocollo WS-Discovery.  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a>Supporto di più endpoint di individuazione UDP per varie versioni per l'individuazione su un solo host del servizio  
 Potrebbe risultare opportuno esporre più endpoint di individuazione UDP per varie versioni per l'individuazione su un solo host del servizio. A tale scopo è necessario specificare un indirizzo univoco per ogni endpoint di individuazione UDP. Nell'esempio seguente viene illustrato come effettuare questa operazione.  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
