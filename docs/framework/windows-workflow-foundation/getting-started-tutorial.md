---
title: Introduzione a Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 540765c09dceef583798ceaf1abf9f191f444697
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773529"
---
# <a name="getting-started-tutorial"></a>Esercitazione introduttiva
In questa sezione contiene un set di procedure dettagliate che introducono alla programmazione di applicazioni di Windows Workflow Foundation (WF). Seguendo le procedure di questi argomenti, verrà compilata un'applicazione che è un gioco per determinare un numero. Nel primo argomento dell'esercitazione vengono descritti i passaggi per creare le attività personalizzate richieste per il flusso di lavoro. Nel secondo argomento, queste attività vengono assemblate in un flusso di lavoro del diagramma di flusso insieme alle attività incorporate del flusso di lavoro. Nel terzo argomento, l'applicazione host viene configurata in modo da eseguire il flusso di lavoro e nell'ultimo argomento viene introdotta la persistenza. Ogni passaggio in questo processo dipende dai passaggi precedenti, pertanto si consiglia di completarli in ordine.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Creare un'attività](how-to-create-an-activity.md)  
 Viene descritto come creare un'attività personalizzata che deriva dall'oggetto <xref:System.Activities.NativeActivity%601> e come comporre questa attività insieme a un'attività incorporata in un'attività composita tramite l'ActivityDesigner.  
  
 [Procedura: Creare un flusso di lavoro](how-to-create-a-workflow.md)  
 Viene descritto come creare flussi di lavoro di diagramma di flusso, sequenziali e di macchina a stati tramite le attività predefinite e le attività personalizzate dall'esercitazione precedente.  
  
 [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)  
 Viene descritto come richiamare un flusso di lavoro da un ambiente host, come passare i dati all'interno e all'esterno di un flusso di lavoro e come riprendere i segnalibri.  
  
 [Procedura: Creare ed eseguire una lunga esecuzione flusso di lavoro](how-to-create-and-run-a-long-running-workflow.md)  
 Viene descritto come aggiungere la persistenza a un'applicazione flusso di lavoro.  
  
 [Procedura: Creare un partecipante di rilevamento personalizzati](how-to-create-a-custom-tracking-participant.md)  
 Viene descritto come creare un partecipante del rilevamento personalizzato e un profilo di rilevamento.  
  
 [Procedura: Ospitare più versioni di un flusso di lavoro Side-by-Side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 Viene descritto come usare `WorkflowIdentity` per ospitare più versioni di un flusso di lavoro side-by-side.  
  
 [Procedura: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 Viene descritto come usare l'aggiornamento dinamico per modificare le istanze in esecuzione del flusso di lavoro.  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione di Windows Workflow Foundation](programming.md)
