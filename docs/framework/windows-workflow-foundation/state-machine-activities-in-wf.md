---
title: Attività della macchina a stati in WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 3086348d1c4f29e3f446e9525a12a9c207efb328
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619000"
---
# <a name="state-machine-activities-in-wf"></a>Attività della macchina a stati in WF
In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sono disponibili numerose attività fornite dal sistema e ActivityDesigner per la creazione di flussi di lavoro di macchine a stati.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Esegue attività contenute usando il comune paradigma della macchina a stati.|  
|<xref:System.Activities.Statements.State>|Rappresenta lo stato di una macchina a stati.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Rappresenta uno stato di chiusura in una macchina a stati. <xref:System.Activities.Core.Presentation.FinalState> è un ActivityDesigner che, quando usato, crea un elemento <xref:System.Activities.Statements.State> preconfigurato come stato di chiusura. Per altre informazioni, vedere [ActivityDesigner FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Rappresenta la transizione tra due stati. È presente alcun **casella degli strumenti** elemento per <xref:System.Activities.Statements.Transition>; le transizioni vengono create nella finestra di progettazione del flusso di lavoro trascinando e rilasciando una linea tra due stati o rilasciando uno stato sui triangoli visualizzati quando uno stato viene passato sopra un altro . Per altre informazioni, vedere [ActivityDesigner Transition](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Vedere anche
- [Esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
