---
title: Costruttori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 8c5d34e5350f3ca64753f1d07cabb40712c66b88
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398532"
---
# <a name="constructors-c-programming-guide"></a>Costruttori (Guida per programmatori C#)

Quando si crea una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md), viene chiamato il relativo costruttore. Una classe o uno struct può avere più costruttori che accettano argomenti diversi. I costruttori consentono al programmatore di impostare i valori predefiniti, limitare la creazione di istanze e scrivere codice flessibile e facile da leggere. Per altre informazioni ed esempi, vedere [Utilizzo di costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) e [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="parameterless-constructors"></a>Costruttori senza parametri
  
Se non si specifica un costruttore per la classe, C# ne definisce uno per impostazione predefinita che crea istanze dell'oggetto e imposta le variabili dei membri sui valori predefiniti elencati nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md). Se non si specifica un costruttore per lo struct, C# usa un *costruttore senza parametri implicito* per inizializzare automaticamente ogni campo di un tipo valore sul rispettivo valore predefinito indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md). Per altre informazioni, vedere [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="constructor-syntax"></a>Sintassi del costruttore

Un costruttore è un metodo il cui nome è identico al nome del tipo relativo. La firma di questo metodo include solo il nome metodo e l'elenco dei parametri, ma non include un tipo restituito. L'esempio seguente illustra il costruttore di una classe denominata `Person`.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Se un costruttore può essere implementato come istruzione unica, è possibile usare una [definizione del corpo dell'espressione](../statements-expressions-operators/expression-bodied-members.md). L'esempio seguente definisce una classe `Location` il cui costruttore ha un solo parametro di stringa denominato *name*. La definizione del corpo dell'espressione assegna l'argomento al campo `locationName`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Costruttori statici

Tutti gli esempi precedenti hanno illustrato costruttori di istanza, che creano un nuovo oggetto. Una classe o uno struct può avere anche un costruttore statico, che inizializza i membri statici del tipo.  I costruttori statici non hanno parametri. Se non si specifica un costruttore statico per inizializzare campi statici, il compilatore C# inizializza i campi statici sul relativo valore predefinito come indicato nella [tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).

L'esempio seguente usa un costruttore statico per inizializzare un campo statico.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

È anche possibile definire un costruttore statico con una definizione di corpo dell'espressione, come illustrato nell'esempio seguente. 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Uso dei costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [Costruttori di istanza](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [Costruttori privati](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [Procedura: Scrivere un costruttore di copia](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [static](../../../csharp/language-reference/keywords/static.md)
- [Perché gli inizializzatori vengono eseguiti nell'ordine inverso dei costruttori? Prima parte](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
