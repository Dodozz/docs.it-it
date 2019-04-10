---
title: 'Procedura: Usare la sicurezza del trasporto e le credenziali per il messaggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f9c90ac93a27f90479ee7225f62afb98a5000fe9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321478"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a>Procedura: Usare la sicurezza del trasporto e le credenziali per il messaggio
Protezione di un servizio con le credenziali di trasporto e messaggio utilizza il meglio delle modalità di sicurezza di trasporto e messaggio di Windows Communication Foundation (WCF). Complessivamente, le funzionalità di sicurezza a livello di trasporto garantiscono integrità e riservatezza, mentre le funzionalità di sicurezza a livello di messaggio offrono vari tipi di credenziali non disponibili quando si utilizzano meccanismi di sicurezza basati esclusivamente sul livello di trasporto. In questo argomento vengono illustrati i passaggi di base per implementare il trasporto con credenziali messaggio utilizzando le associazioni <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.NetTcpBinding>. Per altre informazioni sull'impostazione della modalità di sicurezza, vedere [come: Impostare la modalità di sicurezza](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).  
  
 Quando si imposta la modalità di sicurezza su `TransportWithMessageCredential`, il trasporto determina il meccanismo di sicurezza a livello di trasporto effettivamente utilizzato. Nel caso del protocollo HTTP, il meccanismo è Secure Sockets Layer (SSL) su HTTP (HTTPS). Nel caso del protocollo TCP, invece, il meccanismo è SSL su TCP oppure Windows.  
  
 Se il trasporto è HTTP (tramite l'associazione <xref:System.ServiceModel.WSHttpBinding>), il protocollo HTTPS fornisce la protezione a livello di trasporto. In tal caso è necessario configurare il computer che ospita il servizio con un certificato SSL associato a una porta, come mostrato in seguito in questo argomento.  
  
 Se il trasporto è TCP (tramite l'associazione <xref:System.ServiceModel.NetTcpBinding>), per impostazione predefinita la protezione a livello di trasporto fornita è la protezione di Windows oppure SSL su TCP. Quando si utilizza SSL su TCP è necessario utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> per specificare il certificato, come mostrato in seguito in questo argomento.  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a>Per utilizzare l'associazione WSHttpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)  
  
1. Usare lo strumento HttpCfg.exe per associare un certificato SSL a una porta del computer. Per altre informazioni, vedere [Procedura: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
2. Creare un'istanza della classe <xref:System.ServiceModel.WSHttpBinding> e impostare la proprietà <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.  
  
3. Impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> su un valore appropriato. (Per altre informazioni, vedere [la selezione di un tipo di credenziale](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.  
  
4. Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato. Si noti che l'indirizzo deve utilizzare lo schema "HTTPS" e deve contenere il nome effettivo del computer e il numero della porta a cui il certificato SSL è associato. In alternativa è possibile impostare l'indirizzo di base in configurazione.  
  
5. Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
6. Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost> e chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a>Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto (in codice)  
  
1. Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.  
  
2. Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato. Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.  
  
3. Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato. Si noti che l'indirizzo deve utilizzare lo schema "net.tcp". In alternativa è possibile impostare l'indirizzo di base in configurazione.  
  
4. Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.  
  
5. Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.  
  
6. Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
7. Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a>Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto (in codice)  
  
1. Creare un'istanza della classe <xref:System.ServiceModel.NetTcpBinding> e impostare la proprietà <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> su <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.  
  
2. Impostare la protezione a livello di trasporto in modo che utilizzi Windows. A tale scopo, impostare la proprietà <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> su <xref:System.ServiceModel.TcpClientCredentialType.Windows>. Si noti che questo valore è l'impostazione predefinita.  
  
3. Impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> su un valore appropriato. Nel codice seguente viene utilizzato il valore <xref:System.ServiceModel.MessageCredentialType.Certificate>.  
  
4. Creare un'istanza della classe <xref:System.Uri> con un indirizzo di base appropriato. Si noti che l'indirizzo deve utilizzare lo schema "net.tcp". In alternativa è possibile impostare l'indirizzo di base in configurazione.  
  
5. Creare l'istanza della classe <xref:System.ServiceModel.ServiceHost>.  
  
6. Utilizzare il metodo <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> per impostare in modo esplicito il certificato X.509 del servizio.  
  
7. Aggiungere un endpoint di servizio tramite il metodo <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
8. Chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A>, come mostrato nel codice seguente.  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a>Utilizzo della configurazione  
  
#### <a name="to-use-the-wshttpbinding"></a>Per utilizzare l'associazione WSHttpBinding  
  
1. Configurare il computer con un certificato SSL associato a una porta. (Per altre informazioni, vedere [come: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)). Non è necessario impostare una <`transport`> valore dell'elemento con questa configurazione.  
  
2. Specificare il tipo di credenziale client della protezione a livello di messaggio. L'esempio seguente imposta la `clientCredentialType` attributo del <`message`> elemento `UserName`.  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a>Per utilizzare l'associazione NetTcpBinding con un certificato allo scopo di fornire la protezione a livello di trasporto  
  
1. Nel caso di SSL su TCP occorre specificare in modo esplicito il certificato nell'elemento `<behaviors>`. Nell'esempio seguente viene individuato un certificato in base alla relativa autorità emittente nel percorso di archivio predefinito (archivio locale del computer e archivio personale).  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. Aggiungere un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione delle associazioni  
  
3. Aggiungere un elemento di associazione e quindi impostare l'attributo `name` su un valore appropriato.  
  
4. Aggiungere un <`security`> e impostare il `mode` dell'attributo `TransportWithMessageCredential`.  
  
5. Aggiungere un <`message>` e impostare il `clientCredentialType` attributo su un valore appropriato.  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a>Per utilizzare l'associazione NetTcpBinding con Windows allo scopo di fornire la protezione a livello di trasporto  
  
1. Aggiungere un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) alla sezione delle associazioni,  
  
2. Aggiungere un <`binding`> e impostare il `name` attributo su un valore appropriato.  
  
3. Aggiungere un <`security`> e impostare il `mode` dell'attributo `TransportWithMessageCredential`.  
  
4. Aggiungere un <`transport`> e impostare il `clientCredentialType` dell'attributo `Windows`.  
  
5. Aggiungere un <`message`> e impostare il `clientCredentialType` attributo su un valore appropriato. Nel codice seguente il valore viene impostato su un certificato.  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Impostare la modalità di sicurezza](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)
- [Protezione dei servizi](../../../../docs/framework/wcf/securing-services.md)
- [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
