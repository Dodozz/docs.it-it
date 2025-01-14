---
title: throw - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4536a5caa789712227bfd637d65cfc4c22adf80
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422697"
---
# <a name="throw-c-reference"></a>throw (Riferimenti per C#)

Segnala l'occorrenza di un'eccezione durante l'esecuzione del programma.  
  
## <a name="remarks"></a>Note

La sintassi di `throw` è:

```csharp
throw [e]
```

dove `e` è un'istanza di una classe derivata da <xref:System.Exception?displayProperty=nameWithType>. Nell'esempio seguente l'istruzione `throw` viene usata per generare una <xref:System.IndexOutOfRangeException>, se l'argomento passato a un metodo denominato `GetNumber` non corrisponde a un indice valido di una matrice interna.

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

I caller al metodo usano quindi un blocco `try-catch` o `try-catch-finally` per gestire l'eccezione generata. L'esempio seguente gestisce l'eccezione generata dal metodo `GetNumber`.

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a>Nuova generazione di un'eccezione

È possibile anche usare `throw` in un blocco `catch` per generare nuovamente un'eccezione gestita in un blocco `catch`.  In questo caso, `throw` non accetta un operando di eccezione. È particolarmente utile quando un metodo passa un argomento da un caller a un altro metodo di raccolta e il metodo di raccolta genera un'eccezione che deve essere passata al caller. Nell'esempio seguente viene generata nuovamente una <xref:System.NullReferenceException>, che viene generata quando si tenta di recuperare il primo carattere di una stringa non inizializzata.

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> È possibile anche usare la sintassi `throw e` in un blocco `catch` per creare un'istanza di una nuova eccezione da passare al caller. In questo caso non viene mantenuta la traccia dello stack dell'eccezione originale, che è disponibile dalla proprietà <xref:System.Exception.StackTrace>.

## <a name="the-throw-expression"></a>Espressione `throw`

A partire da C# 7.0 è possibile usare `throw` come espressione e come istruzione. Ciò consente di generare un'eccezione in contesti non supportati in precedenza. Sono inclusi:

- [L'operatore condizionale](../operators/conditional-operator.md). Nell'esempio seguente viene usata un'espressione `throw` per generare una <xref:System.ArgumentException> se a un metodo viene passato una matrice di stringa vuota. Prima di C# 7.0, la logica avrebbe dovuto usare un'istruzione `if` / `else`.

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- [L'operatore null-coalescing](../operators/null-coalescing-operator.md). Nell'esempio seguente viene usata un'espressione `throw` con un operatore null-coalescing per generare un'eccezione, se la stringa assegnata a una proprietà `Name` è `null`.

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  

- [lambda](../../programming-guide/statements-expressions-operators/lambda-expressions.md) o metodo con corpo di espressione. L'esempio seguente illustra un metodo con corpo di espressione che genera una <xref:System.InvalidCastException> perché non è supportata una conversione in un valore <xref:System.DateTime>.

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [try-catch](try-catch.md)
- [Istruzioni try, catch e throw in C++](try-catch.md)
- [Parole chiave di C#](index.md)
- [Procedura: Generare in modo esplicito le eccezioni](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
