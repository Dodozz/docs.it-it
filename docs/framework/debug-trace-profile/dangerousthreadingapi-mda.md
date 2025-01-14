---
title: MDA dangerousThreadingAPI
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46b0add67fc6bc139ef02e09190670870749d4c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61874776"
---
# <a name="dangerousthreadingapi-mda"></a>MDA dangerousThreadingAPI
L'assistente al debug gestito `dangerousThreadingAPI` viene attivato quando il metodo <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> viene chiamato per un thread diverso da quello attuale.  
  
## <a name="symptoms"></a>Sintomi  
 Un'applicazione non risponde o si blocca per un tempo imprecisato. È possibile che i dati del sistema e dell'applicazione rimangano in uno stato non prevedibile temporaneamente o anche dopo la chiusura di un'applicazione. Alcune operazioni non vengono completate come previsto.  
  
 I sintomi possono variare ampiamente a causa della casualità implicita nel problema.  
  
## <a name="cause"></a>Causa  
 Un thread viene sospeso in modo asincrono da un altro thread tramite il metodo <xref:System.Threading.Thread.Suspend%2A>. Non c'è modo di stabilire se sia sicuro sospendere un altro thread che potrebbe avere un'operazione in corso. La sospensione del thread può causare il danneggiamento dei dati o l'interruzione di invariabili. Se un thread viene sospeso e non viene mai ripreso tramite il metodo <xref:System.Threading.Thread.Resume%2A>, l'applicazione può bloccarsi per un tempo imprecisato, danneggiando i dati. Questi metodi sono stati contrassegnati come obsoleti.  
  
 Se le primitive di sincronizzazione si trovano nel thread di destinazione, vi rimarranno durante la sospensione, con la possibilità di un deadlock se un altro thread, ad esempio quello che esegue il metodo <xref:System.Threading.Thread.Suspend%2A>, tenta di acquisire un blocco sulla primitiva. In questa situazione, il problema si manifesta sotto forma di deadlock.  
  
## <a name="resolution"></a>Risoluzione  
 Evitare progettazioni che richiedano l'uso di <xref:System.Threading.Thread.Suspend%2A> e <xref:System.Threading.Thread.Resume%2A>. Per l'interazione tra thread, usare le primitive di sincronizzazione, ad esempio <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> o l'istruzione C# `lock`. Se è necessario usare questi metodi, ridurre il periodo di tempo e la quantità di codice eseguito quando il thread si trova in uno stato di sospensione.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR. Si limita a generare un report dei dati relativi alle operazioni di threading dannose.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito identifica il metodo di threading dannoso che ha causato l'attivazione dell'assistente stesso.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 Il codice di esempio seguente illustra una chiamata al metodo <xref:System.Threading.Thread.Suspend%2A> che causa l'attivazione di `dangerousThreadingAPI`.  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Istruzione lock](~/docs/csharp/language-reference/keywords/lock-statement.md)
