---
title: Strutture di dati per la programmazione in parallelo
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87ea2cbb46aca87af15b2c12321322c1b048df56
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625613"
---
# <a name="data-structures-for-parallel-programming"></a>Strutture di dati per la programmazione in parallelo
In .NET Framework versione 4 sono stati introdotti diversi nuovi tipi utili nella programmazione parallela, inclusi un set di classi di raccolta simultanee, primitive di sincronizzazione leggera e tipi per l'inizializzazione differita. È possibile usare questi tipi con qualsiasi codice dell'applicazione multithreading, inclusi Task Parallel Library e PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Classi di raccolta simultanee  
 Le classi di raccolta nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> consentono di eseguire operazioni di aggiunta e rimozione thread-safe che, ove possibile, evitano i blocchi e, dove i blocchi sono necessari, usano quelli con granularità fine. Diversamente dalle raccolte introdotte in .NET Framework versioni 1.0 e 2.0, in una classe di raccolta simultanea non è necessario che il codice utente acquisisca alcun blocco quando accede agli elementi. Le classi di raccolta simultanee possono migliorare considerevolmente le prestazioni rispetto a tipi come <xref:System.Collections.ArrayList?displayProperty=nameWithType> e <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (con il blocco implementato dall'utente) negli scenari in cui più thread aggiungono e rimuovono elementi da una raccolta.  
  
 Nella tabella seguente vengono elencate le nuove classi di raccolta simultanee:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Fornisce funzionalità di blocco e limitazione per le raccolte thread-safe che implementano <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. I thread producer vengono bloccati se non sono disponibili slot o se la raccolta è completa. I thread consumer vengono bloccati se la raccolta è vuota. Questo tipo supporta anche l'accesso che non causa blocchi da parte di consumer e producer. <xref:System.Collections.Concurrent.BlockingCollection%601> può essere usata come classe di base o archivio di backup per fornire funzionalità di blocco limitazione per le classi di raccolta che supportano <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Implementazione di un contenitore thread-safe che fornisce operazioni add e get scalabili.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Tipo di dizionario simultaneo e scalabile.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Coda FIFO simultanea e scalabile.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Stack LIFO simultaneo e scalabile.|  
  
 Per altre informazioni, vedere [Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Primitive di sincronizzazione  
 Le nuove primitive di sincronizzazione nello spazio dei nomi <xref:System.Threading?displayProperty=nameWithType> consentono la concorrenza con granularità fine e prestazioni più veloci evitando i costosi meccanismi di blocco del codice multithreading legacy. Alcuni dei nuovi tipi, ad esempio <xref:System.Threading.Barrier?displayProperty=nameWithType> e <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> non hanno controparti nelle versioni precedenti di .NET Framework.  
  
 La tabella seguente elenca i nuovi tipi di sincronizzazione:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Consente a più thread di usare un algoritmo in parallelo fornendo un punto in cui ogni attività può segnalare il proprio arrivo e quindi venire bloccata finché non arrivano alcune o tutte le attività. Per altre informazioni, vedere [Barriera](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Semplifica gli scenari di fork e join fornendo un agevole meccanismo di rendezvous. Per altre informazioni, vedere [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Primitiva di sincronizzazione simile a <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim> è più semplice, ma può essere usata solo per la comunicazione all'interno di un processo.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Primitiva di sincronizzazione che limita il numero di thread che possono accedere simultaneamente a una risorsa o a un pool di risorse. Per altre informazioni, vedere [Semaphore e SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Primitiva di blocco a esclusione reciproca che fa in modo che il thread che prova ad acquisire il blocco rimanga in attesa in un ciclo, o *spin*, per un determinato periodo di tempo prima di sospendere il quantum. Negli scenari in cui si prevede che l'attesa nel blocco sarà breve, <xref:System.Threading.SpinLock> offre prestazioni migliori di altre forme di blocco. Per altre informazioni, vedere [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Tipo leggero di piccole dimensioni che ruoterà per un periodo di tempo specificato e infine metterà il thread in uno stato di attesa se il numero spin viene superato.  Per altre informazioni, vedere [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Per altre informazioni, vedere:  
  
- [Procedura: Usare SpinLock per la sincronizzazione di basso livello](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
- [Procedura: Sincronizzare operazioni simultanee con una barriera](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Classi di inizializzazione differita  
 Con l'inizializzazione differita, la memoria per un oggetto non viene allocata fino a quando non è necessaria. L'inizializzazione differita può migliorare le prestazioni distribuendo le allocazioni degli oggetti in modo uniforme per l'intera durata di un programma. È possibile abilitare l'inizializzazione differita per qualsiasi tipo personalizzato eseguendo il wrapping del tipo <xref:System.Lazy%601>.  
  
 La tabella seguente elenca i nuovi tipi di inizializzazione differita:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Fornisce l'inizializzazione differita leggera e thread-safe.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Fornisce un valore con inizializzazione differita per ogni thread e ogni thread richiama in modo differito la funzione di inizializzazione.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Fornisce metodi statici che evitano di dover allocare un'istanza di inizializzazione differita dedicata e usano invece i riferimenti per garantire che le destinazioni siano state inizializzate quando vi si accede.|  
  
 Per altre informazioni, vedere [Inizializzazione differita](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Eccezioni di aggregazione  
 Il tipo <xref:System.AggregateException?displayProperty=nameWithType> può essere usato per acquisire più eccezioni generate simultaneamente in thread separati e restituirle al thread di unione come un'unica eccezione. I tipi <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e PLINQ usano ampiamente <xref:System.AggregateException> a questo scopo. Per altre informazioni, vedere [Gestione delle eccezioni](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md) e [Procedura: Gestire le eccezioni in una query PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- <xref:System.Threading?displayProperty=nameWithType>
- [Programmazione parallela](../../../docs/standard/parallel-programming/index.md)
