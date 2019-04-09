---
title: Uso di NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 5090cfdfeb068acda1e1092e408f3cd747c574c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121017"
---
# <a name="using-the-nethttpbinding"></a>Uso di NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> è un'associazione progettata per utilizzare i servizi HTTP o WebSocket e Usa la codifica binaria per impostazione predefinita. <xref:System.ServiceModel.NetHttpBinding> rileverà se viene utilizzato con un contratto request / reply o un contratto duplex e modificherà il comportamento di corrispondenza - utilizzerà HTTP per i contratti request / reply e WebSockets per i contratti duplex. È possibile eseguire l'override di questo comportamento usando l'impostazione <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> -Forza WebSocket per essere usato anche per i contratti request / reply.  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> -Ciò impedisce l'utilizzo WebSockets. Il tentativo di utilizzo di un contratto duplex con questa impostazione genererà un'eccezione.  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> -Questo è il valore predefinito e si comporta come descritto in precedenza.  
  
 <xref:System.ServiceModel.NetHttpBinding> supporta sessioni affidabili in modalità HTTP sia in modalità WebSocket. Nella modalità WebSocket, le sessioni vengono fornite dal trasporto.  
  
> [!WARNING]
>  Quando si usa <xref:System.ServiceModel.NetHttpBinding> e l'elemento TransferMode dell'associazione è impostato su TransferMode.Streamed, i flussi di grandi dimensioni possono causare un deadlock e quindi il timeout della chiamata. Per risolvere il problema inviare messaggi più piccoli o usare TransferMode.Buffered.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>Configurazione dell'utilizzo di NetHttpBinding in un servizio  
 L'endpoint <xref:System.ServiceModel.NetHttpBinding> può essere configurato come qualsiasi altra associazione. Nel frammento di configurazione seguente è illustrato come configurare un servizio WCF con <xref:System.ServiceModel.NetHttpBinding>.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 Nel frammento di codice seguente viene illustrato come aggiungere l'oggetto <xref:System.ServiceModel.NetHttpBinding> nel codice.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione delle associazioni per i servizi](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Associazioni](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Servizi duplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)
