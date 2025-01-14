---
title: Sintassi dettagliata
description: Informazioni sulla differenza tra la sintassi dettagliata e leggera in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: c95965d7d9d18a0fca11663a474dbbc9375a9494
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641670"
---
# <a name="verbose-syntax"></a>Sintassi dettagliata

Sono disponibili per numerosi costrutti in due forme di sintassi di F# linguaggio: *sintassi dettagliata* e *sintassi leggera*. La sintassi dettagliata non è viene comunemente utilizzata, ma offre il vantaggio di essere meno sensibili alla rientro. La sintassi leggera è più breve e utilizza il rientro per indicare l'inizio e alla fine di costrutti, anziché, ad esempio parole chiave aggiuntive `begin`, `end`, `in`e così via. La sintassi di predefinita è la sintassi leggera. In questo argomento viene descritta la sintassi per F# viene costruito quando non è abilitata la sintassi leggera. Sintassi dettagliata è sempre abilitata, in modo che anche se si abilita la sintassi leggera, è comunque possibile usare la sintassi dettagliata per alcuni costrutti. È possibile disabilitare la sintassi leggera, utilizzando il `#light "off"` direttiva.

## <a name="table-of-constructs"></a>Tabella dei costrutti

Nella tabella seguente illustra la sintassi leggera e dettagliata per F# costrutti di linguaggio in contesti in cui è presente una differenza tra le due forme. In questa tabella, le parentesi acute (&lt;&gt;) racchiudere gli elementi della sintassi fornita dall'utente. Vedere la documentazione per ogni costrutto di linguaggio per informazioni più dettagliate sulla sintassi usata all'interno di questi costrutti.

<table>
<tr>
<th>Costrutto di linguaggio</th>
<th>Sintassi leggera</th>
<th>Sintassi dettagliata</th>
</tr>
<tr>
<td>
espressioni composte
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

nidificata `let` associazioni

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
blocco di codice
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td>record
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>classe
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td>struttura</td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>unione discriminata</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>interfaccia</td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>espressione di oggetto</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>implementazione dell'interfaccia</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>estensione del tipo</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Direttive per il compilatore](compiler-directives.md)
- [Linee guida per la formattazione del codice](code-formatting-guidelines.md)
