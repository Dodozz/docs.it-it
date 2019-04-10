---
title: Guida rapida alla risoluzione dei problemi di WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], troubleshooting
- Windows Communication Foundation [WCF], troubleshooting
ms.assetid: a9ea7a53-f31a-46eb-806e-898e465a4992
ms.openlocfilehash: 4327e8bb07cb03a91f7384f7fe82bc2e47f6fcb9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320002"
---
# <a name="wcf-troubleshooting-quickstart"></a>Guida rapida alla risoluzione dei problemi di WCF
In questo argomento viene elencata una serie di problemi noti rilevati dai clienti durante lo sviluppo di client e servizi WCF. Se il problema rilevato non presente in questo elenco, si consiglia di configurare la traccia del servizio. In tal modo verrà generato un file di traccia che è possibile visualizzare con il visualizzatore dei file di traccia e verranno ricevute informazioni dettagliate sulle eccezioni che si possono verificare nel servizio. Per altre informazioni sulla configurazione della traccia, vedere: [Configurazione della traccia](../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md). Per altre informazioni sul Visualizzatore dei file di traccia, vedere: [Strumento Visualizzatore di tracce (SvcTraceViewer.exe) del servizio](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).  
  
1. [Dopo aver installato Windows 7 e IIS, quando tenta di passare a un servizio WCF viene visualizzato il messaggio di errore seguente: Errore HTTP 404.3 – non trovato](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#bkmk_0)  
  
     Errore HTTP 404.3 - La pagina richiesta non può essere servita a causa della configurazione estensioni. Se la pagina è uno script, aggiungere un gestore. Se il file deve essere scaricato, aggiungere una mappa MIME. Errore dettagliato InformationModule StaticFileModule.  
  
2. [A volte viene restituita un'eccezione MessageSecurityException alla seconda richiesta se il client è inattivo per un periodo di tempo dopo la prima richiesta. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q1)  
  
3. [Il servizio rifiuta nuovi client se sta interagendo già con 10 client. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q2)  
  
4. [È possibile caricare la configurazione del servizio da una posizione diversa dal file di configurazione dell'applicazione WCF?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q3)  
  
5. [Il servizio e il client funzionano correttamente, ma quando il client è in un altro computer non funzionano più. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q4)  
  
6. [Quando genera un'eccezione FaultException\<eccezione > in cui il tipo è un'eccezione, viene restituito sempre un tipo FaultException generale sul client e non il tipo generico. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q5)  
  
7. [Sembra che le operazioni unidirezionali e request-reply vengano restituite approssimativamente alla stessa velocità quando la risposta non contiene dati. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q6)  
  
8. [Utilizzando un certificato X.509 con il servizio viene generata un'eccezione System.Security.Cryptography.CryptographicException. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q77)  
  
9. [In seguito alla modifica del primo parametro di un'operazione di passaggio da lettere maiuscole a lettere minuscole, il client genera un'eccezione. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q88)  
  
10. [Utilizzando uno degli strumenti di traccia, viene generata un'eccezione EndpointNotFoundException. Qual è il problema?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q99)  
  
11. [Quando si chiama un'applicazione HTTP Web WCF da un'applicazione SOAP WCF il servizio restituisce l'errore seguente: 405 metodo non consentito](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BK_MK99)  
  
 [Quale è l'indirizzo di base? In che modo è correlato a un indirizzo dell'endpoint?](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md#BKMK_q10)  
  
<a name="bkmk_0"></a>   
## <a name="after-installing-windows-7-and-iis-when-i-attempt-to-browse-to-a-wcf-service-i-get-the-following-error-message-http-error-4043--not-found"></a>Dopo aver installato Windows 7 e IIS, quando tenta di passare a un servizio WCF viene visualizzato il messaggio di errore seguente: Errore HTTP 404.3 – non trovato  
 Il messaggio di errore completo è:  
  
 Errore HTTP 404.3 - La pagina richiesta non può essere servita a causa della configurazione estensioni. Se la pagina è uno script, aggiungere un gestore. Se il file deve essere scaricato, aggiungere una mappa MIME. Errore dettagliato InformationModule StaticFileModule.  
  
 Questo messaggio di errore si verifica quando "Attivazione HTTP di Windows Communication Foundation" non è impostato in modo esplicito nel Pannello di controllo. Per effettuare questa impostazione accedere al Pannello di controllo e fare clic su Programmi e funzionalità nell'angolo in basso a sinistra della finestra. Fare clic su Attivazione o disattivazione delle funzionalità Windows. Espandere Microsoft .NET Framework 3.5.1. e selezionare Windows Communication Foundation HTTP Activation.  
  
<a name="BKMK_q1"></a>   
## <a name="sometimes-i-receive-a-messagesecurityexception-on-the-second-request-if-my-client-is-idle-for-a-while-after-the-first-request-what-is-happening"></a>A volte viene restituita un'eccezione MessageSecurityException alla seconda richiesta se il client è inattivo per un periodo di tempo dopo la prima richiesta. Qual è il problema?  
 La seconda richiesta può non riuscire principalmente per due motivi: (1) la sessione è scaduta o (2) il server Web che ospita il servizio viene riciclato. Nel primo caso, la sessione è valida fino al timeout del servizio. Quando il servizio non riceve una richiesta dal client entro il periodo di tempo specificato nell'associazione del servizio (<xref:System.ServiceModel.Channels.Binding.ReceiveTimeout%2A>), il servizio termina la sessione di sicurezza. I messaggi client successivi determinano l'eccezione <xref:System.ServiceModel.Security.MessageSecurityException>. Il client deve ristabilire una sessione protetta con il servizio per inviare altri messaggi o utilizzare un token del contesto di sicurezza con stato. I token del contesto di sicurezza con stato consentono inoltre a una sessione protetta di restare attiva quando un server Web viene riciclato. Per altre informazioni sull'uso dei token di contesto di sicurezza con stato in una sessione protetta, vedere [come: Creare un contesto di sicurezza Token per una sessione protetta](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md). In alternativa, è possibile disabilitare le sessioni protette. Quando si usa la [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) associazione, è possibile impostare il `establishSecurityContext` proprietà `false` disattivare sessioni protette. Per disabilitare le sessioni protette per altre associazioni, è necessario creare un'associazione personalizzata. Per informazioni dettagliate sulla creazione di un'associazione personalizzata, vedere [come: Creare un'associazione personalizzata usando SecurityBindingElement](../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md). Prima di applicare qualsiasi opzione, è necessario conoscere i requisiti di sicurezza dell'applicazione.  
  
<a name="BKMK_q2"></a>   
## <a name="my-service-starts-to-reject-new-clients-after-about-10-clients-are-interacting-with-it-what-is-happening"></a>Il servizio rifiuta nuovi client se sta interagendo già con 10 client. Qual è il problema?  
 Per impostazione predefinita, i servizi possono gestire solo 10 sessioni simultanee. Pertanto, se le associazioni del servizio utilizzano sessioni, il servizio accetta nuove connessioni client fino a raggiungere quel numero e in seguito rifiuta le nuove connessioni client fino a quando una delle sessioni correnti non viene chiusa. È possibile supportare più client in vari modi. Se il servizio non richiede le sessioni, non utilizzare un'associazione con sessione. (Per altre informazioni, vedere [utilizzando le sessioni](../../../docs/framework/wcf/using-sessions.md).) Un'altra opzione consiste nell'incrementare il limite di sessioni impostando il valore della proprietà <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A> sul numero adatto alla circostanza.  
  
<a name="BKMK_q3"></a>   
## <a name="can-i-load-my-service-configuration-from-somewhere-other-than-the-wcf-applications-configuration-file"></a>È possibile caricare la configurazione del servizio da una posizione diversa dal file di configurazione dell'applicazione WCF?  
 È possibile, tuttavia è necessario creare una classe <xref:System.ServiceModel.ServiceHost> personalizzata che esegue l'override del metodo <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> . All'interno di tale metodo è possibile chiamare la base per caricare la prima configurazione (se si desidera caricare anche le informazioni di configurazione standard), ma si può anche sostituire completamente il sistema di caricamento della configurazione. Si noti che se si desidera caricare la configurazione da un file di configurazione diverso dal quello dell'applicazione, è necessario analizzare direttamente il file di configurazione e caricare la configurazione.  
  
 Nell'esempio di codice seguente viene illustrato come eseguire l'override del metodo <xref:System.ServiceModel.ServiceHostBase.ApplyConfiguration%2A> e configurare direttamente un endpoint.  
  
```csharp
public class MyServiceHost : ServiceHost  
{  
    public MyServiceHost(Type serviceType, params Uri[] baseAddresses)    
      : base(serviceType, baseAddresses)  
    {
        Console.WriteLine("MyServiceHost Constructor");
    }  
  
    protected override void ApplyConfiguration()  
    {  
        string straddress = GetAddress();  
        Uri address = new Uri(straddress);  
        Binding binding = GetBinding();  
        base.AddServiceEndpoint(typeof(IData), binding, address);  
    }  
  
    string GetAddress()  
    {
        return "http://MyMachine:7777/MyEndpointAddress/";
    }  
  
    Binding GetBinding()  
    {  
        WSHttpBinding binding = new WSHttpBinding();  
        binding.Security.Mode = SecurityMode.None;  
        return binding;  
    }  
}  
```  
  
<a name="BKMK_q4"></a>   
## <a name="my-service-and-client-work-great-but-i-cant-get-them-to-work-when-the-client-is-on-another-computer-whats-happening"></a>Il servizio e il client funzionano correttamente, ma quando il client è in un altro computer non funzionano più. Qual è il problema?  
 In base all'eccezione, i problemi possono essere diversi:  
  
-   Potrebbe essere necessario modificare gli indirizzi dell'endpoint del client sul nome host anziché su "localhost".  
  
-   Potrebbe essere necessario aprire la porta all'applicazione. Per informazioni dettagliate, vedere [Firewall Instructions](../../../docs/framework/wcf/samples/firewall-instructions.md) negli esempi di SDK.  
  
-   Per altri possibili problemi, vedere l'argomento degli esempi [esegue gli esempi di Windows Communication Foundation](./samples/running-the-samples.md).  
  
-   Se il client sta utilizzando le credenziali di Windows e l'eccezione è <xref:System.ServiceModel.Security.SecurityNegotiationException>, configurare Kerberos come descritto di seguito.  
  
    1.  Aggiungere le credenziali di identificazione all'elemento dell'endpoint nel file App.config del client:  
  
        ```xml
        <endpoint   
          address="http://MyServer:8000/MyService/"   
          binding="wsHttpBinding"   
          bindingConfiguration="WSHttpBinding_IServiceExample"   
          contract="IServiceExample"   
          behaviorConfiguration="ClientCredBehavior"   
          name="WSHttpBinding_IServiceExample">  
          <identity>  
            <userPrincipalName value="name@corp.contoso.com"/>  
          </identity>  
        </endpoint>  
        ```  
  
    2.  Eseguire il servizio indipendente con l'account System o NetworkService. È possibile eseguire questo comando per creare una finestra di comando con l'account System:  
  
        ```console
        at 12:36 /interactive "cmd.exe"  
        ```  
  
    3.  Ospitare il servizio in Internet Information Services (IIS) che, per impostazione predefinita, utilizza l'account del nome dell'entità servizio (SPN).  
  
    4.  Registrare un nuovo SPN nel dominio utilizzando SetSPN. Si noti che è necessario essere un amministratore di dominio per poter eseguire questa operazione.  
  
 Per altre informazioni sul protocollo Kerberos, vedere [Security Concepts Used in WCF](../../../docs/framework/wcf/feature-details/security-concepts-used-in-wcf.md) e:  
  
-   [Debug degli errori di autenticazione di Windows](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
  
-   [Registrazione di nomi SPN Kerberos utilizzando Http.sys](https://go.microsoft.com/fwlink/?LinkId=86943)  
  
-   [Descrizione di Kerberos](https://go.microsoft.com/fwlink/?LinkId=86946)  
  
<a name="BKMK_q5"></a>   
## <a name="when-i-throw-a-faultexceptionexception-where-the-type-is-an-exception-i-always-receive-a-general-faultexception-type-on-the-client-and-not-the-generic-type-whats-happening"></a>Quando genera un'eccezione FaultException\<eccezione > in cui il tipo è un'eccezione, viene restituito sempre un tipo FaultException generale sul client e non il tipo generico. Qual è il problema?  
 È consigliabile creare un tipo di dati dell'errore personalizzato e dichiararlo come tipo di dettaglio nel contratto di errore. Ciò è necessario in quanto, se si utilizzano tipi di eccezione forniti dal sistema:  
  
-   Viene creata una dipendenza dal tipo che rimuove uno dei maggiori punti di forza delle applicazioni orientate ai servizi.  
  
-   Non è possibile dipendere dalla serializzazione delle eccezioni in modo standard. Alcuni casi, come <xref:System.Security.SecurityException>, potrebbero non essere affatto serializzabili.  
  
-   Vengono esposti dettagli di implementazione interni ai client. Per altre informazioni, vedere [se si specifica e gestione degli errori in contratti e servizi](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
 Se si sta eseguendo il debug di un'applicazione, tuttavia, è possibile serializzare le informazioni sull'eccezione e restituirle al client utilizzando la classe <xref:System.ServiceModel.Description.ServiceDebugBehavior> .  
  
<a name="BKMK_q6"></a>   
## <a name="it-seems-like-one-way-and-request-reply-operations-return-at-roughly-the-same-speed-when-the-reply-contains-no-data-whats-happening"></a>Sembra che le operazioni unidirezionali e request-reply vengano restituite approssimativamente alla stessa velocità quando la risposta non contiene dati. Qual è il problema?  
 Per operazione unidirezionale si intende che il contratto dell'operazione accetta un messaggio di input e non restituisce un messaggio di output. In WCF, tutte le chiamate client restituiscono quando i dati in uscita sono stato scritto per la trasmissione o viene generata un'eccezione. Le operazioni unidirezionali funzionano nello stesso modo e possono generare un'eccezione se il servizio non viene trovato o possono bloccarsi se il servizio non è pronto ad accettare i dati dalla rete. In genere in WCF, ciò comporta la restituzione al client più rapidamente request-reply; le chiamate unidirezionali ma qualsiasi condizione che rallenta l'invio dei dati in uscita sulla rete rallenta operazioni unidirezionali e le operazioni request-reply. Per altre informazioni, vedere [Services unidirezionale](../../../docs/framework/wcf/feature-details/one-way-services.md) e [accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
<a name="BKMK_q77"></a>   
## <a name="im-using-an-x509-certificate-with-my-service-and-i-get-a-systemsecuritycryptographycryptographicexception-whats-happening"></a>Utilizzando un certificato X.509 con il servizio viene generata un'eccezione System.Security.Cryptography.CryptographicException. Qual è il problema?  
 Questa situazione in genere si verifica dopo aver modificato l'account utente utilizzato per eseguire il processo di lavoro IIS. Ad esempio, in [!INCLUDE[wxp](../../../includes/wxp-md.md)], se si modifica l'account utente predefinito con cui si esegue Aspnet_wp.exe da ASPNET in un account utente personalizzato, è possibile che si verifichi questo errore. Se si utilizza una chiave privata, il processo che la utilizza dovrà disporre delle autorizzazioni per accedere al file in cui è archiviata tale chiave.  
  
 In questo caso, è necessario assegnare i privilegi di accesso in lettura all'account del processo per il file che contiene la chiave privata. Ad esempio, se il processo di lavoro IIS è in esecuzione con l'account Bob, è necessario assegnare a Bob l'accesso in lettura al file che contiene la chiave privata.  
  
 Per altre informazioni su come assegnare all'account utente corretto accesso al file che contiene la chiave privata per un certificato X.509 specifico, vedere [come: Rendere accessibili a WCF i certificati X.509](../../../docs/framework/wcf/feature-details/how-to-make-x-509-certificates-accessible-to-wcf.md).  
  
<a name="BKMK_q88"></a>   
## <a name="i-changed-the-first-parameter-of-an-operation-from-uppercase-to-lowercase-now-my-client-throws-an-exception-whats-happening"></a>In seguito alla modifica del primo parametro di un'operazione di passaggio da lettere maiuscole a lettere minuscole, il client genera un'eccezione. Qual è il problema?  
 Il valore dei nomi di parametro nella firma dell'operazione fa parte del contratto e supporta la distinzione tra maiuscole e minuscole. Utilizzare l'attributo <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType> quando è necessario distinguere tra il nome del parametro locale e i metadati che descrivono l'operazione per le applicazioni client.  
  
<a name="BKMK_q99"></a>   
## <a name="im-using-one-of-my-tracing-tools-and-i-get-an-endpointnotfoundexception-whats-happening"></a>Utilizzando uno degli strumenti di traccia, viene generata un'eccezione EndpointNotFoundException. Qual è il problema?  
 Se si usa uno strumento di traccia che non è il meccanismo di traccia fornite dal sistema WCF e si riceve un <xref:System.ServiceModel.EndpointNotFoundException> che indica che si è verificato una mancata corrispondenza del filtro indirizzo, è necessario usare il <xref:System.ServiceModel.Description.ClientViaBehavior> classe per indirizzare i messaggi all'utilità di traccia e dispone l'utilità reindirizzi tali messaggi all'indirizzo del servizio. La classe <xref:System.ServiceModel.Description.ClientViaBehavior> modifica l'intestazione di indirizzamento `Via` per specificare il successivo indirizzo di rete separatamente dal destinatario finale, indicato dall'intestazione di indirizzamento `To` . Durante questa modifica è importante tuttavia non modificare l'indirizzo dell'endpoint che viene utilizzato per stabilire il valore `To` .  
  
 Nell'esempio di codice seguente viene illustrato un file di configurazione client di esempio.  
  
```xml
<endpoint   
  address="http://localhost:8000/MyServer/"  
  binding="wsHttpBinding"  
  bindingConfiguration="WSHttpBinding_IMyContract"  
  behaviorConfiguration="MyClient"   
  contract="IMyContract"   
  name="WSHttpBinding_IMyContract">  
</endpoint>  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="MyClient">  
      <clientVia viaUri="http://localhost:8001/MyServer/"/>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
<a name="BKMK_q10"></a>   
## <a name="what-is-the-base-address-how-does-it-relate-to-an-endpoint-address"></a>Quale è l'indirizzo di base? In che modo è correlato a un indirizzo dell'endpoint?  
 Un indirizzo di base è l'indirizzo radice per una classe <xref:System.ServiceModel.ServiceHost> . Per impostazione predefinita, se si aggiunge una classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior> alla configurazione del servizio, il linguaggio di descrizione dei servizi Web (WSDL, Web Services Description Language) per tutti gli endpoint che l'host pubblica viene recuperato dall'indirizzo di base HTTP, oltre che da qualsiasi indirizzo relativo fornito al comportamento dei metadati, più "?wsdl". Se si ha familiarità con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e IIS, l'indirizzo di base è equivalente alla directory virtuale.  
  
## <a name="sharing-a-port-between-a-service-endpoint-and-a-mex-endpoint-using-the-nettcpbinding"></a>Condivisione di una porta tra un endpoint servizio e un endpoint MEX utilizzando NetTcpBinding  
 Se si specifica l'indirizzo di base per un servizio come net.tcp://MioServer:8080/MioServizio e si aggiungono gli endpoint seguenti:  
  
```xml  
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
 Se inoltre si modifica una delle impostazioni NetTcpBinding come illustrato nel frammento di configurazione seguente:  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="10" maxBufferPoolSize="524288" maxBufferSize="65536" maxConnections="11" maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384"/>  
      <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false"/>  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign"/>  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 Verrà visualizzato un errore simile al seguente: Eccezione non gestita: System.ServiceModel.AddressAlreadyInUseException: È già presente un listener su 0.0.0.0: 9000 endpoint IP che è possibile risolvere questo errore, specificando un URL completo con una porta diversa per l'endpoint MEX come illustrato nel frammento di configurazione seguenti:  
  
```xml
<services>  
  <service name="Microsoft.Samples.NetTcp.CalculatorService">  
    <endpoint address="calcsvc" binding ="netTcpBinding" contract="Microsoft.Samples.NetTcp.ICalculator"/>  
    <endpoint address="net.tcp://localhost:9001/servicemodelsamples/mex" binding="mexTcpBinding" contract="IMetadataExchange" />  
  </service>  
</services>  
```  
  
<a name="BK_MK99"></a>   
## <a name="when-calling-a-wcf-web-http-application-from-a-wcf-soap-application-the-service-returns-the-following-error-405-method-not-allowed"></a>Quando si chiama un'applicazione HTTP Web WCF da un'applicazione SOAP WCF il servizio restituisce l'errore seguente: 405 metodo non consentito  
 La chiamata a un'applicazione HTTP Web WCF (un servizio che usa il <xref:System.ServiceModel.WebHttpBinding> e <xref:System.ServiceModel.Description.WebHttpBehavior>) da un WCF service può generare l'eccezione seguente: `Unhandled Exception: System.ServiceModel.FaultException`1[System.ServiceModel.ExceptionDetail]: Il server remoto ha restituito una risposta non prevista: (405) metodo non consentito.' questa eccezione si verifica perché WCF sovrascrive in uscita <xref:System.ServiceModel.OperationContext> con la posta in arrivo <xref:System.ServiceModel.OperationContext>. Per risolvere questo problema, creare un oggetto <xref:System.ServiceModel.OperationContextScope> all'interno dell'operazione del servizio HTTP Web WCF. Ad esempio:  
  
```csharp
public string Echo(string input)  
{  
    using (new OperationContextScope(this.InnerChannel))  
    {  
        return base.Channel.Echo(input);  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Debug degli errori di autenticazione di Windows](../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)
