---
title: struct - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 5317ea403575dca7ed64a5784fa9c993fa8d2f64
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633831"
---
# <a name="struct-c-reference"></a>struct (Riferimenti per C#)

Un `struct` è un tipo di valore generalmente usato per incapsulare piccoli gruppi di variabili correlate, ad esempio le coordinate di un rettangolo o le caratteristiche di un articolo in un inventario. Nell'esempio che segue è illustrata una semplice dichiarazione struct:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Osservazioni

Gli struct possono contenere anche [costruttori](../../programming-guide/classes-and-structs/constructors.md), [costanti](../../programming-guide/classes-and-structs/constants.md), [campi](../../programming-guide/classes-and-structs/fields.md), [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [indicizzatori](../../programming-guide/indexers/index.md), [operatori](../../programming-guide/statements-expressions-operators/operators.md), [eventi](../../programming-guide/events/index.md) e [tipi annidati](../../programming-guide/classes-and-structs/nested-types.md), anche se è consigliabile trasformare il tipo in una classe se sono necessari molti di questi membri.

Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

Gli struct possono implementare un'interfaccia, ma non possono ereditare da altri struct. Per questo motivo i membri di struct non possono essere dichiarati come `protected`.

Per altre informazioni, vedere [Struct](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Esempi

Per altre informazioni ed esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per i relativi esempi, vedere [Uso di struct](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Tabella dei valori predefiniti](default-values-table.md)
- [Tabella dei tipi incorporati](built-in-types-table.md)
- [Tipi](types.md)
- [Tipi valore](value-types.md)
- [class](class.md)
- [interface](interface.md)
- [Classi e struct](../../programming-guide/classes-and-structs/index.md)
