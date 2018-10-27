---
title: Interoperabilità con applicazioni POX
ms.date: 03/30/2017
ms.assetid: 449276b8-4633-46f0-85c9-81f01d127636
ms.openlocfilehash: b7fdb4e16bce52025515ced065d0f48cffb7fa3f
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50036021"
---
# <a name="interoperability-with-pox-applications"></a>Interoperabilità con applicazioni POX

"Plain Old XML" applicazioni (POX) comunicano scambiando messaggi HTTP non elaborati che contengono solo dati di applicazioni XML non inclusi all'interno di una SOAP envelope. Windows Communication Foundation (WCF) può fornire servizi e client che utilizzano messaggi POX. Nel servizio, WCF è utilizzabile per implementare servizi che espongono endpoint a client, ad esempio i browser Web e linguaggi di scripting che inviano e ricevono messaggi POX. Sul client, il modello di programmazione WCF è utilizzabile per implementare i client che comunicano con servizi basati su POX.  
  
> [!NOTE]
> Questo documento è stato scritto originariamente per [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.0.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 3.5 dispone di supporto incorporato per l'utilizzo di applicazioni POX. Per altre informazioni, vedere [modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).
  
## <a name="pox-programming-with-wcf"></a>Programmazione POX con WCF

I servizi WCF che comunicano su HTTP tramite messaggi POX utilizzano un' [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).

```xml
<customBinding>
   <binding name="poxServerBinding">
       <textMessageEncoding messageVersion="None" />
       <httpTransport />
   </binding>
</customBinding>
```

Questa associazione personalizzata contiene due elementi:

- [\<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)

- [\<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)

Lo standard di codificatore di messaggi di testo di WCF è configurato per l'utilizzo di <xref:System.ServiceModel.Channels.MessageVersion.None%2A> valore, che consente di elaborare payload di messaggi XML che non arrivano incapsulati in una SOAP envelope.

I client WCF che comunicano su HTTP tramite messaggi POX utilizzano un'associazione simile (illustrata nel codice imperativo seguente).

```csharp
private static Binding CreatePoxBinding()
{
    TextMessageEncodingBindingElement encoder =
        new TextMessageEncodingBindingElement( MessageVersion.None, Encoding.UTF8 );
    HttpTransportBindingElement transport = new HttpTransportBindingElement();
    transport.ManualAddressing = true;
    return new CustomBinding( new BindingElement[] { encoder, transport } );
}
```

Poiché i client POX devono specificare in modo esplicito gli URI ai quali inviano messaggi, devono in genere configurare <xref:System.ServiceModel.Channels.HttpTransportBindingElement> come modalità di indirizzamento manuale impostando la proprietà <xref:System.ServiceModel.Channels.TransportBindingElement.ManualAddressing%2A> su `true` nell'elemento. Ciò consente ai messaggi di essere indirizzati in modo esplicito dal codice dell'applicazione e non sarà quindi necessario creare un nuovo <xref:System.ServiceModel.ChannelFactory> ogni volta che un'applicazione invia un messaggio a un URI HTTP diverso.

Poiché i messaggi POX non utilizzano intestazioni SOAP per trasmettere informazioni importanti sul protocollo, i client e i servizi POX spesso devono modificare parti della richiesta HTTP sottostante utilizzata per inviare o ricevere un messaggio. Informazioni sul protocollo HTTP-specifiche, ad esempio le intestazioni HTTP e i codici di stato vengono rilevate nel modello di programmazione WCF di due classi:

- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> che contiene informazioni sulla richiesta HTTP, ad esempio le intestazioni di metodo e di richiesta HTTP.

- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty> che contiene informazioni sulla risposta HTTP, ad esempio il codice di stato e la descrizione dello stato HTTP, come pure qualsiasi intestazione di risposta HTTP.
  
Esempio di codice seguente viene illustrato come creare un messaggio di richiesta HTTP GET indirizzato a `http://localhost:8100/customers`.

```csharp
Message request = Message.CreateMessage( MessageVersion.None, String.Empty );
request.Headers.To = "http://localhost:8100/customers";

HttpRequestMessageProperty property = new HttpRequestMessageProperty();
property.Method = "GET";
property.SuppressEntityBody = true;
request.Properties.Add( HttpRequestMessageProperty.Name, property );
```

In primo luogo viene creata una richiesta vuota <xref:System.ServiceModel.Channels.Message> chiamando <xref:System.ServiceModel.Channels.Message.CreateMessage%28System.ServiceModel.Channels.MessageVersion%2CSystem.String%29>. Il parametro <xref:System.ServiceModel.Channels.MessageVersion.None%2A> viene utilizzato per indicare che non è necessaria una SOAP envelope e il parametro <xref:System.String.Empty> viene passato come Action. Il messaggio di richiesta viene quindi indirizzato impostando l'intestazione <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> sull'URI desiderato. Viene quindi creato <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.Method%2A> viene impostato sul metodo del verbo HTTP GET e <xref:System.ServiceModel.Channels.HttpRequestMessageProperty.SuppressEntityBody%2A> viene impostato su `true` per indicare che nessun dato deve essere inviato nel corpo del messaggio di richiesta HTTP in uscita. Infine la proprietà della richiesta viene aggiunta alla raccolta <xref:System.ServiceModel.Channels.Message.Properties%2A> del messaggio di richiesta in modo da influire sull'invio della richiesta da parte del trasporto HTTP. Il messaggio è quindi pronto per essere inviato su un'istanza appropriata di <xref:System.ServiceModel.Channels.IRequestChannel>.

È possibile utilizzare tecniche simili nel servizio per estrarre <xref:System.ServiceModel.Channels.HttpRequestMessageProperty> da un messaggio in ingresso e creare una risposta.
