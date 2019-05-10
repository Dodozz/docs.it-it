---
title: Gestione dell'istanza sospesa
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: c23d2dfd48ecb57a3fb418734c916586178986e9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622414"
---
# <a name="suspended-instance-management"></a>Gestione dell'istanza sospesa
In questo esempio viene illustrato come gestire le istanze del flusso di lavoro che sono state sospese.  L'azione predefinita per l'oggetto <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> è `AbandonAndSuspend`. Pertanto, per impostazione predefinita, le eccezioni non gestite generate da un'istanza del flusso di lavoro ospitata nell'oggetto <xref:System.ServiceModel.WorkflowServiceHost> comporteranno l'eliminazione dell'istanza dalla memoria (abbandonata) e la versione durevole/persistente dell'istanza sarà contrassegnata come sospesa. Non sarà possibile eseguire un'istanza del flusso di lavoro sospesa finché non viene annullata la sospensione.

 Nell'esempio viene illustrata l'implementazione di un'utilità della riga di comando per eseguire query per le istanze sospese e viene mostrato come consentire all'utente di riprendere o terminare l'istanza. In questo esempio, un servizio flusso di lavoro genera intenzionalmente un'eccezione, comportandone la sospensione. L'utilità della riga di comando può essere quindi usata per eseguire query per l'istanza e, successivamente, per riprendere o terminare l'istanza.

## <a name="demonstrates"></a>Dimostrazione
 <xref:System.ServiceModel.WorkflowServiceHost> con <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> e <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).

## <a name="discussion"></a>Discussione
 L'utilità della riga di comando implementata in questo esempio è specifica per l'implementazione dell'archivio di istanze SQL fornito con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]. Se si dispone di un'implementazione personalizzata dell'archivio di istanze, è possibile adattare questa utilità sostituendo le implementazioni `WorkflowInstanceCommand` dell'esempio con le implementazioni specifiche dell'archivio di istanze.

 L'implementazione fornita esegue direttamente i comandi SQL nell'archivio di istanze SQL per elencare le istanze sospese e si basa su un oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> aggiunto all'oggetto <xref:System.ServiceModel.WorkflowServiceHost> per riprendere o terminare le istanze.

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Per questo esempio è necessario aver abilitato i seguenti componenti di Windows:

    1. Microsoft Message Queue (MSMQ) Server

    2. SQL Server Express

2. Impostare il database SQL Server.

    1. Da un prompt dei comandi di Visual Studio 2010, eseguire "Setup. cmd" dalla directory di esempio SuspendedInstanceManagement, che esegue le operazioni seguenti:

        1. Creare un database di persistenza tramite SQL Server Express. Se il database di persistenza è già presente, viene eliminato e ricreato

        2. Impostare il database per la persistenza.

        3. Aggiungere IIS APPPOOL\DefaultAppPool e NT AUTHORITY\Network Service al ruolo InstanceStoreUsers definito durante l'impostazione del database per la persistenza.

3. Impostare la coda del servizio.

    1. In Visual Studio 2010, fare doppio clic il **SampleWorkflowApp** del progetto e fare clic su **imposta come progetto di avvio**.

    2. Compilare ed eseguire SampleWorkflowApp premendo **F5**. In questo modo verrà creata la coda richiesta.

    3. Premere **invio** per arrestare SampleWorkflowApp.

    4. Aprire la console Gestione computer eseguendo Compmgmt.msc da un prompt dei comandi.

    5. Espandere **applicazioni e servizi**, **Accodamento**, **code Private**.

    6. Fare clic il **ReceiveTx** della coda e selezionare **proprietà**.

    7. Selezionare il **sicurezza** scheda e consentire **Everyone** disporre delle autorizzazioni per **Ricevi messaggio**, **Visualizza il messaggio**, e  **Invio messaggio**.

4. A questo punto, eseguire l'esempio.

    1. In Visual Studio 2010, eseguire nuovamente il progetto SampleWorkflowApp senza debug premendo **CTRL+F5**. Nella finestra della console saranno stampati due indirizzi endpoint: uno per l'endpoint dell'applicazione e l'altro per l'oggetto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>. Viene quindi creata un'istanza del flusso di lavoro e i record di rilevamento per tale istanza saranno visualizzati nella finestra della console. L'istanza del flusso di lavoro genererà un'eccezione che comporterà la sospensione e l'interruzione dell'istanza.

    2. L'utilità della riga di comando può essere quindi usata per eseguire ulteriori azioni in qualsiasi istanza. Di seguito è riportata la sintassi per gli argomenti della riga di comando:

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         I comandi supportati sono: `Query`, `Resume` e `Terminate`.  L'opzione InstanceId è richiesta solo per le operazioni `Resume` e `Terminate`.

#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)

1. Aprire la console Gestione computer eseguendo Compmgmt.msc da un prompt dei comandi di `vs2010`.

2. Espandere **applicazioni e servizi**, **Accodamento**, **code Private**.

3. Eliminare il **ReceiveTx** coda.

4. Per rimuovere il database di persistenza, eseguire cleanup.cmd.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
