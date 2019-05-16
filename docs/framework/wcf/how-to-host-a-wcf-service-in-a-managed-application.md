---
title: "Procedura: Ospitare un servizio WCF in un'applicazione gestita"
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: b6d1c9c38e2cc5f1b1b7b5538af0339987563de6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637586"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>Procedura: Ospitare un servizio WCF in un'app gestita

Per ospitare un servizio all'interno di un'applicazione gestita, incorporare il codice per il servizio nel codice dell'applicazione, definire un endpoint per il servizio in modo imperativo nel codice, in modo dichiarativo tramite la configurazione o tramite endpoint predefiniti, quindi creare un'istanza di <xref:System.ServiceModel.ServiceHost>.

Per iniziare a ricevere messaggi, chiamare <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>. In tal modo viene creato e aperto il listener per il servizio. Questo tipo di hosting di un servizio viene spesso chiamato "self-hosting"" perché è la stessa applicazione gestita a svolgere il lavoro di hosting. Per chiudere il servizio, chiamare <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> su <xref:System.ServiceModel.ServiceHost>.

Un servizio può essere ospitato anche in un servizio Windows gestito, in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS). Per altre informazioni sulle opzioni per un servizio di hosting, vedere [servizi di Hosting](../../../docs/framework/wcf/hosting-services.md).

L'hosting di un servizio in un'applicazione gestita è l'opzione più flessibile perché richiede la distribuzione di un'infrastruttura minima. Per altre informazioni sui servizi di hosting nelle applicazioni gestite, vedere [Hosting in un'applicazione gestita](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).

Nella procedura seguente viene illustrato come implementare un servizio indipendente in un'applicazione console.

## <a name="create-a-self-hosted-service"></a>Creare un servizio self-hosted

1. Creare una nuova applicazione console:

   1. Aprire Visual Studio e selezionare **New** > **Project** dal **File** menu.

   2. Nel **modelli installati** elenco, selezionare **Visual c#** oppure **Visual Basic**e quindi selezionare **Windows Desktop**.

   3. Selezionare il **App Console** modello. Tipo di `SelfHost` nella **Name** casella e quindi scegliere **OK**.

2. Fare doppio clic su **SelfHost** nelle **Esplora soluzioni** e selezionare **Aggiungi riferimento**. Selezionare **System. ServiceModel** dalle **.NET** scheda e quindi scegliere **OK**.

    > [!TIP]
    > Se il **Esplora soluzioni** finestra non è visibile, selezionarla **Esplora soluzioni** dal **visualizzazione** menu.

3. Fare doppio clic su **Program.cs** oppure **Module1.vb** nelle **Esplora** per aprirlo nella finestra del codice, se non è già aperto. Aggiungere le istruzioni seguenti all'inizio del file:

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. Definire e implementare un contratto di servizio. In questo esempio viene definito un codice `HelloWorldService` che restituisce un messaggio in base all'input del servizio.

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > Per altre informazioni su come definire e implementare un'interfaccia del servizio, vedere [come: Definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) e [come: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).

5. All'inizio del metodo `Main`, creare un'istanza della classe <xref:System.Uri> con l'indirizzo di base del servizio.

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. Creare un'istanza della classe <xref:System.ServiceModel.ServiceHost>, passando un <xref:System.Type> che rappresenta il tipo di servizio e l'URI (Uniform Resource Identifier) dell'indirizzo di base a <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>. Abilitare la pubblicazione dei metadati, quindi chiamare il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> sull'oggetto <xref:System.ServiceModel.ServiceHost> per inizializzare il servizio e prepararlo a ricevere messaggi.

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > In questo esempio vengono utilizzati endpoint predefiniti e per il servizio non è necessario alcun file di configurazione. Se non è specificato alcun endpoint, il runtime ne crea uno per ogni indirizzo di base per ciascun contratto di servizio implementato dal servizio. Per altre informazioni sugli endpoint predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

7. Premere **Ctrl**+**MAIUSC**+**B** per compilare la soluzione.

## <a name="test-the-service"></a>Eseguire il test del servizio

1. Premere **Ctrl**+**F5** per eseguire il servizio.

2. Aprire **Client di prova WCF**.

    > [!TIP]
    > Per aprire **Client di prova WCF**, aprire il prompt dei comandi per gli sviluppatori per Visual Studio ed eseguire **WcfTestClient.exe**.

3. Selezionare **aggiunta di un servizio** dalle **File** menu.

4. Tipo di `http://localhost:8080/hello` nella casella Indirizzo e fare clic su **OK**.

    > [!TIP]
    > Verificare che il servizio sia in esecuzione. In caso contrario, il passaggio non viene eseguito. Se nel codice è stato modificato l'indirizzo di base, in questo passaggio utilizzare l'indirizzo di base modificato.

5. Fare doppio clic su **SayHello** sotto il **progetti di servizi** nodo. Digitare il nome nel **valore** colonna il **richiedere** elenco e fare clic su **Invoke**.

   Viene visualizzato un messaggio di risposta nel **risposta** elenco.

## <a name="example"></a>Esempio

Nell'esempio seguente viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per ospitare un servizio di tipo `HelloWorldService`, quindi viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> su <xref:System.ServiceModel.ServiceHost>. Nel codice viene fornito un indirizzo di base, viene abilitata la pubblicazione di metadati e vengono utilizzati endpoint predefiniti.

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [Procedura: Ospitare un servizio WCF in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
- [Servizi di hosting](../../../docs/framework/wcf/hosting-services.md)
- [Procedura: Definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [Procedura: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Associazioni fornite dal sistema](../../../docs/framework/wcf/system-provided-bindings.md)
