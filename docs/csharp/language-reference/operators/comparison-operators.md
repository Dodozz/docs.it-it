---
title: Operatori di confronto - Riferimenti per C#
description: Informazioni sugli operatori di confronto C# che è possibile usare per controllare l'ordine dei valori numerici.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 5b6668e20e4d69b7d6bdf3e6283574f1b974ef54
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423960"
---
# <a name="comparison-operators-c-reference"></a>Operatori di confronto (Riferimenti per C#)

Gli operatori di confronto [`<` (minore di)](#less-than-operator-), [`>` (maggiore di)](#greater-than-operator-), [`<=` (minore o uguale a)](#less-than-or-equal-operator-) e [`>=` (maggiore o uguale a)](#greater-than-or-equal-operator-), noti anche come operatori relazionali, confrontano gli operandi. Questi operatori supportano tutti i tipi numerici [integrali](../builtin-types/integral-numeric-types.md) e [a virgola mobile](../keywords/floating-point-types-table.md).

> [!NOTE]
> Per gli operatori `==`, `<`, `>`, `<=` e `>=`, se uno degli operandi non è un numero (<xref:System.Double.NaN?displayProperty=nameWithType> oppure <xref:System.Single.NaN?displayProperty=nameWithType>) il risultato dell'operazione è `false`. Questo significa che il valore `NaN` non è maggiore di, minore di, né uguale a qualsiasi altro valore `double` (o `float`), incluso `NaN`. Per altre informazioni ed esempi, vedere l'articolo di riferimento per <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Anche i tipi di enumerazione supportano gli operatori di confronto. Per gli operandi dello stesso tipo [enum](../keywords/enum.md), i valori corrispondenti del tipo integrale sottostante vengono confrontati.

Gli operatori [`==` e `!=`](equality-operators.md) controllano se i relativi operandi sono uguali oppure no.

## <a name="less-than-operator-"></a>Operatore "minore di" \<

L'operatore `<` restituisce `true` se l'operando di sinistra è minore dell'operando di destra, `false` in caso contrario:

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>Operatore "maggiore di" >

L'operatore `>` restituisce `true` se l'operando di sinistra è maggiore dell'operando di destra, `false` in caso contrario:

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Operatore "minore o uguale a" \<=

L'operatore `<=` restituisce `true` se l'operando di sinistra è minore o uguale all'operatore di destra, `false` in caso contrario:

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Operatore "maggiore o uguale a" >=

L'operatore `>=` restituisce `true` se l'operando di sinistra è maggiore o uguale all'operatore di destra, `false` in caso contrario:

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Overload degli operatori

Un tipo definito dall'utente può eseguire l'[overload](../keywords/operator.md) degli operatori `<`, `>`, `<=` e `>=`.

Se un tipo esegue l'overload di uno degli operatori `<` o `>`, deve eseguire l'overload sia di `<` che di `>`. Se un tipo esegue l'overload di uno degli operatori `<=` o `>=`, deve eseguire l'overload sia di `<=` che di `>=`.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Operatori relazionali e di test del tipo](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Operatori C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Operatori di uguaglianza](equality-operators.md)
