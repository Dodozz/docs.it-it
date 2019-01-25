---
title: Convalida client
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 3a80121894ddbb753efbe047d14a14a57f8dddc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640004"
---
# <a name="client-validation"></a>Convalida client
I servizi pubblicano spesso metadati per consentire la generazione e configurazione automatica di tipi di proxy client. Quando il servizio non è considerato attendibile, le applicazioni client devono convalidare che i metadati siano conformi ai criteri dell'applicazione client riguardanti la sicurezza, le transazioni, il tipo di contratto di servizio e così via. Nell'esempio seguente viene dimostrato come scrivere un comportamento dell'endpoint client che convalida l'endpoint del servizio per garantire che quest'ultimo possa essere usato senza rischi.  
  
 Il servizio espone quattro endpoint del servizio. Il primo endpoint usa WSDualHttpBinding, il secondo usa l'autenticazione NTLM, il terzo abilita il flusso delle transazioni e il quarto usa l'autenticazione basata sui certificati.  
  
 Il client usa la classe <xref:System.ServiceModel.Description.MetadataResolver> per recuperare i metadati per il servizio. Il client applica i criteri di proibizione delle associazioni duplex, autenticazione NTLM e flusso delle transazioni usando un comportamento di convalida. Per ogni <xref:System.ServiceModel.Description.ServiceEndpoint> istanza importata dai metadati del servizio, l'applicazione client aggiunge un'istanza del `InternetClientValidatorBehavior` comportamento dell'endpoint per il <xref:System.ServiceModel.Description.ServiceEndpoint> prima di provare a usare un client Windows Communication Foundation (WCF) a cui connettersi l'endpoint. Il metodo `Validate` del comportamento viene eseguito prima che venga chiamata qualsiasi operazione nel servizio e applica i criteri del client generando `InvalidOperationExceptions`.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Per eseguire l'esempio nello stesso computer  
  
1.  Aprire un prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire Setup. bat dalla cartella di installazione dell'esempio. In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.  
  
2.  Eseguire l'applicazione di servizio da \service\bin\Debug.  
  
3.  Eseguire l'applicazione client da \client\bin\Debug. L'attività del client viene visualizzata nella finestra dell'applicazione console.  
  
4.  Se il client e il servizio non possono comunicare, vedere [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
5.  Rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio. Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.  
  
### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer  
  
1.  Nel server, in un prompt dei comandi sviluppatori per Visual Studio eseguire con privilegi di amministratore, digitare `setup.bat service`. In esecuzione `setup.bat` con il `service` argomento consente di creare un certificato di servizio con il nome di dominio completo del computer ed esportare il certificato di servizio in un file denominato CER.  
  
2.  Modificare App.config sul server per riflettere il nome del nuovo certificato, Vale a dire, modificare il `findValue` attributo la [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) elemento per il nome di dominio completo del computer.  
  
3.  Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.  
  
4.  Sul client, aprire un prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore e digitare `setup.bat client`. In esecuzione `setup.bat` con il `client` argomento crea un certificato client denominato Client.com ed Esporta il certificato client in un file denominato CER.  
  
5.  Nel file client.cs modificare il valore dell'indirizzo dell'endpoint MEX e il `findValue` per impostare il certificato del server predefinito in modo che corrisponda al nuovo indirizzo del servizio. Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server. Ricompilare il file.  
  
6.  Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.  
  
7.  Sul client, eseguire Importservicecert. bat in un prompt dei comandi di per gli sviluppatori per Visual Studio aperto con privilegi di amministratore. In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.  
  
8.  Nel server, eseguire importclientcert. bat in un prompt dei comandi di per gli sviluppatori per Visual Studio aperto con privilegi di amministratore. In questo modo viene importato il certificato del client dal file Client.cer nell'archivio LocalMachine - TrustedPeople.  
  
9. Nel computer del servizio compilare il progetto di servizio in Visual Studio ed eseguire service.exe.  
  
10. Nel computer client eseguire client.exe.  
  
    1.  Se il client e il servizio non possono comunicare, vedere [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>Per eseguire la pulizia dopo l'esempio  
  
-   Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.  
  
    > [!NOTE]
    >  Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer. Se sono stati eseguiti esempi WCF che utilizzano certificati in più computer, assicurarsi di cancellare i certificati del servizio che sono stati installati in CurrentUser - TrustedPeople archiviare. A tale scopo, utilizzare il comando seguente: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)
