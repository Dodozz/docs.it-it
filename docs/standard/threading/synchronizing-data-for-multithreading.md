---
title: Sincronizzazione dei dati per il multithreading
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET Framework], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb44fad991c8184686fcda90878bae2ec53260c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617915"
---
# <a name="synchronizing-data-for-multithreading"></a>Sincronizzazione dei dati per il multithreading
Se più thread sono in grado di effettuare chiamate alle proprietà e ai metodi di un singolo oggetto, è essenziale che tali chiamate siano sincronizzate. In caso contrario un thread potrebbe interrompere le operazioni eseguite da un altro thread e l'oggetto potrebbe rimanere in uno stato non valido. Una classe i cui membri sono protetti da tali interruzioni è detta thread-safe.  
  
 L'infrastruttura CLI (Common Language Infrastructure) offre diverse strategie per sincronizzare l'accesso a membri statici e di istanza:  
  
-   Aree di codice sincronizzate. È possibile usare la classe <xref:System.Threading.Monitor> o il supporto del compilatore per questa classe per sincronizzare solo il codice di blocco necessario, migliorando le prestazioni.  
  
-   Sincronizzazione manuale. È possibile usare gli oggetti di sincronizzazione della libreria di classi .NET Framework. Vedere la [panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md), che include una descrizione della classe <xref:System.Threading.Monitor>.  
  
-   Contesti sincronizzati. È possibile utilizzare <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> per abilitare la sincronizzazione semplice e automatica per gli oggetti <xref:System.ContextBoundObject>.  
  
-   Classi delle raccolte nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType>. Queste classi consentono di eseguire operazioni di aggiunta e rimozione incorporate sincronizzate. Per altre informazioni, vedere [Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md).  
  
 Common Language Runtime offre un modello di thread in cui le classi rientrano in un numero di categorie che possono essere sincronizzate in molti modi in base ai requisiti. La tabella seguente indica il supporto di sincronizzazione disponibile per campi e metodi con una determinata categoria di sincronizzazione.  
  
|Category|Campi globali|Campi statici|Metodi statici|Campi di istanza|Metodi di istanza|Blocchi di codice specifici|  
|--------------|-------------------|-------------------|--------------------|---------------------|----------------------|--------------------------|  
|Nessuna sincronizzazione|No|No|No|No|No|No|  
|Contesto sincronizzato|No|No|No|Yes|Yes|No|  
|Aree di codice sincronizzate|No|No|Solo se contrassegnato|No|Solo se contrassegnato|Solo se contrassegnato|  
|Sincronizzazione manuale|Manuale|Manuale|Manuale|Manuale|Manuale|Manuale|  
  
## <a name="no-synchronization"></a>Nessuna sincronizzazione  
 Questa è l'impostazione predefinita per gli oggetti. Qualsiasi thread può accedere a qualsiasi metodo o campo in qualsiasi momento. Un solo thread alla volta deve accedere a questi oggetti.  
  
## <a name="manual-synchronization"></a>Sincronizzazione manuale  
 La libreria di classi .NET Framework offre una serie di classi per la sincronizzazione dei thread. Vedere [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="synchronized-code-regions"></a>Aree di codice sincronizzate  
 È possibile usare la classe <xref:System.Threading.Monitor> o una parola chiave del compilatore per sincronizzare aree di codice, metodi di istanza e metodi statici. Non esiste un supporto per i campi statici sincronizzati.  
  
 Sia Visual Basic che C# supportano il contrassegno delle aree di codice con una parola chiave del linguaggio specifico, l'istruzione `lock` in C# o l'istruzione `SyncLock` in Visual Basic. Quando il codice viene eseguito da un thread, viene effettuato un tentativo di acquisire il blocco. Se il blocco è già stato acquisito da un altro thread, il thread si blocca finché il blocco non diventa disponibile. Quando il thread esce dall'area di codice sincronizzata, il blocco viene rilasciato, indipendentemente dal modo in cui il thread esce dall'area.  
  
> [!NOTE]
>  Le istruzioni `lock` e `SyncLock` vengono implementate usando <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>. Pertanto gli altri metodi di <xref:System.Threading.Monitor> possono essere usati in combinazione all'interno dell'area sincronizzata.  
  
 Si può anche decorare un metodo con **MethodImplAttribute** e **MethodImplOptions. Synchronized**, ottenendo lo stesso effetto dell'uso di **Monitor** o di una delle parole chiave del compilatore per bloccare l'intero corpo del metodo.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> può essere usato per interrompere le operazioni di blocco di un thread, ad esempio in attesa dell'accesso a un'area di codice sincronizzata di un thread. **Thread.Interrupt** viene usato anche per interrompere l'esecuzione dei thread, ad esempio <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Non bloccare il tipo, ovvero `typeof(MyType)` in C#, `GetType(MyType)` in Visual Basic o `MyType::typeid` in C++, per proteggere i metodi `static` (metodi `Shared` in Visual Basic). Usare invece un oggetto statico privato. Analogamente, non usare `this` in C# (`Me` in Visual Basic) per bloccare i metodi di istanza. Usare invece un oggetto privato. Una classe o istanza può essere bloccata da un codice diverso dal proprio, causando potenzialmente deadlock o problemi di prestazioni.  
  
### <a name="compiler-support"></a>Supporto del compilatore  
 Visual Basic e C# supportano una parola chiave del linguaggio che usa <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> per bloccare l'oggetto. Visual Basic supporta l'istruzione [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md), C# supporta l'istruzione [lock](~/docs/csharp/language-reference/keywords/lock-statement.md).  
  
 In entrambi i casi, se viene generata un'eccezione nell'area di codice, il blocco acquisito da **lock** o **SyncLock** viene rilasciato automaticamente. I compilatori C# e Visual Basic creano un blocco **try**/**finally** con **Monitor.Enter** all'inizio del blocco try e **Monitor.Exit** nel blocco **finally**. Se viene generata un'eccezione all'interno del blocco **lock** o **SyncLock**, viene eseguito il gestore **finally** per consentire l'esecuzione di operazioni di pulizia.  
  
## <a name="synchronized-context"></a>Contesto sincronizzato  
 È possibile usare **SynchronizationAttribute** per qualsiasi **ContextBoundObject** per sincronizzare tutti i campi e i metodi di istanza. Tutti gli oggetti nello stesso dominio di contesto condividono lo stesso blocco. Più thread possono accedere ai metodi e ai campi, ma è consentito un singolo thread alla volta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>
- [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md) (Thread e threading)
- [Panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
- [Istruzione SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md)
- [Istruzione lock](~/docs/csharp/language-reference/keywords/lock-statement.md)
