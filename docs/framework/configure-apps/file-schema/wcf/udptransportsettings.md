---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: f5be9681dc69fd68dfdfa90f4eb305dc4aa4514b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788752"
---
# <a name="udptransportsettings"></a>\<udpTransportSettings>
Questo elemento di configurazione espone le impostazioni di trasporto UDP per [ \<udpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md).  
  
\<system.ServiceModel>  
\<standardEndpoints>  
\<udpDiscoveryEndpoint>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|Integer che specifica il numero massimo di hash del messaggio usati dal trasporto per l'identificazione di messaggi duplicati.  Il rilevamento dei duplicati verrà eseguito al livello TransportManager. L'impostazione di questa proprietà su 0 disabilita il rilevamento di messaggi duplicati.<br /><br /> Questo attributo consente a sviluppatori e amministratori di sistema di disattivare gli algoritmi per il rilevamento di messaggi duplicati. È possibile che si desideri disattivare questa funzionalità per implementare un algoritmo di rilevamento dei duplicati personalizzato.<br /><br /> Il valore predefinito è 4112.|  
|maxBufferPoolSize|Integer che specifica le dimensioni massime dei pool di buffer usati dal trasporto.|  
|maxMulticastRetransmitCount|Integer che specifica il numero massimo di volte in cui il messaggio unicast deve essere ritrasmesso (oltre al primo invio).<br /><br /> Il valore predefinito è 2.|  
|maxPendingMessageCount|Integer che specifica il numero massimo di messaggi ricevuti ma non ancora rimossi da InputQueue per una singola istanza di canale.  Se InputQueue ha raggiunto il limite massimo di messaggi in sospeso, il messaggio verrà eliminato.<br /><br /> Il valore predefinito è 32.|  
|maxReceivedMessageSize|Integer che specifica le dimensioni massime di un messaggio che può essere elaborato dall'associazione.<br /><br /> Il valore predefinito è 65507.|  
|maxUnicastRetransmitCount|Integer che specifica il numero massimo di volte in cui il messaggio unicast deve essere ritrasmesso (oltre al primo invio).  Se il messaggio viene inviato a un indirizzo unicast e un messaggio di risposta viene ricevuto con un'intestazione RelatesTo corrispondente, la ritrasmissione può terminare prima che il messaggio venga ritrasmesso il numero di volte configurato.<br /><br /> Il valore predefinito è 1.|  
|multicastInterfaceId|Stringa che identifica in modo univoco la scheda di rete da usare durante l'invio e la ricezione di traffico multicast in computer multihomed. In fase di runtime il trasporto utilizzerà questo valore di attributo per individuare l'indice dell'interfaccia usata per impostare le opzioni del socket `IP_MULTICAST_IF` e `IPV6_MULTICAST_IF`.  Lo stesso indice dell'interfaccia verrà usato per l'unione di un gruppo multicast, se applicabile.<br /><br /> Il valore predefinito è `null`.|  
|socketReceiveBufferSize|Integer che specifica le dimensioni del buffer di ricezione nel socket WinSock sottostante.<br /><br /> Un utente di un canale di ricezione può usare questo attributo nell'associazione per controllare il comportamento del sistema alla ricezione dei dati.  Ad esempio, per un'applicazione che usa messaggi WCF in ingresso alla soglia massima, l'uso di un valore superiore per questo attributo consentirebbe ai messaggi di posizionarsi nel buffer WinSock in attesa che l'applicazione sia in grado di elaborarli.  L'utilizzo di un valore inferiore nella stessa situazione comporterebbe il rilascio dei messaggi. Questo attributo espone WinSock sottostante `SO_RCVBUF` opzione socket. Valore di questo attributo deve essere almeno la dimensione di `maxReceivedMessageSize`.   Impostandola su un valore minore di `maxReceivedMessageSize` comporterà un'eccezione di runtime.<br /><br /> Il valore predefinito è 65536.|  
|timeToLive|Integer che specifica il numero di hop dei segmenti di rete che un pacchetto multicast può attraversare.  Questo attributo espone la funzionalità associata alle opzioni del socket `IP_MULTICAST_TTL` e `IP_TTL`.<br /><br /> Il valore predefinito è 1.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<udpDiscoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Endpoint standard che dispone di un contratto di individuazione e di un'associazione del trasporto UDP fissi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
