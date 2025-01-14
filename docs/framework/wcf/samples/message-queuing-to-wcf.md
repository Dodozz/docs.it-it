---
title: Accodamento messaggi in Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
ms.openlocfilehash: 2dc0bc3154e2762d3296bf79a6f7245f87aefeb7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664898"
---
# <a name="message-queuing-to-windows-communication-foundation"></a>Accodamento messaggi in Windows Communication Foundation
Questo esempio dimostra come un'applicazione di Accodamento messaggi (MSMQ) può inviare un messaggio MSMQ a un servizio Windows Communication Foundation (WCF). Il servizio è un'applicazione console indipendente che consente di osservare il servizio che riceve messaggi in coda.  
  
 Il contratto di servizio è `IOrderProcessor`che definisce un servizio unidirezionale adatto per l'uso con le code. Un messaggio MSMQ non ha un'intestazione Action, pertanto non è possibile eseguire automaticamente il mapping di messaggi MSMQ diversi ai contratti dell'operazione. Pertanto, può essere presente un solo contratto dell'operazione. Se si vuole definire più di un contratto dell'operazione per il servizio, l'applicazione deve fornire informazioni come quale intestazione nel messaggio MSMQ (ad esempio, l'etichetta o correlationID) può essere utilizzata per decidere quale contratto dell'operazione inviare.
  
 Il messaggio MSMQ non contiene informazioni come su quali intestazioni è stato eseguito il mapping ai diversi parametri del contratto dell'operazione. Il parametro è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) che contiene il messaggio MSMQ sottostante. Il tipo "T" nella classe <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) rappresenta i dati serializzati nel corpo del messaggio MSMQ. In questo esempio, il tipo `PurchaseOrder` è serializzato nel corpo del messaggio MSMQ.  
  
 Nell'esempio di codice seguente viene mostrato il contratto di servizio del servizio di elaborazione degli ordini.  

```csharp
// Define a service contract.
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 Il servizio è indipendente. Quando si utilizza il trasporto MSMQ, la coda utilizzata deve essere creata in anticipo. Questa operazione può essere eseguita manualmente o mediante il codice. In questo esempio, il servizio verifica l'esistenza della coda e la crea se necessario. Il nome della coda viene letto dal file di configurazione.

```csharp
public static void Main()
{
    // Get the MSMQ queue name from the application settings in
    // configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];
    // Create the MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);
    …
}
```

 Il servizio crea e apre una classe <xref:System.ServiceModel.ServiceHost> per `OrderProcessorService`, come mostra il codice di esempio seguente.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
    serviceHost.Open();
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
    serviceHost.Close();
}
```

 Il nome della coda MSMQ viene specificato in una sezione appSettings del file di configurazione, come mostra la configurazione di esempio seguente.

> [!NOTE]
>  Nel nome della coda viene usato un punto (.) per il computer locale e il separatore barra rovesciata nel percorso. L'indirizzo dell'endpoint WCF specifica uno schema MSMQ. FormatName e viene utilizzato localhost per il computer locale. L'indirizzo della coda delle linee guida per l'indirizzamento del nome di formato MSMQ segue lo schema msmq.formatname.

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

 L'applicazione client è un'applicazione MSMQ che utilizza il metodo <xref:System.Messaging.MessageQueue.Send%2A> per inviare un messaggio durevole e transazionale alla coda, come mostra il codice di esempio seguente.

```csharp
//Connect to the queue.
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);

// Create the purchase order.
PurchaseOrder po = new PurchaseOrder();
po.CustomerId = "somecustomer.com";
po.PONumber = Guid.NewGuid().ToString();

PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
lineItem1.ProductId = "Blue Widget";
lineItem1.Quantity = 54;
lineItem1.UnitCost = 29.99F;

PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
lineItem2.ProductId = "Red Widget";
lineItem2.Quantity = 890;
lineItem2.UnitCost = 45.89F;

po.orderLineItems = new PurchaseOrderLineItem[2];
po.orderLineItems[0] = lineItem1;
po.orderLineItems[1] = lineItem2;

// Submit the purchase order.
Message msg = new Message();
msg.Body = po;
//Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{

    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
    // Complete the transaction.
    scope.Complete();

}
Console.WriteLine("Placed the order:{0}", po);
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 Quando si esegue l'esempio, le attività del client e del servizio vengono visualizzate nelle finestre della console del servizio e del client. È possibile osservare il servizio che riceve i messaggi dal client. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client. Notare che essendo usato l'accodamento, non è necessario che client e servizio siano in esecuzione contemporaneamente. Ad esempio è possibile eseguire il client, arrestarlo e quindi avviare il servizio e riceve comunque i messaggi.

### <a name="to-setup-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Se il servizio viene eseguito prima, verificherà la presenza della coda. Se la coda non è presente, il servizio ne creerà una. È possibile eseguire il servizio prima per creare la coda oppure è possibile crearne una tramite il gestore code MSMQ. Per creare una coda in Windows 2008, eseguire i passaggi riportati di seguito.

    1. Aprire Server Manager in Visual Studio 2012.

    2. Espandere la **funzionalità** scheda.

    3. Fare doppio clic su **code Private**e selezionare **New**, **coda privata**.

    4. Verificare i **transazionale** casella.

    5. Immettere `ServiceModelSamplesTransacted` come il nome della nuova coda.

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Per eseguire l'esempio in una configurazione con singolo computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-across-computers"></a>Per eseguire l'esempio tra più computer

1. Copiare i file del programma servizio dalla cartella \service\bin\, presente nella cartella specifica del linguaggio, nel computer del servizio.

2. Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.

3. Nel file Client.exe.config modificare orderQueueName per specificare il nome del computer del servizio anziché ".".

4. Sul computer del servizio eseguire Service.exe da un prompt dei comandi.

5. Sul computer client avviare Client.exe da un prompt dei comandi.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`  
  
## <a name="see-also"></a>Vedere anche

- [Code in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [Procedura: Scambiare messaggi con endpoint WCF e le applicazioni di Accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Accodamento messaggi](https://go.microsoft.com/fwlink/?LinkId=94968)
