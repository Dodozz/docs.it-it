---
title: Accesso a OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: c104ceb22117d7cc53050a6513a4aea58fdff8c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772882"
---
# <a name="accessing-operationcontext"></a>Accesso a OperationContext
Questo esempio viene illustrato come l'attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.Send>) può essere utilizzato con un'attività di ambiti personalizzata per accedere <xref:System.ServiceModel.OperationContext.Current%2A> e allegare o recuperare un'intestazione di messaggio personalizzata all'interno di un messaggio in ingresso o in uscita.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Attività di messaggistica, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come usare punti di estensibilità (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) nelle attività di messaggistica per accedere a <xref:System.ServiceModel.OperationContext.Current%2A>. I callback vengono registrati all'interno dell'esecuzione del flusso di lavoro come un'implementazione di <xref:System.Activities.IExecutionProperty> raccolta dalle attività della messaggistica durante l'esecuzione. Qualsiasi attività di messaggistica nello stesso ambito di tale implementazione <xref:System.Activities.IExecutionProperty> risulta interessata. In particolare, questo esempio usa un'attività di ambiti personalizzata per applicare il comportamento di callback. <xref:System.ServiceModel.Activities.ISendMessageCallback> viene usato nel flusso di lavoro client per includere l'oggetto <xref:System.Activities.WorkflowApplication.Id%2A> del flusso di lavoro come <xref:System.ServiceModel.Channels.MessageHeader> in uscita. Questa intestazione viene quindi scelta nel servizio usando <xref:System.ServiceModel.Activities.IReceiveMessageCallback> e il valore dell'intestazione viene stampato nella console.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP. Per eseguire questo esempio, corretto elenchi ACL URL deve essere aggiunto (vedere [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate), tramite l'esecuzione di Visual Studio come amministratore oppure eseguendo il comando seguente in un prompt dei comandi con privilegi elevati per aggiungere gli ACL appropriati. Assicurarsi che vengono sostituiti il dominio e il nome utente.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.  
  
    1.  Compilare la soluzione.  
  
    2.  Impostare più progetti di avvio facendo clic sulla soluzione e selezionando **Imposta progetti di avvio**.  
  
    3.  Aggiungere **assistenza** e **Client** (in questo ordine) come più progetti di avvio.  
  
    4.  Eseguire l'applicazione. Nella console client viene visualizzato un flusso di lavoro che viene eseguito due volte e nella finestra Servizio è visualizzato l'ID istanza di tali flussi di lavoro.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
