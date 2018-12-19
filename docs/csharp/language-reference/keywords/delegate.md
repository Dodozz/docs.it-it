---
title: delegate - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 233b0255121cf6e7a5283041d594e2d843f105fb
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286468"
---
# <a name="delegate-c-reference"></a>delegate (Riferimenti per C#)

La dichiarazione di un tipo delegato è simile alla firma di un metodo. Ha un valore restituito e una serie di parametri di qualsiasi tipo:

```csharp
public delegate void TestDelegate(string message);
public delegate int TestDelegate(MyType m, long num);
```

`delegate` è un tipo riferimento che può essere usato per incapsulare un metodo denominato o anonimo. I delegati sono simili ai puntatori a funzioni in C++, ma sono indipendenti dai tipi e protetti. Per le applicazioni dei delegati, vedere  [Delegati](../../../csharp/programming-guide/delegates/index.md) e [Delegati generici](../../../csharp/programming-guide/generics/generic-delegates.md).

## <a name="remarks"></a>Note

I delegati sono la base degli [eventi](../../../csharp/programming-guide/events/index.md).

È possibile creare un'istanza di un delegato associandolo a un metodo denominato o anonimo. Per altre informazioni, vedere [Metodi denominati](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) e [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).

È necessario creare un'istanza del delegato con un metodo o un'espressione lambda con tipo restituito compatibile e parametri di input. Per altre informazioni sul grado di varianza consentito nella firma del metodo, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md). Per l'uso con i metodi anonimi, è necessario dichiarare insieme il delegato e il codice da associare ad esso. In questa sezione sono descritti entrambi i metodi per la creazione di istanze di delegati.

## <a name="example"></a>Esempio

[!code-csharp[csrefKeywordsTypes#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#8)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../../csharp/language-reference/index.md)  
- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
- [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
- [Tipi riferimento](../../../csharp/language-reference/keywords/reference-types.md)  
- [Delegati](../../../csharp/programming-guide/delegates/index.md)  
- [Eventi](../../../csharp/programming-guide/events/index.md)  
- [Delegati con metodi denominati o metodi anonimi](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 
- [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
