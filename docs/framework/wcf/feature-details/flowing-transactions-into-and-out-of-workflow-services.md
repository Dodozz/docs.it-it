---
title: Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: 4a5cde045c6c676c2efc694c67fd049b6eb611b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708636"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a>Propagazione di transazioni all'interno e all'esterno di servizi flusso di lavoro
Servizi e client del flusso di lavoro possono partecipare alle transazioni.  Affinché un'operazione del servizio diventi parte di una transazione di ambiente, posizionare un'attività <xref:System.ServiceModel.Activities.Receive> all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Qualsiasi chiamata effettuata da un'attività <xref:System.ServiceModel.Activities.Send> o un'attività <xref:System.ServiceModel.Activities.SendReply> all'interno di <xref:System.ServiceModel.Activities.TransactedReceiveScope> verrà effettuata anche all'interno della transazione di ambiente. Un'applicazione client del flusso di lavoro può creare una transazione di ambiente tramite l'attività <xref:System.Activities.Statements.TransactionScope> e chiamare operazioni del servizio utilizzando la transazione di ambiente. In questo argomento viene illustrato il processo di creazione di un servizio flusso di lavoro e di un client flusso di lavoro che partecipano a transazioni.  
  
> [!WARNING]
>  Se un'istanza del servizio flusso di lavoro viene caricata all'interno di una transazione e il flusso di lavoro contiene un'attività <xref:System.Activities.Statements.Persist>, l'istanza del flusso di lavoro verrà interrotta finché non si verifica il timeout della transazione.  
  
> [!IMPORTANT]
>  Ogni volta che si utilizza un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, è consigliabile posizionare tutte le attività Receive del flusso di lavoro all'interno delle attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.  
  
> [!IMPORTANT]
>  Quando si utilizza l'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> e i messaggi arrivano nell'ordine non corretto, il flusso di lavoro verrà interrotto quando si tenterà di consegnare il primo messaggio nell'ordine non corretto. È necessario assicurarsi che il flusso di lavoro sia sempre in corrispondenza di un punto di interruzione coerente quando il flusso di lavoro è inattivo. In questo modo sarà possibile riavviare il flusso di lavoro da un punto di persistenza precedente nel caso in cui il flusso di lavoro venga interrotto.  
  
### <a name="create-a-shared-library"></a>Creare una libreria condivisa  
  
1.  Creare una nuova soluzione Visual Studio vuota.  
  
2.  Aggiungere un nuovo progetto della libreria di classi denominato `Common`. Aggiungere riferimenti agli assembly riportati di seguito:  
  
    -   System.Activities.dll  
  
    -   System.ServiceModel.dll  
  
    -   System.ServiceModel.Activities.dll  
  
    -   System.Transactions.dll  
  
3.  Aggiungere una nuova classe denominata `PrintTransactionInfo` al progetto `Common`. Questa classe è derivata da <xref:System.Activities.NativeActivity> ed esegue l'overload del metodo <xref:System.Activities.NativeActivity.Execute%2A>.  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     Si tratta di un'attività nativa che visualizza informazioni sulla transazione di ambiente e viene utilizzata sia nei flussi di lavoro del servizio che del client utilizzati nel presente argomento. Compilare la soluzione per rendere disponibile in questa attività il **comuni** sezione il **della casella degli strumenti**.  
  
### <a name="implement-the-workflow-service"></a>Implementare il servizio di flusso di lavoro  
  
1.  Aggiungere un nuovo servizio di flusso di lavoro WCF, denominato `WorkflowService` per il `Common` progetto. Per eseguire questa operazione, a destra il `Common` progetto, scegliere **Add**, **nuovo elemento...** , Selezionare **flusso di lavoro** sotto **modelli installati** e selezionare **servizio del flusso di lavoro WCF**.  
  
     ![Aggiunta di un servizio del flusso di lavoro](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")  
  
2.  Eliminare le attività `ReceiveRequest` e `SendResponse` predefinite.  
  
3.  Trascinare un'attività <xref:System.Activities.Statements.WriteLine> nell'attività `Sequential Service`. Impostare la proprietà Text su `"Workflow Service starting ..."` come illustrato nell'esempio seguente.  
  
     ![Aggiunta di un'attività WriteLine](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")  
  
4.  Trascinare e rilasciare un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>. Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività sono reperibili nel **messaggistica** sezione del **casella degli strumenti**. Il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività è costituita da due sezioni **richiedere** e **corpo**. Il **richiedere** sezione sono contenute le <xref:System.ServiceModel.Activities.Receive> attività. Il **corpo** sezione contiene le attività da eseguire all'interno di una transazione dopo che è stato ricevuto un messaggio.  
  
     ![Aggiunta di un'attività TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")  
  
5.  Selezionare il <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività e scegliere il **variabili** pulsante. Aggiungere le variabili seguenti.  
  
     ![Aggiunta di variabili a TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")  
  
    > [!NOTE]
    >  È possibile eliminare la variabile relativa ai dati, presente per impostazione predefinita. È possibile utilizzare anche la variabile dell'handle esistente.  
  
6.  Trascinare e rilasciare un <xref:System.ServiceModel.Activities.Receive> attività all'interno di **richiesta** sezione del <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività. Impostare le proprietà seguenti:  
  
    |Proprietà|Value|  
    |--------------|-----------|  
    |CanCreateInstance|True (controllare la casella di controllo)|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiunta di un'attività Receive](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")  
  
7.  Fare clic su di **definire...**  collegare il <xref:System.ServiceModel.Activities.Receive> attività e configurare le impostazioni seguenti:  
  
     ![Configurazione delle impostazioni di messaggio per l'attività Receive](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")  
  
8.  Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nella sezione Corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>. All'interno dell'attività <xref:System.Activities.Statements.Sequence>, trascinare e rilasciare due attività <xref:System.Activities.Statements.WriteLine> e impostare le proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> come illustrato nella tabella seguente.  
  
    |Attività|Value|  
    |--------------|-----------|  
    |WriteLine 1|"Service: Ricezione completato"|  
    |WriteLine 2|"Service: Received = " + requestMessage|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiunta di attività WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")  
  
9. Trascinare e rilasciare il `PrintTransactionInfo` attività dopo la seconda <xref:System.Activities.Statements.WriteLine> attività nel **corpo** nel <xref:System.ServiceModel.Activities.TransactedReceiveScope> attività.  
  
     ![Dopo avere aggiunto PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")  
  
10. Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Assign> dopo l'attività `PrintTransactionInfo` e impostarne le proprietà in base alla tabella seguente.  
  
    |Proprietà|Valore|  
    |--------------|-----------|  
    |A|replyMessage|  
    |Valore|"Service: Invio risposta".|  
  
11. Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il <xref:System.Activities.Statements.Assign> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Begin reply".  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Dopo avere aggiunto Assign e WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")  
  
12. Fare clic il <xref:System.ServiceModel.Activities.Receive> attività e selezionare **crea SendReply** e incollarlo dopo l'ultimo <xref:System.Activities.Statements.WriteLine> attività. Fare clic su di **definire...**  collegare il `SendReplyToReceive` attività e configurare le impostazioni seguenti.  
  
     ![Impostazioni dei messaggi di risposta](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")  
  
13. Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `SendReplyToReceive` attività e set ha <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Risposta inviata."  
  
14. Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività nella parte inferiore del flusso di lavoro e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Service: Flusso di lavoro termina, premere INVIO per uscire."  
  
     Il flusso di lavoro del servizio completato dovrebbe risultare analogo al seguente:  
  
     ![Servizio del flusso di lavoro di completare](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")  
  
### <a name="implement-the-workflow-client"></a>Implementare il client flusso di lavoro  
  
1.  Aggiungere una nuova applicazione flusso di lavoro WCF, denominata `WorkflowClient`, al progetto `Common`. Per eseguire questa operazione, a destra il `Common` progetto, scegliere **Add**, **nuovo elemento...** , Selezionare **flusso di lavoro** sotto **modelli installati** e selezionare **attività**.  
  
     ![Aggiungere un progetto di attività](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")  
  
2.  Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> sull'area di progettazione.  
  
3.  All'interno dell'attività <xref:System.Activities.Statements.Sequence> trascinare e rilasciare un'attività <xref:System.Activities.Statements.WriteLine> e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su `"Client: Workflow starting"`. Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiungere un'attività WriteLine](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")  
  
4.  Trascinare e rilasciare un'attività <xref:System.Activities.Statements.TransactionScope> dopo l'attività <xref:System.Activities.Statements.WriteLine>.  Selezionare l'attività <xref:System.Activities.Statements.TransactionScope>, fare clic sul pulsante Variabili e aggiungere le variabili seguenti.  
  
     ![Aggiungere variabili a TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")  
  
5.  Trascinare e rilasciare un'attività <xref:System.Activities.Statements.Sequence> nel corpo dell'attività <xref:System.Activities.Statements.TransactionScope>.  
  
6.  Trascinare e rilasciare un'attività `PrintTransactionInfo` all'interno dell'attività <xref:System.Activities.Statements.Sequence>.  
  
7.  Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il `PrintTransactionInfo` attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Client: Inizio invio". Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![Aggiunta di attività](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")  
  
8.  Trascinare e rilasciare un'attività <xref:System.ServiceModel.Activities.Send> dopo l'attività <xref:System.Activities.Statements.Assign> e impostare le proprietà seguenti:  
  
    |Proprietà|Value|  
    |--------------|-----------|  
    |EndpointConfigurationName|workflowServiceEndpoint|  
    |OperationName|StartSample|  
    |ServiceContractName|ITransactionSample|  
  
     Il flusso di lavoro dovrebbe risultare analogo al seguente:  
  
     ![L'impostazione di proprietà dell'attività Send](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")  
  
9. Fare clic su di **definire...**  collegare e configurare le impostazioni seguenti:  
  
     ![Attività messaggio le impostazioni di invio](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")  
  
10. Fare clic il <xref:System.ServiceModel.Activities.Send> attività e selezionare **crea ReceiveReply**. L'attività <xref:System.ServiceModel.Activities.ReceiveReply> sarà posizionata automaticamente dopo l'attività <xref:System.ServiceModel.Activities.Send>.  
  
11. Fare clic sul collegamento Definisci nell'attività ReceiveReplyForSend e configurare le impostazioni seguenti:  
  
     ![L'impostazione delle impostazioni del messaggio ReceiveForSend](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")  
  
12. Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività tra il <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà su "Client: Invia completo".  
  
13. Trascinare e rilasciare un <xref:System.Activities.Statements.WriteLine> attività dopo il <xref:System.ServiceModel.Activities.ReceiveReply> attività e set relativo <xref:System.Activities.Statements.WriteLine.Text%2A> proprietà "lato Client: Risposta ricevuta = "+ replyMessage  
  
14. Trascinare e rilasciare un'attività `PrintTransactionInfo` dopo l'attività <xref:System.Activities.Statements.WriteLine>.  
  
15. Trascinare un'attività <xref:System.Activities.Statements.WriteLine> alla fine del flusso di lavoro e impostarne la proprietà <xref:System.Activities.Statements.WriteLine.Text%2A> su "Client workflow ends". Il flusso di lavoro client completato viene visualizzato come illustrato del diagramma seguente.  
  
     ![Il client completo workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")  
  
16. Compilare la soluzione.  
  
### <a name="create-the-service-application"></a>Creare l'applicazione di servizio  
  
1.  Aggiungere un nuovo progetto Applicazione console denominato `Service` alla soluzione. Aggiungere riferimenti agli assembly riportati di seguito:  
  
    1.  System.Activities.dll  
  
    2.  System.ServiceModel.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
2.  Aprire il file Program.cs generato e il codice seguente:  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  Aggiungere il file app.config seguente al progetto.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a>Creare l'applicazione client  
  
1.  Aggiungere un nuovo progetto Applicazione console denominato `Client` alla soluzione. Aggiungere un riferimento a System.Activities.dll.  
  
2.  Aprire il file program.cs e aggiungere il codice seguente.  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Servizi flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Panoramica delle transazioni di Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/transactions-overview.md)
