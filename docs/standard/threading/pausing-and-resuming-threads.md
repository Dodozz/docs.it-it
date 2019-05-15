---
title: Sospensione e interruzione di thread
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interrupting threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b39f91c5fabcfb5d7929a645b438b5db77f70956
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644925"
---
# <a name="pausing-and-interrupting-threads"></a>Sospensione e interruzione di thread

Le tecniche più comuni per sincronizzare le attività dei thread consistono nel blocco e nel rilascio dei thread oppure nel blocco di oggetti o aree di codice. Per altre informazioni su questi meccanismi di blocco, vedere [Panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 È anche possibile fare in modo che i thread vengano sospesi automaticamente. Quando i thread sono bloccati o sospesi, è possibile usare un'eccezione <xref:System.Threading.ThreadInterruptedException> per interromperne lo stato di attesa.  
  
## <a name="the-threadsleep-method"></a>Metodo Thread.Sleep

 Se si chiama il metodo <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>, il thread corrente viene bloccato immediatamente per il numero di millisecondi o l'intervallo di tempo passato al metodo, cedendo il resto della porzione di tempo a un altro thread. Una volta trascorso tale intervallo, il thread inattivo riprende l'esecuzione.  
  
 Un thread non può chiamare <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> su un altro thread.  <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> è un metodo statico che determina sempre il thread corrente da sospendere.  
  
 Se si chiama <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> con un valore di <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType>, un thread rimarrà sospeso finché non verrà interrotto da un altro thread tramite una chiamata al metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nel thread sospeso o finché non verrà terminato da una chiamata al relativo metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  L'esempio seguente illustra entrambi i metodi per interrompere un thread inattivo.  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a>Interruzione di thread

 È possibile interrompere un thread in attesa chiamando il metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> sul thread bloccato per generare un'eccezione <xref:System.Threading.ThreadInterruptedException>, che fa uscire il thread dalla chiamata che lo blocca. Il thread dovrebbe intercettare l'eccezione <xref:System.Threading.ThreadInterruptedException> ed eseguire le operazioni appropriate per continuare a funzionare. Se il thread ignora l'eccezione, l'ambiente di esecuzione la intercetta e interrompe il thread.  
  
> [!NOTE]
>  Se il thread di destinazione non è bloccato al momento della chiamata del metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>, il thread non subisce interruzioni finché non viene bloccato. Se il thread non si blocca, verrà completato senza subire alcuna interruzione.  
  
 Se un'attesa è di tipo gestito, sia <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> che <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> riporteranno immediatamente il thread allo stato di attività. Nel caso di un'attesa non gestita, ad esempio un platform invoke alla funzione Win32 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject), né <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> né <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> potrà assumere il controllo del thread fino alla restituzione o alla chiamata nel codice gestito. Di seguito è descritto il comportamento nel codice gestito.  
  
- <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadInterruptedException> nel thread di destinazione.  
  
- <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> fa uscire un thread da qualsiasi attesa e genera un'eccezione <xref:System.Threading.ThreadAbortException> nel thread. Per informazioni dettagliate, vedere [Eliminazione definitiva di thread](../../../docs/standard/threading/destroying-threads.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadInterruptedException>
- <xref:System.Threading.ThreadAbortException>
- [Threading](../../../docs/standard/threading/index.md)
- [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
- [Panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
