---
title: Modelli di programmazione asincrona
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50d76aef201fead37923a65cfeead16638b09842
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031174"
---
# <a name="asynchronous-programming-patterns"></a>Modelli di programmazione asincrona

In .NET sono disponibili tre modelli per l'esecuzione di operazioni asincrone:  

- **Modello asincrono basato su attività (TAP)**, che usa un unico metodo per rappresentare l'inizio e il completamento di un'operazione asincrona. Il modello TAP è stato introdotto in .NET Framework 4. **È l'approccio consigliato per la programmazione asincrona in .NET.** Le parole chiave [async](~/docs/csharp/language-reference/keywords/async.md) e [await](~/docs/csharp/language-reference/keywords/await.md) in C# e gli operatori [Async](~/docs/visual-basic/language-reference/modifiers/async.md) e [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in Visual Basic aggiungono il supporto del linguaggio per TAP. Per altre informazioni, vedere [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) (Modello asincrono basato su attività, TAP).  

- **Modello asincrono basato su eventi (EAP)**, ovvero il modello legacy basato su eventi per fornire il comportamento asincrono. Richiede un metodo con il suffisso `Async` e uno o più eventi, i tipi delegati del gestore eventi e i tipi derivati da `EventArg`. EAP è stato introdotto in .NET Framework 2.0. Questo modello non è più consigliato per i nuovi progetti di sviluppo. Per ulteriori informazioni, vedere [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP).  

- Il **modello di programmazione asincrona (APM)** (chiamato anche modello <xref:System.IAsyncResult>) è il modello legacy che usa l'interfaccia <xref:System.IAsyncResult> per fornire il comportamento asincrono. In questo modello, le operazioni sincrone richiedono i metodi `Begin` e `End` (ad esempio `BeginWrite` e `EndWrite` per implementare un'operazione di scrittura asincrona). Questo modello non è più consigliato per i nuovi sviluppi. Per altre informazioni, vedere [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) (Modello di programmazione asincrona, APM).  
  
## <a name="comparison-of-patterns"></a>Confronto dei modelli

Per un rapido confronto tra le procedure delle operazioni asincrone dei tre modelli, considerare un metodo `Read` che legga una specifica quantità di rati in un determinato buffer, iniziando da uno specifico offset:  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

La controparte TAP di questo metodo espone il seguente metodo `ReadAsync` singolo:  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

La controparte EAP esporrà il seguente set di tipi e membri:  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
La controparte APM espone i metodi `BeginRead` e `EndRead`:  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a>Vedere anche

- [La programmazione asincrona in dettaglio](../async-in-depth.md)
- [Programmazione asincrona in C#](~/docs/csharp/async.md)
- [Programmazione asincrona in F#](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [Programmazione asincrona con Async e Await (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/async/index.md)
