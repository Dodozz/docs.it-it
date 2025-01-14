---
title: Delegati - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, delegates
- delegates [C#]
ms.assetid: 97de039b-c76b-4b9c-a27d-8c1e1c8d93da
ms.openlocfilehash: faab42a7a2f7dda12f32a65890b795abfe0d11ca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608723"
---
# <a name="delegates-c-programming-guide"></a>Delegati (Guida per programmatori C#)
Un [delegate](../../../csharp/language-reference/keywords/delegate.md) è un tipo che rappresenta riferimenti ai metodi con un elenco di parametri e un tipo restituito particolari. Quando si crea un'istanza di un delegato, è possibile associare l'istanza a qualsiasi metodo con una firma compatibile e un tipo restituito. Tramite l'istanza di delegato è possibile richiamare (o chiamare) il metodo.  
  
 I delegati vengono utilizzati per passare metodi come argomenti ad altri metodi. I gestori di evento non sono altro che metodi richiamati tramite delegati. Creare un metodo personalizzato e una classe, ad esempio un controllo Windows, che può chiamare tale metodo quando si verifica un determinato evento. Nell'esempio che segue viene illustrata la dichiarazione di un delegato:  
  
 [!code-csharp[csProgGuideDelegates#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#20)]  
  
 Qualsiasi metodo di qualsiasi classe o struct accessibile che corrisponde al tipo di delegato può essere assegnato al delegato. Il metodo può essere un metodo statico o di istanza. In questo modo è possibile modificare le chiamate ai metodi a livello di codice, nonché inserire nuovo codice nelle classi esistenti.  
  
> [!NOTE]
>  Nel contesto di overload dei metodi, la firma di un metodo non include il valore restituito, mentre nel contesto dei delegati, la firma include il valore restituito. In altre parole, un metodo deve restituire lo stesso tipo del delegato.  
  
 La possibilità di fare riferimento a un metodo come parametro rende i delegati ideali per la definizione di metodi di callback. È ad esempio possibile passare un riferimento a un metodo per il confronto di due oggetti passati come argomento a un algoritmo di ordinamento. Poiché il codice di confronto è in una routine separata, l'algoritmo di ordinamento può essere scritto in modo più generale.  
  
## <a name="delegates-overview"></a>Panoramica dei delegati  
 Di seguito sono riportate le proprietà dei delegati:  
  
- I delegati sono simili ai puntatori a funzione del linguaggio C++, ma sono interamente orientati agli oggetti e, a differenza dei puntatori C++ a funzioni membro, incapsulano sia un'istanza che un metodo dell'oggetto.
  
- Consentono di passare metodi come parametri.  
  
- Possono essere utilizzati per definire metodi di callback.  
  
- Possono essere concatenati, ad esempio per chiamare più metodi su un singolo evento.  
  
- Non devono corrispondere necessariamente al tipo del delegato. Per altre informazioni, vedere [Uso della varianza nei delegati](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
- In C# versione 2.0 sono stati introdotti i [metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) che consentono di passare blocchi di codice come parametri anziché un metodo definito separato. In C# 3.0 sono state introdotte le espressioni lambda per scrivere in modo più conciso i blocchi di codice in linea. I metodi anonimi e le espressioni lambda vengono compilati, in determinati contesti, in tipi delegati. Queste funzionalità sono ora note complessivamente come funzioni anonime. Per altre informazioni sulle espressioni lambda, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## <a name="in-this-section"></a>In questa sezione  
  
- [Uso dei delegati](../../../csharp/programming-guide/delegates/using-delegates.md)  
  
- [Quando utilizzare i delegati anziché le interfacce (Guida per programmatori C#)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms173173(v=vs.100))  
  
- [Delegati con metodi denominati o metodi anonimi](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
  
- [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
- [Uso della varianza nei delegati](../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)  
  
- [Procedura: Combinare delegati multicast](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)  
  
- [Procedura: Dichiarare un delegato, crearne un'istanza e usarlo](../../../csharp/programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md)  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Delegati](~/_csharplang/spec/delegates.md) nella [Specifica del linguaggio C#](../../language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="featured-book-chapters"></a>Capitoli del libro rappresentati  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni Lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Tutto su C# 3.0, terza edizione: più di 250 soluzioni per i programmatori C# 3.0)  
  
 [Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegati ed eventi) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29) (Imparare C# 3.0: concetti di base di C# 3.0)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Delegate>
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Eventi](../../../csharp/programming-guide/events/index.md)
