---
title: 'Espressioni condizionali: if... then... else'
description: Informazioni su come scrivere espressioni condizionali F# per l'esecuzione di diversi rami del codice.
ms.date: 05/16/2016
ms.openlocfilehash: db2d5ce5b75ecda171f2623c986878dcee1cf4d9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641982"
---
# <a name="conditional-expressions-ifthenelse"></a>Espressioni condizionali: `if...then...else`

Il `if...then...else` espressione esegue diversi rami del codice e restituisce un valore diverso in base all'espressione booleana specificata.

## <a name="syntax"></a>Sintassi

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Note

Nella sintassi precedente *expression1* viene eseguita quando l'espressione booleana restituisce `true`; in caso contrario, *expression2* viene eseguito.

A differenza di altri linguaggi, la `if...then...else` costrutto è un'espressione, non un'istruzione. Ciò significa che produce un valore, ovvero il valore dell'ultima espressione nel ramo che esegue. I tipi di valori prodotti in ogni ramo devono corrispondere. Se è presente non espliciti `else` branch, il tipo è `unit`. Pertanto, se il tipo del `then` ramo è qualsiasi tipo diverso da `unit`, deve essere presente un `else` ramo con lo stesso tipo restituito. Quando si concatenano `if...then...else` le espressioni, è possibile usare la parola chiave `elif` invece di `else if`; sono equivalenti.

## <a name="example"></a>Esempio

L'esempio seguente illustra come usare il `if...then...else` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
