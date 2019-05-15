---
title: Abbreviazioni dei tipi
description: Informazioni su F# digitare le abbreviazioni per assegnare un nome più significativo di un tipo per rendere il codice più facile da leggere.
ms.date: 05/16/2016
ms.openlocfilehash: 2930db1dcaa66741900bc91937aa1fd2f006c5f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641691"
---
# <a name="type-abbreviations"></a>Abbreviazioni dei tipi

Oggetto *abbreviazione di tipo* è un alias o nome alternativo per un tipo.

## <a name="syntax"></a>Sintassi

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a>Note

È possibile utilizzare le abbreviazioni dei tipi per assegnare un tipo di un nome più significativo, per rendere il codice più facile da leggere. È anche possibile utilizzarli per creare un nome facile da usare per un tipo che è altrimenti difficile da scrivere. Inoltre, è possibile utilizzare le abbreviazioni dei tipi per renderne più semplice modificare un tipo sottostante senza dover modificare tutto il codice che usa il tipo. Di seguito è un'abbreviazione di tipo semplice.

Per impostazione predefinita l'accessibilità delle abbreviazioni di tipo `public`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

Abbreviazioni dei tipi possono includere i parametri generici, come nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

Nel codice precedente, `Transform` è un'abbreviazione di tipo che rappresenta una funzione che accetta un singolo argomento di qualsiasi tipo e che restituisce un singolo valore di quel tipo stesso.

Abbreviazioni dei tipi non vengono mantenute nel codice .NET Framework MSIL. Pertanto, quando si usa un F# assembly da un altro linguaggio .NET Framework, è necessario utilizzare il nome del tipo sottostante per un tipo unitnames.

Abbreviazioni dei tipi sono utilizzabili anche in unità di misura. Per altre informazioni, vedere [unità di misura](units-of-measure.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
