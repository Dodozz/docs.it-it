---
title: Istruzione continue - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 0b3baf6eb4843ff67a3d76af06ca86ca9ec2db03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690592"
---
# <a name="continue-c-reference"></a><span data-ttu-id="61ca5-102">continue (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="61ca5-102">continue (C# Reference)</span></span>

<span data-ttu-id="61ca5-103">L'istruzione `continue` passa il controllo all'iterazione successiva dell'istruzione [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) di inclusione in cui è presente.</span><span class="sxs-lookup"><span data-stu-id="61ca5-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="61ca5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="61ca5-104">Example</span></span>

<span data-ttu-id="61ca5-105">In questo esempio viene inizializzato un contatore per il conteggio da 1 a 10.</span><span class="sxs-lookup"><span data-stu-id="61ca5-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="61ca5-106">Usando l'istruzione `continue` in combinazione con l'espressione `(i < 9)`, le istruzioni comprese tra `continue` e la fine del corpo di `for` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="61ca5-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="61ca5-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="61ca5-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="61ca5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61ca5-108">See also</span></span>

- [<span data-ttu-id="61ca5-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="61ca5-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="61ca5-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="61ca5-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="61ca5-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="61ca5-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="61ca5-112">Istruzione break</span><span class="sxs-lookup"><span data-stu-id="61ca5-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
- [<span data-ttu-id="61ca5-113">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="61ca5-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
