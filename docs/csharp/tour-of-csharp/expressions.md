---
title: Espressioni C# - Panoramica del linguaggio C#
description: Le espressioni, gli operandi e gli operatori sono blocchi predefiniti del linguaggio C#
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 682f98d51bf4eb3c1641297972afb86956e06d3e
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212092"
---
# <a name="expressions"></a>Espressioni

Le *espressioni* sono costituite da *operandi* e *operatori*. Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi. Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`, mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.

Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori. L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.

Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:

*   Ad eccezione degli operatori di assegnazione, tutti gli operatori binari *prevedono l'associazione all'operando a sinistra*. In altri termini, le operazioni vengono eseguite da sinistra a destra. L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.
*   Gli operatori di assegnazione e gli operatori condizionali (`?:`) *prevedono l'associazione all'operando a destra*. In altri termini, le operazioni vengono eseguite da destra a sinistra. L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.

È possibile controllare la precedenza e l'associatività usando le parentesi. Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.

La maggior parte degli operatori può essere*in overload*. L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.

Di seguito sono riepilogati gli operatori di C# e sono elencate le categorie di operatori in ordine di precedenza, a partire da quella più alta. Gli operatori della stessa categoria hanno uguale precedenza. Sotto ciascuna categoria è riportato il relativo elenco di espressioni e la descrizione di ogni tipo di espressione.

* Primario
    - `x.m`: Accesso ai membri
    - `x(...)`: Chiamata a metodi e delegati
    - `x[...]`: Accesso a matrici e indicizzatori
    - `x++`: Post-incremento
    - `x--`: Post-decremento
    - `new T(...)`: Creazione di oggetti e delegati
    - `new T(...){...}`: creazione di oggetti con inizializzatore
    - `new {...}`:  inizializzatore di oggetti anonimo
    - `new T[...]`: creazione di matrici
    - `typeof(T)`: ottiene l'oggetto <xref:System.Type> per `T`
    - `checked(x)`: Valutare l'espressione in un contesto controllato (checked)
    - `unchecked(x)`: Valutare l'espressione in un contesto non controllato (unchecked)
    - `default(T)`: ottiene un valore predefinito di tipo `T`
    - `delegate {...}`: Funzione anonima (metodo anonimo)
* Unario
    - `+x`: identità
    - `-x`: Negazione
    - `!x`: Negazione logica
    - `~x`: Negazione bit per bit
    - `++x`: Pre-incremento
    - `--x`: Pre-decremento
    - `(T)x`: converte in modo esplicito `x` al tipo `T`
    - `await x`: attende in modo asincrono il completamento di `x`
* Moltiplicazione
    - `x * y`: Moltiplicazione
    - `x / y`: Divisione
    - `x % y`: Resto
* Addizione
    - `x + y`: Addizione, concatenazione di stringhe, combinazione di delegati
    - `x – y`: Sottrazione, rimozione di delegati
* Shift
    - `x << y`: Spostamento a sinistra
    - `x >> y`: Spostamento a destra
* Operatori relazionali e operatori di test del tipo
    - `x < y`: Minore di
    - `x > y`: Maggiore di
    - `x <= y`: Minore o uguale
    - `x >= y`: Maggiore o uguale a
    - `x is T`: restituisce `true` se `x` è un oggetto `T`, altrimenti `false`
    - `x as T`: restituisce `x` tipizzato come `T` oppure `null` se `x` non è un oggetto `T`
* Uguaglianza
    - `x == y`: Uguale
    - `x != y`: Diverso
* AND logico
    - `x & y`: AND Integer bit per bit, AND logico booleano
* XOR logico
    - `x ^ y`: XOR Integer bit per bit, XOR logico booleano
* OR logico
    - `x | y`: OR Integer bit per bit, OR logico booleano
* AND condizionale
    - `x && y`: restituisce `y` solo se `x` non è `false`
* OR condizionale
    - `x || y`: restituisce `y` solo se `x` non è `true`
* Null-coalescing
    - `x ?? y`: Restituisce `y` se `x` è null, altrimenti `x`
* Condizionale
    - `x ? y : z`: restituisce `y` se `x` è `true`, `z` se `x` è `false`
* Assegnazione o funzione anonima
    - `x = y`: Assegnazione
    - `x op= y`: assegnazione composta. Gli operatori supportati sono
        - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
    - `(T x) => y`: Funzione anonima (espressione lambda)

> [!div class="step-by-step"]
> [Precedente](types-and-variables.md)
> [Successivo](statements.md)