---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 6b44f63d20e0e2ed0d2486003b15a932ba939f55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670235"
---
# <a name="wsdualhttpbinding"></a>\<wsDualHttpBinding>
Definisce un'associazione protetta, affidabile e interoperabile adatta per contratti di servizio duplex o per la comunicazione tramite intermediari SOAP.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<wsDualHttpBinding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|bypassProxyOnLocal|Valore booleano che indica se ignorare il server proxy per indirizzi locali. Il valore predefinito è `false`.|  
|clientBaseAddress|URI che imposta l'indirizzo di base che il client ascolta per i messaggi di risposta dal servizio. Se viene specificato, questo indirizzo (più un GUID per ogni canale) viene usato per l'ascolto. Se il valore non viene specificato, l'indirizzo di base del client viene generato in un modo specifico del trasporto. Il valore predefinito è `null`.|  
|closeTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|hostnameComparisonMode|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI. Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.|  
|maxBufferPoolSize|Numero intero che specifica la dimensione del pool di buffer massima per questa associazione. Il valore predefinito è 524.288 byte (512 * 1024). Molte parti di Windows Communication Foundation (WCF) usano buffer. La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer. Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool. In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.|  
|maxReceivedMessageSize|Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore SOAP. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536.|  
|messageEncoding|Definisce il codificatore usato per codificare il messaggio. Di seguito vengono elencati i valori validi:<br /><br /> -Text: Usare un codificatore di messaggi di testo.<br />-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).<br />-Il valore predefinito è testo.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.|  
|name|Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|proxyAddress|URI che specifica l'indirizzo del proxy HTTP. Se `useDefaultWebProxy` è `true`, questa impostazione deve essere `null`. Il valore predefinito è `null`.|  
|receiveTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|sendTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|textEncoding|Imposta la codifica del set di caratteri da usare per l'emissione dei messaggi nell'associazione. Di seguito vengono elencati i valori validi:<br /><br /> -BigEndianUnicode: Codifica Unicode BigEndian.<br />-Unicode: codifica a 16 bit.<br />-UTF8: codifica a 8 bit<br /><br /> L'impostazione predefinita è UTF8. L'attributo è di tipo <xref:System.Text.Encoding>.|  
|transactionFlow|Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions. Il valore predefinito è `false`.|  
|useDefaultWebProxy|Valore booleano che indica se viene usato il proxy HTTP di sistema configurato automaticamente. L'indirizzo proxy deve essere `null`, ovvero non deve essere impostato, se l'attributo è `true`. Il valore predefinito è `true`.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsdualhttpbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="remarks"></a>Note  
 `WSDualHttpBinding` fornisce lo stesso supporto per i protocolli di servizi Web di `WSHttpBinding`, ma esclusivamente per l'uso con contratti duplex. `WSDualHttpBinding` supporta solo la sicurezza SOAP e richiede un sistema di messaggistica affidabile. Per questa associazione è necessario che il client disponga di un URI pubblico che fornisca un endpoint di callback per il servizio. A tale scopo, usare l'attributo `clientBaseAddress`. Un'associazione duale espone l'indirizzo IP del client al servizio. Nel client è necessario implementare un meccanismo di sicurezza in grado di garantire che il client si connetta solo a servizi ritenuti attendibili.  
  
 Questa associazione può essere usata per comunicare in modo affidabile attraverso uno o più intermediari SOAP.  
  
 Per impostazione predefinita, questa associazione genera uno stack di runtime con WS-ReliableMessaging per l'affidabilità, WS-Security per la sicurezza del messaggio e l'autenticazione, HTTP per il recapito dei messaggi e una codifica messaggi Text/XML.  
  
## <a name="example"></a>Esempio  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
