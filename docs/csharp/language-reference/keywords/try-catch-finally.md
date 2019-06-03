---
title: try...catch...finally - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 787005ec09a2c5c4f0e5033c83fd6a7ab7875b7e
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422162"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="18135-102">try...catch...finally (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="18135-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="18135-103">Le parole chiave `catch` e `finally` vengono in genere usate insieme per rilevare e usare le risorse in un blocco `try`, gestire situazioni anomale in un blocco `catch` e liberare le risorse nel blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="18135-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="18135-104">Per altre informazioni ed esempi sulla rigenerazione di un'eccezione, vedere [try-catch](try-catch.md) e [Generazione di eccezioni](../../../standard/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="18135-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="18135-105">Per altre informazioni sul blocco `finally`, vedere la pagina [try-finally](try-finally.md).</span><span class="sxs-lookup"><span data-stu-id="18135-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="18135-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="18135-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="18135-107">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="18135-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="18135-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18135-108">See also</span></span>

- [<span data-ttu-id="18135-109">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="18135-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="18135-110">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="18135-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="18135-111">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="18135-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="18135-112">Istruzioni try, throw e catch (C++)</span><span class="sxs-lookup"><span data-stu-id="18135-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="18135-113">throw</span><span class="sxs-lookup"><span data-stu-id="18135-113">throw</span></span>](throw.md)
- [<span data-ttu-id="18135-114">Procedura: Generare in modo esplicito le eccezioni</span><span class="sxs-lookup"><span data-stu-id="18135-114">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="18135-115">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="18135-115">using Statement</span></span>](using-statement.md)
