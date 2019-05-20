---
title: Clausola let (Riferimento C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: e9e10957e7ebe93a6dea9bbb6233ca7733f68e20
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633466"
---
# <a name="let-clause-c-reference"></a>Clausola let (Riferimento C#)

In un'espressione di query, è utile talvolta archiviare il risultato di una sottoespressione per poterlo usare in clausole successive. È possibile eseguire questa operazione con la parola chiave `let`, che crea una nuova variabile di intervallo e la inizializza con il risultato dell'espressione fornita. Dopo essere stata inizializzata con un valore, la variabile di intervallo non può essere usata per archiviare un altro valore. Può essere tuttavia sottoposta a query, se contiene un tipo che può essere sottoposto a query.

## <a name="example"></a>Esempio

Nell'esempio seguente, `let` viene usato in due modi:

1. Per creare un tipo enumerabile che può essere sottoposto a query.

2. Per consentire alla query di chiamare `ToLower` solo una volta sulla variabile di intervallo `word`. Senza usare `let`, si dovrebbe chiamare `ToLower` in ogni predicato della clausola `where`.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Parole chiave di query (LINQ)](query-keywords.md)
- [LINQ (Language-Integrated Query)](../../linq/index.md)
- [Nozioni di base su LINQ in C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [Gestire le eccezioni nelle espressioni di query](../../linq/handle-exceptions-in-query-expressions.md)
