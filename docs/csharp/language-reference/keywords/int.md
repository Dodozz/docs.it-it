---
title: int - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: 6cabc2c6d4930c5d5fc88e76a17c1a6425ddd1bd
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185779"
---
# <a name="int-c-reference"></a>int (Riferimenti per C#)

`int` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.

|Tipo|Intervallo|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`int`|da -2.147.483.648 a 2.147.483.647|Valore intero a 32 bit con segno|<xref:System.Int32?displayProperty=nameWithType>|

## <a name="literals"></a>Valori letterali

È possibile dichiarare e inizializzare una variabile `int` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.  Se il valore letterale integer è esterno all'intervallo di `int`, vale a dire se è minore di <xref:System.Int32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Int32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 90.946 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `int`.

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]

> [!NOTE]
> Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario. I valori letterali decimali non hanno prefissi.

A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.
- C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.
- C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale. In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.

Di seguito sono riportati alcuni esempi.

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]

I valori letterali integer possono includere anche un suffisso che denoti il tipo, anche se non è disponibile alcun suffisso che denoti il tipo `int`. Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:

1. `int`
2. [uint](../../../csharp/language-reference/keywords/uint.md)
3. [long](../../../csharp/language-reference/keywords/long.md)
4. [ulong](../../../csharp/language-reference/keywords/ulong.md)

In questi esempi il valore letterale 90946 è di tipo `int`.

## <a name="conversions"></a>Conversioni

Si verifica una conversione implicita predefinita da `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md). Ad esempio:

```csharp
// '123' is an int, so an implicit conversion takes place here:
float f = 123;
```

Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`. L'istruzione di assegnazione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast:

```csharp
long aLong = 22;
int i1 = aLong;       // Error: no implicit conversion from long.
int i2 = (int)aLong;  // OK: explicit conversion.
```

Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `int`. L'istruzione seguente, ad esempio, genera un errore di compilazione, a meno che non venga usato un cast esplicito:

```csharp
int x = 3.0;         // Error: no implicit conversion from double.
int y = (int)3.0;    // OK: explicit conversion.
```

Per altre informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.Int32>
- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
