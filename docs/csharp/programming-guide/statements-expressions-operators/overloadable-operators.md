---
title: Operatori che supportano l'overload - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/27/2018
helpviewer_keywords:
- C# language, operator overloading
- operator overloading [C#]
ms.assetid: 390d9d01-79fc-40ab-9ed3-0bf448da1b6a
ms.openlocfilehash: c1f8570600d4479bcd07547ba643f2aeecaed0d3
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67398022"
---
# <a name="overloadable-operators-c-programming-guide"></a>Operatori che supportano l'overload (Guida per programmatori C#)

C# consente ai tipi definiti dall'utente di eseguire l'overload degli operatori definendo le funzioni membro statiche mediante la parola chiave [operator](../../language-reference/keywords/operator.md). Non tutti gli operatori, tuttavia, possono essere sottoposti a overload e gli altri sono soggetti alle restrizioni elencate in questa tabella:

| Operatori | Possibilità di overload |
| --------- | --------------- |
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [!](../../language-reference/operators/boolean-logical-operators.md#logical-negation-operator-), [~](../../language-reference/operators/bitwise-and-shift-operators.md#bitwise-complement-operator-), [++](../../language-reference/operators/arithmetic-operators.md#increment-operator-), [--](../../language-reference/operators/arithmetic-operators.md#decrement-operator---), [true](../../language-reference/operators/true-false-operators.md), [false](../../language-reference/operators/true-false-operators.md)|Questi operatori unari possono essere sottoposti a overload.|
|[+](../../language-reference/operators/addition-operator.md), [-](../../language-reference/operators/subtraction-operator.md), [\*](../../language-reference/operators/arithmetic-operators.md#multiplication-operator-), [/](../../language-reference/operators/arithmetic-operators.md#division-operator-), [%](../../language-reference/operators/arithmetic-operators.md#remainder-operator-), [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-), [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-), [^](../../language-reference/operators/boolean-logical-operators.md#logical-exclusive-or-operator-), [\<\<](../../language-reference/operators/bitwise-and-shift-operators.md#left-shift-operator-), [>>](../../language-reference/operators/bitwise-and-shift-operators.md#right-shift-operator-)|Questi operatori binari possono essere sottoposti a overload.|
|[==](../../language-reference/operators/equality-operators.md#equality-operator-), [!=](../../language-reference/operators/equality-operators.md#inequality-operator-), [\<](../../language-reference/operators/comparison-operators.md#less-than-operator-), [>](../../language-reference/operators/comparison-operators.md#greater-than-operator-), [\<=](../../language-reference/operators/comparison-operators.md#less-than-or-equal-operator-), [>=](../../language-reference/operators/comparison-operators.md#greater-than-or-equal-operator-)|Gli operatori di confronto possono essere sottoposti a overload (vedere però la nota dopo questa tabella).|
|[&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-)|Gli operatori logici condizionali non possono essere sottoposti a overload, ma vengono valutati con `&` e <code>&#124;</code> che possono essere sottoposti a overload.|
|[&#91;&#93;](../../language-reference/operators/member-access-operators.md#indexer-operator-)|L'operatore di indicizzazione matrice non può essere sottoposto a overload, ma è possibile definire gli [indicizzatori](../indexers/index.md).|
|[(T)x](../../language-reference/operators/type-testing-and-conversion-operators.md#cast-operator-)|L'operatore cast non può essere sottoposto a overload, ma è possibile definire nuovi operatori di conversione (vedere [explicit](../../language-reference/keywords/explicit.md) e [implicit](../../language-reference/keywords/implicit.md)).|
|[+=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [-=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [\*=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [/=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [%=](../../language-reference/operators/arithmetic-operators.md#compound-assignment), [&=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [&#124;=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [^=](../../language-reference/operators/boolean-logical-operators.md#compound-assignment), [\<\<=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment), [>>=](../../language-reference/operators/bitwise-and-shift-operators.md#compound-assignment)|Gli operatori di assegnazione non possono essere sottoposti a overload in modo esplicito. Quando viene eseguito l'overload di un operatore binario, viene tuttavia eseguito anche in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente. Ad esempio, `+=` viene valutato usando `+`, che può essere sottoposto a overload.|
|[=](../../language-reference/operators/assignment-operator.md), [.](../../language-reference/operators/member-access-operators.md#member-access-operator-), [?:](../../language-reference/operators/conditional-operator.md), [??](../../language-reference/operators/null-coalescing-operator.md), [->](../../language-reference/operators/pointer-related-operators.md#pointer-member-access-operator--), [=>](../../language-reference/operators/lambda-operator.md), [f(x)](../../language-reference/operators/member-access-operators.md#invocation-operator-), [as](../../language-reference/operators/type-testing-and-conversion-operators.md#as-operator), [checked](../../language-reference/keywords/checked.md), [unchecked](../../language-reference/keywords/unchecked.md), [default](../../programming-guide/statements-expressions-operators/default-value-expressions.md), [delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md), [is](../../language-reference/operators/type-testing-and-conversion-operators.md#is-operator), [new](../../language-reference/operators/new-operator.md), [sizeof](../../language-reference/keywords/sizeof.md), [typeof](../../language-reference/operators/type-testing-and-conversion-operators.md#typeof-operator)|Questi operatori non possono essere sottoposti a overload.|

> [!NOTE]
> Gli operatori di confronto, se sottoposti a overload, devono esserlo in coppie, ovvero, se `==` è sottoposto a overload, deve esserlo anche `!=`. È vero anche il contrario e se `!=` è sottoposto a overload deve esserlo anche `==`. Lo stesso vale per gli operatori di confronto `<` e `>` e per `<=` e `>=`.

Per informazioni su come eseguire l'overload di un operatore, vedere l'articolo relativo alla parola chiave [operator](../../language-reference/keywords/operator.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Istruzioni, espressioni e operatori](index.md)
- [Operatori](operators.md)
- [Operatori C#](../../language-reference/operators/index.md)
- [Why are overloaded operators always static in C#?](https://blogs.msdn.microsoft.com/ericlippert/2007/05/14/why-are-overloaded-operators-always-static-in-c/) (Perché gli operatori sottoposti a overload sono sempre statici in C#?)
