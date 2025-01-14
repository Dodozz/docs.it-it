---
title: Processo di approvazione dei documenti
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: dfc2e0a12d053733823427ac50066b1e4a0f97aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62005123"
---
# <a name="document-approval-process"></a>Processo di approvazione dei documenti
In questo esempio illustra l'uso di molte funzionalità di Windows Workflow Foundation (WF) e Windows Communication Foundation (WCF) tra loro. Insieme implementano uno scenario del processo di approvazione dei documenti. Un'applicazione client può inviare documenti da sottoporre ad approvazione e approvare documenti. Un'applicazione di gestione delle approvazioni è utile per semplificare le comunicazioni tra i client e per applicare le regole del processo di approvazione che consiste in un flusso di lavoro che può eseguire molti tipi di approvazione. Le attività servono per ottenere un processo di approvazione singola, di approvazione a quorum (una percentuale del gruppo di responsabili approvazione) e di approvazione complessa costituito da un'approvazione a quorum e una singola in sequenza.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Il grafico seguente illustra il flusso di lavoro documenti processo approvazione:  
  
 ![Flusso di lavoro del processo di approvazione di un documento](./media/document-approval-process/document-approval-process.jpg)  
  
 Dalla prospettiva del client, il processo di approvazione funziona nel modo seguente:  
  
1. Un client esegue una sottoscrizione per essere un utente del sistema del processo di approvazione.  
  
2. Un client WCF invia a un servizio WCF ospitato dall'applicazione di gestione delle approvazioni.  
  
3. Al client viene restituito un ID utente univoco. Il client può ora partecipare ai processi di approvazione.  
  
4. Una volta inserito, un client può inviare un documento per l'approvazione usando un processo di approvazione singolo, a quorum o complesso.  
  
5. La selezione di un pulsante nell'interfaccia del client avvia un'istanza del flusso di lavoro in un host dei servizi flusso di lavoro del client.  
  
6. Il flusso di lavoro invia una richiesta di approvazione all'applicazione di gestione delle approvazioni.  
  
7. Il proprietario del flusso di lavoro avvia un flusso di lavoro per rappresentare un processo di approvazione.  
  
8. Una volta che il proprietario ha eseguito il flusso di lavoro di approvazione, i risultati vengono restituiti al client.  
  
9. Il client visualizza i risultati.  
  
10. Un client può ricevere una richiesta di approvazione e rispondere alla richiesta in qualsiasi momento.  
  
11. Un servizio WCF ospitato nel client può ricevere una richiesta di approvazione dall'applicazione di gestione delle approvazioni.  
  
12. Le informazioni sul documento vengono presentate nel client per la revisione.  
  
13. L'utente può approvare o rifiutare il documento.  
  
14. Un client WCF viene usato per inviare una risposta di approvazione all'applicazione di gestione delle approvazioni.  
  
 Dal punto di vista dell'applicazione di gestione delle approvazioni, il processo di approvazione funziona nel modo seguente:  
  
1. Un client richiede la partecipazione al sistema del processo di approvazione.  
  
2. Un servizio WCF in responsabile dell'approvazione riceve una richiesta a far parte del sistema del processo di approvazione.  
  
3. Viene generato un ID univoco per il client. Le informazioni utente vengono archiviate in un database.  
  
4. L'ID univoco viene restituito all'utente.  
  
5. Viene ricevuta una richiesta di approvazione. Il responsabile dell'approvazione esegue un processo di approvazione.  
  
6. Il responsabile dell'approvazione riceve una richiesta di approvazione che avvia un nuovo flusso di lavoro.  
  
7. A seconda del tipo di richiesta (semplice, a quorum o complessa), viene eseguita un'attività diversa.  
  
8. Le attività di invio e ricezione con correlazione vengono usate per inviare la richiesta di approvazione al client per la revisione e per ricevere la risposta.  
  
9. Il risultato del flusso di lavoro del processo di approvazione viene inviato al client.  
  
## <a name="using-the-sample"></a>Utilizzo dell'esempio  
  
##### <a name="to-set-up-the-database"></a>Per impostare il database  
  
1. Da un prompt dei comandi di Visual Studio 2010 aperto con privilegi di amministratore, passare alla cartella DocumentApprovalProcess ed eseguire Setup. cmd.  
  
##### <a name="to-set-up-the-application"></a>Per impostare l'applicazione  
  
1. Con Visual Studio 2010, aprire il file della soluzione Documentapprovalprocess.  
  
2. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3. Per eseguire la soluzione, avviare l'applicazione di approvazione Manager facendo clic con il progetto ApprovalManager nel **Esplora soluzioni** e facendo clic su **Debug**->**Start**  nuova istanza di dal menu di scelta rapida.  
  
     Attendere l'output del responsabile per sapere che è pronta.  
  
##### <a name="to-run-the-single-approval-scenario"></a>Per eseguire lo scenario di approvazione singola  
  
1. Aprire un prompt dei comandi con l'autorizzazione di amministratore.  
  
2. Passare alla directory contenente la soluzione.  
  
3. Passare alla cartella ApprovalClient\Bin\Debug ed eseguire due istanze di ApprovalClient.exe.  
  
4. Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.  
  
5. Digitare un nome utente e fare clic su **sottoscrivere**. Per un client usare `UserType1` e per l'altro il tipo `UserType2`.  
  
6. Nel client `UserType1` selezionare il tipo di approvazione singola dal menu a discesa e digitare un nome e il contenuto del documento. Fare clic su **Richiedi l'approvazione**.  
  
7. Nel client `UserType2` viene visualizzato un documento in attesa di approvazione. Selezionarlo e premere **approvare** oppure **rifiutare**. I risultati devono essere visualizzati nel client `UserType1`.  
  
##### <a name="to-run-the-quorum-approval-scenario"></a>Per eseguire lo scenario di approvazione a quorum  
  
1. Aprire un prompt dei comandi con l'autorizzazione di amministratore.  
  
2. Passare alla directory contenente la soluzione.  
  
3. Passare alla cartella ApprovalClient\Bin\Debug ed eseguire tre istanze di ApprovalClient.exe.  
  
4. Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.  
  
5. Digitare un nome utente e fare clic su **sottoscrivere**. Per un client usare `UserType1` e per gli altri due usare il tipo `UserType2`.  
  
6. Nel client `UserType1` selezionare il tipo di approvazione a quorum dal menu a discesa e digitare un nome e il contenuto del documento. Fare clic su **Richiedi l'approvazione**. In questo modo viene richiesto che i due client `UserType2` approvino o rifiutino il documento. Mentre entrambi i client `UserType2` devono rispondere, solo un client deve approvare il documento.  
  
7. Nei client `UserType2` viene visualizzato un documento in attesa di approvazione. Selezionarlo e premere **approvare** oppure **rifiutare**. I risultati devono essere visualizzati nel client `UserType1`.  
  
##### <a name="to-run-the-complex-approval-scenario"></a>Per eseguire lo scenario di approvazione complesso  
  
1. Aprire un prompt dei comandi con l'autorizzazione di amministratore.  
  
2. Passare alla directory contenente la soluzione.  
  
3. Passare alla cartella ApprovalClient\Bin\Debug ed eseguire quattro istanze di ApprovalClient.exe.  
  
4. Fare clic su **individua**, attendere finché il **sottoscrivere** pulsante è abilitato.  
  
5. Digitare un nome utente e fare clic su **sottoscrivere**. Per un client usare `UserType1`, per il secondo usare il tipo `UserType2` e per l'ultimo usare `UserType3`.  
  
6. Nel client `UserType1` selezionare il tipo di approvazione singola dal menu a discesa e digitare un nome e il contenuto del documento. Fare clic su **Richiedi l'approvazione**.  
  
7. Nei client `UserType2` viene visualizzato un documento in attesa di approvazione. Selezionarlo e premere **approvare**, il documento viene passato per il `UserType3` client.  
  
     Se il documento viene approvato dal primo quorum `UserType2`, il documento viene passato al client `UserType3`.  
  
8. Approvare o rifiutare il documento dal client `UserType3`. I risultati devono essere visualizzati nel client `UserType1`.  
  
##### <a name="to-clean-up"></a>Per eseguire la pulizia  
  
1. Da un prompt dei comandi di Visual Studio 2010, passare alla cartella DocumentApprovalProcess ed eseguire Cleanup.
