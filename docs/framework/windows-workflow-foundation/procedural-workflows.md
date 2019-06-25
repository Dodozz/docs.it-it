---
title: Flussi di lavoro procedurali
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 15ff155fb057c4c10663d383a8942108c6e4375c
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348359"
---
# <a name="procedural-workflows"></a>Flussi di lavoro procedurali
Nei flussi di lavoro procedurali vengono usati metodi di controllo del flusso simili a quelli dei linguaggi procedurali. Tra questi costrutti sono inclusi `While` e `If`. Questi flussi di lavoro possono essere creati liberamente usando altre attività di controllo del flusso quale <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Sequence>.  
  
## <a name="controlling-execution-flow"></a>Controllo del flusso di esecuzione  
 La libreria di attività del flusso di lavoro dispone di attività per modellare la maggior parte dei metodi di controllo del flusso usati nei linguaggi procedurali, Sono inclusi:  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Per utilizzare le attività di controllo di flusso, trascinamento della selezione dal **attività** della casella degli strumenti in un'attività composta nella finestra di progettazione.  
  
> [!NOTE]
>  Se si usa la funzionalità di hosting di Windows Server AppFabric ospitare flussi di lavoro in una Web farm, AppFabric sposterà istanze tra server di AppFabric differenti. È necessario quindi che le risorse possano essere condivise tra tutti i nodi.  Nessuna delle attività predefinite del flusso di lavoro di .NET 4 contiene operazioni di accesso alle risorse locali. Poiché AppFabric non offre alcun meccanismo per contrassegnare un flusso di lavoro come non spostabile, uno sviluppatore non deve creare attività personalizzate che non vengono eseguite correttamente quando un flusso di lavoro viene spostato.  
  
## <a name="see-also"></a>Vedere anche

- [Flussi di lavoro del diagramma di flusso](flowchart-workflows.md)
