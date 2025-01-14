---
title: 'Procedura: Abilitare la modalità di rilevamento thread in SpinLock'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 111ab87ca419217f425eb5d4bc9b52f5f30f0237
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644840"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Procedura: Abilitare la modalità di rilevamento thread in SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType> è un blocco di esclusione reciproca di basso livello che è possibile usare per scenari con tempi di attesa molto brevi. <xref:System.Threading.SpinLock> non è rientrante. Dopo che un thread entra nel blocco, deve uscirne correttamente prima di potervi accedere di nuovo. In genere, qualsiasi tentativo di entrare di nuovo nel blocco causerebbe un deadlock e il debug dei deadlock può rivelarsi molto difficile. Come ausilio per lo sviluppo, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supporta una modalità di rilevamento dei thread che provoca la generazione di un'eccezione quando un thread tenta di entrare di nuovo in un blocco che già lo contiene. Questo permette di individuare facilmente il punto in cui il thread non è uscito correttamente dal blocco. È possibile attivare la modalità di rilevamento dei thread usando il costruttore <xref:System.Threading.SpinLock>, che accetta un parametro di input booleano, e passando un argomento `true`. Dopo aver completato le fasi di sviluppo e test, disattivare la modalità di rilevamento dei thread per ottenere prestazioni migliori.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra la modalità di rilevamento dei thread. Le righe per l'uscita corretta dal blocco sono impostate come commento per simulare un errore di codifica che restituisce uno dei risultati seguenti:  
  
- Viene generata un'eccezione se l'oggetto <xref:System.Threading.SpinLock> è stato creato usando un argomento `true` (`True` in Visual Basic).  
  
- Viene generato un deadlock se l'oggetto <xref:System.Threading.SpinLock> è stato creato usando un argomento `false` (`False` in Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Vedere anche

- [SpinLock](../../../docs/standard/threading/spinlock.md)
