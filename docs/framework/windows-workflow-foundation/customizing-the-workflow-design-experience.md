---
title: Personalizzazione della fase di progettazione del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 87b49b025cfb27812933511b76c5a024cde4995a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680303"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizzazione della fase di progettazione del flusso di lavoro

In [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] sono stati semplificati gli scenari per progettare le attività personalizzate e riallocare [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Pertanto lo sviluppo e la distribuzione sono più semplici e più flessibili. La modifica infrastrutturale principale prevede che il nuovo modello di programmazione della finestra di progettazione attività viene compilato su Windows Presentation Foundation (WPF). In questo modo è possibile definire in modo dichiarativo gli ActivityDesigner e riallocare [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in altre applicazioni in modo semplice. In caso di riallocazione, è possibile sviluppare un editor di espressioni personalizzato per supportare IntelliSense o un dominio di espressioni semplificato. L'integrazione con Windows Communication Foundation (WCF) è diventato più semplice grazie all'uso dei servizi del flusso di lavoro. Gli ActivityDesigner personalizzati e l'albero degli elementi del modello possono essere usati per migliorare le esperienze in fase di progettazione nelle progettazioni flussi di lavoro riallocate.

## <a name="in-this-section"></a>In questa sezione

 [Uso di finestre di progettazione e modelli di attività personalizzati](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 Viene descritto come creare nuovi ActivityDesigner e modelli personalizzati.

 [Riallocazione di Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 Viene descritto come riallocare la [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] all'esterno di Visual Studio e come visualizzare gli errori di convalida.

 [Uso di un editor di espressioni personalizzato](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 Viene descritto come implementare un editor di espressioni personalizzato da usare con le finestre di progettazione del flusso di lavoro riallocate all'esterno di Visual Studio 2010.

## <a name="reference"></a>Riferimenti

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vedere anche

- [Estensione di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)
- [Finestra di progettazione](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [ActivityDesigner personalizzati](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [Riallocazione della finestra di progettazione](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)