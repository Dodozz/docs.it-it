---
title: <netTcpContextBinding>
ms.date: 03/30/2017
ms.assetid: 1d4715e1-5fff-4c3d-a226-18f21d0b30c4
ms.openlocfilehash: 35a7f322a38135ae2f728993f29b570c1fa94e8d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783461"
---
# <a name="nettcpcontextbinding"></a>\<netTcpContextBinding>
Specifica un contesto per l'associazione <xref:System.ServiceModel.NetTcpBinding> che richiede che il livello di protezione sia Sign. Il meccanismo contextExchangeMechanism dell'associazione NetTcpContextBinding è SOAPHeader.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netTcpContextBinding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netTcpContextBinding>
  <binding closeTimeout="TimeSpan"
           contextProtectionLevel="EncryptAndSign/None/Sign"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="String"
                 defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 defaultRealm="String" />
      <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpContextBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|closeTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|contextProtectionLevel|Valore valido dell'elemento <xref:System.Net.Security.ProtectionLevel> che specifica il livello di protezione desiderato dell'intestazione SOAP usata per propagare le informazioni sul contesto.  Il valore predefinito è <xref:System.Net.Security.ProtectionLevel.Sign>.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI. Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.|  
|listenBacklog|Numero intero positivo che specifica il numero massimo di canali di attesa accettati nel listener. Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito. L'attributo `connectionTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione. Il valore predefinito è 10.|  
|maxBufferPoolSize|Numero intero che specifica la dimensione del pool di buffer massima per questa associazione. Il valore predefinito è 512 * 1024 byte. Molte parti di Windows Communication Foundation (WCF) usano buffer. La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer. Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool. In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.|  
|maxBufferSize|Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria. Se il buffer è pieno, i dati in eccesso rimangono nel socket sottostante fino a che non è di nuovo disponibile spazio nel buffer. Questo valore non può essere inferiore a `maxReceivedMessageSize`. Il valore predefinito è 65536. Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|maxConnections|Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà. Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.<br /><br /> Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.<br /><br /> Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.<br /><br /> Il valore predefinito è 10.|  
|maxReceivedMessageSize|Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore SOAP. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536.|  
|name|Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|portSharingEnabled|Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione. Se è `false`, ciascuna associazione usa la propria porta esclusiva. Questa impostazione è appropriata solo per i servizi in quanto non ha effetto per i client.|  
|receiveTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:10:00.|  
|sendTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|transactionFlow|Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions. Il valore predefinito è `false`.|  
|transactionProtocol|Specifica il protocollo di transazione da usare con questa associazione. I valori validi sono:<br /><br /> -OleTransactions<br />-   WSAtomicTransactionOctober2004<br /><br /> L'impostazione predefinita è OleTransactions. L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.|  
|transferMode|Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.NetTcpContextBinding>
- <xref:System.ServiceModel.Configuration.NetTcpContextBindingElement>
- <xref:System.ServiceModel.Channels.ContextBindingElement>
- [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
