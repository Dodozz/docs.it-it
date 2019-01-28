---
title: Parola chiave char - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: b0aaf6c0b2f614fa5ff8611407cea567da1faafb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616315"
---
# <a name="char-c-reference"></a>char (Riferimenti per C#)

La parola chiave `char` è usata per dichiarare un'istanza della struttura <xref:System.Char?displayProperty=nameWithType> usata da .NET Framework per rappresentare un carattere Unicode. Il valore di un oggetto `Char` è un valore numerico (ordinale) a 16 bit.

 I caratteri Unicode vengono usati per rappresentare la maggior parte delle lingue scritte di tutto il mondo.

|Tipo|Intervallo|Dimensione|Tipo .NET|
|----------|-----------|----------|-------------------------|
|`char`|U+0000 a U+FFFF|Carattere Unicode a 16 bit|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a>Valori letterali

Le costanti di tipo `char` possono essere scritte come valori letterali carattere, sequenze di escape esadecimali o rappresentazioni Unicode. È anche possibile eseguire il cast dei codici a caratteri integrali. Nell'esempio seguente vengono inizializzate quattro variabili `char` con lo stesso carattere `X`:

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a>Conversioni

`char` può essere convertito in modo implicito in [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md). Non è tuttavia disponibile nessuna conversione implicita da altri tipi nel tipo `char`.

Il tipo <xref:System.Char?displayProperty=nameWithType> offre diversi metodi statici per usare i valori `char`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- <xref:System.Char>
- [Riferimenti per C#](../../../csharp/language-reference/index.md)
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
- [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabella delle conversioni numeriche implicite](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabella delle conversioni numeriche esplicite](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)
- [Stringhe](../../../csharp/programming-guide/strings/index.md)
