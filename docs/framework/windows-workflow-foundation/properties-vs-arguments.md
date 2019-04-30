---
title: Proprietà e Argomenti
ms.date: 03/30/2017
ms.assetid: 14651389-4a49-4cbb-9ddf-c83fdc155df1
ms.openlocfilehash: a6ea4755599f18e8bbaa8187941623578d2168ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962630"
---
# <a name="properties-vs-arguments"></a>Proprietà e Argomenti
Sono disponibili diverse opzioni per passare dati in un'attività. Oltre a usare <xref:System.Activities.InArgument>, è possibile sviluppare attività che ricevono dati usando le proprietà CLR standard o le proprietà <xref:System.Activities.ActivityAction> pubbliche. In questo argomento viene illustrato come selezionare il tipo di metodo appropriato.  
  
## <a name="using-clr-properties"></a>Utilizzo delle proprietà CLR  
 Per il passaggio di dati in un'attività, le proprietà CLR (cioè metodi pubblici che usano routine Get e Set per esporre i dati) costituiscono la scelta che presenta le maggiori restrizioni. Il valore di un parametro passato in una proprietà CLR deve essere noto quando la soluzione viene compilata; questo valore sarà lo stesso per ogni istanza del flusso di lavoro. In questo modo, un valore passato in una proprietà CLR è simile a una costante definita nel codice; questo valore non può essere modificato per tutta la durata dell'attività e non può essere modificato per le diverse istanze dell'attività. <xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A> è un esempio di una proprietà CLR esposta da un'attività; il nome del metodo chiamato dall'attività non può essere modificato in base alle condizioni di runtime e resterà uguale per ogni istanza dell'attività.  
  
## <a name="using-arguments"></a>Utilizzo degli argomenti  
 Gli argomenti devono essere usati quando i dati vengono valutati solo una volta per tutta la durata dell'attività; ovvero, il valore non verrà modificato nel corso della durata dell'attività, ma potrà essere diverso per le diverse istanze dell'attività. <xref:System.Activities.Statements.If.Condition%2A> è un esempio di un valore che viene valutato una volta; per questo motivo viene definito come argomento. <xref:System.Activities.Statements.WriteLine.Text%2A> è un altro esempio di metodo che deve essere definito come argomento, poiché viene valutato solo una volta durante l'esecuzione dell'attività, ma può essere diverso per le istanze diverse dell'attività.  
  
## <a name="using-activityaction"></a>Uso di ActivityAction  
 Quando i dati devono essere valutati più volte durante la durata dell'esecuzione di un'attività, è necessario usare <xref:System.Activities.ActivityAction>. Ad esempio, la proprietà <xref:System.Activities.Statements.While.Condition%2A> viene valutata per ogni iterazione del ciclo <xref:System.Activities.Statements.While>. Se a tale scopo si utilizzasse <xref:System.Activities.InArgument>, non si uscirebbe mai dal ciclo, poiché l'argomento non verrebbe rivalutato per ogni iterazione e restituirebbe sempre lo stesso risultato.
