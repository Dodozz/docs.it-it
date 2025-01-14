---
title: Asserzioni
description: Informazioni su come usare l'espressione 'assert' come una funzionalità di debug per testare le espressioni in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 5fe24195c7548e9fbb927e4b95b752c7a963c6b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642044"
---
# <a name="assertions"></a>Asserzioni

Il `assert` espressione è una funzionalità di debug che è possibile usare per testare un'espressione. In caso di errore in modalità Debug, un'asserzione genera una finestra di dialogo di errore di sistema.

## <a name="syntax"></a>Sintassi

```fsharp
assert condition
```

## <a name="remarks"></a>Note

Il `assert` espressione con tipo `bool -> unit`.

Nella sintassi precedente *condizione* rappresenta un'espressione booleana che deve essere testato. Se l'espressione restituisce `true`, esecuzione continua senza interruzioni. Se restituisce `false`, viene generata una finestra di dialogo di errore di sistema. La finestra di dialogo di errore ha una didascalia che contiene la stringa **asserzione non riuscita**. La finestra di dialogo contiene un'analisi dello stack che indica dove si è verificato l'errore di asserzione.

Il controllo delle asserzioni è abilitato solo quando si esegue la compilazione in modalità Debug. vale a dire, se la costante `DEBUG` è definito. Nel sistema del progetto, per impostazione predefinita, il `DEBUG` costante è definita nella configurazione di Debug ma non nella configurazione di rilascio.

Errore di asserzione non può essere intercettato tramite F# gestione delle eccezioni.

> [!NOTE]
> Il `assert` funzione si risolve in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

Esempio di codice seguente viene illustrato l'utilizzo del `assert` espressione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
