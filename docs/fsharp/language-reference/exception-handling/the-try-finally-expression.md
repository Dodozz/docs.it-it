---
title: 'Eccezioni: Espressione try...finally'
description: Informazioni su come il F# ' try... finally' espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un'eccezione.
ms.date: 05/16/2016
ms.openlocfilehash: d246bce52b5f30d5e8d7e3c36e9f7d7c48627913
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645457"
---
# <a name="exceptions-the-tryfinally-expression"></a>Eccezioni: Espressione try...finally

Il `try...finally` espressione consente di eseguire il codice di pulitura, anche se un blocco di codice genera un'eccezione.

## <a name="syntax"></a>Sintassi

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Note

Il `try...finally` espressione può essere utilizzata per eseguire il codice nel *expression2* nella sintassi precedente, indipendentemente dal fatto che viene generata un'eccezione durante l'esecuzione del *expression1*.

Il tipo della *expression2* non viene utilizzato il valore dell'espressione intera; il tipo restituito quando non si verifica un'eccezione è l'ultimo valore nella *expression1*. Quando si verifica un'eccezione, viene restituito alcun valore e trasferisce il flusso di controllo per il gestore di eccezioni corrispondente successivo lo stack di chiamate. Se non viene trovato alcun gestore di eccezioni, il programma termina. Prima viene eseguito il codice in un gestore corrispondente o il programma termina, il codice nel `finally` ramo viene eseguito.

Il codice seguente illustra l'uso del `try...finally` espressione.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

L'output nella console è come indicato di seguito.

```
Closing stream
Exception handled.
```

Come si vede dall'output, il flusso è stato chiuso prima che venisse gestita l'eccezione esterno e il file `test.txt` contiene il testo `test1`, indica che i buffer sono stati scaricati e scritti sul disco anche se l'eccezione trasferita controllo al gestore dell'eccezione esterna.

Si noti che il `try...with` costrutto è distinto dal costrutto di `try...finally` costruire. Pertanto, se il codice richiede sia una `with` blocco e una `finally` blocco, è necessario annidare i due costrutti, come nell'esempio di codice seguente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

Nel contesto delle espressioni di calcolo, tra cui espressioni di sequenza e flussi di lavoro asincroni **try... finally** espressioni possono avere un'implementazione personalizzata. Per altre informazioni, vedere [espressioni di calcolo](../computation-expressions.md).

## <a name="see-also"></a>Vedere anche

- [Gestione delle eccezioni](index.md)
- [Eccezioni: Il `try...with` espressione](the-try-with-expression.md)
