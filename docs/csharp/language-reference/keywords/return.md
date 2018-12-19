---
title: Istruzione return - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 058dc1d51099196559bee4ec2b96dc883e813f93
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236557"
---
# <a name="return-c-reference"></a><span data-ttu-id="e900a-102">return (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e900a-102">return (C# Reference)</span></span>

<span data-ttu-id="e900a-103">L'istruzione `return` termina l'esecuzione del metodo in cui viene visualizzata e restituisce il controllo al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e900a-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="e900a-104">Può restituire anche un valore facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e900a-104">It can also return an optional value.</span></span> <span data-ttu-id="e900a-105">Se il metodo è un tipo `void`, l'istruzione `return` può essere omessa.</span><span class="sxs-lookup"><span data-stu-id="e900a-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="e900a-106">Se l'istruzione return è all'interno di un blocco `try`, il blocco `finally`, se presente, verrà eseguito prima che il controllo venga restituito al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e900a-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="e900a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e900a-107">Example</span></span>

 <span data-ttu-id="e900a-108">Nell'esempio seguente il metodo `CalculateArea()` restituisce la variabile locale `area` come valore [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="e900a-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](double.md) value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="e900a-109">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e900a-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e900a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e900a-110">See also</span></span>

- [<span data-ttu-id="e900a-111">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e900a-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e900a-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e900a-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e900a-113">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e900a-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e900a-114">Istruzione return</span><span class="sxs-lookup"><span data-stu-id="e900a-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
- [<span data-ttu-id="e900a-115">Istruzioni di spostamento</span><span class="sxs-lookup"><span data-stu-id="e900a-115">Jump Statements</span></span>](jump-statements.md)
