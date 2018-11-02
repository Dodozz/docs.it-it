---
title: 'Cicli: espressioni while...do (F#)'
description: Vedere come while... tale espressione viene usata per l'esecuzione iterativa (ciclo) quando viene soddisfatta una condizione di test specificato.
ms.date: 05/16/2016
ms.openlocfilehash: 5cf4461669221f91cb50e238c25494f03a10bbc2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45664709"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="f4b57-103">Espressione Loops: while...do</span><span class="sxs-lookup"><span data-stu-id="f4b57-103">Loops: while...do Expression</span></span>

<span data-ttu-id="f4b57-104">Il `while...do` espressione viene usata per l'esecuzione iterativa (ciclo) quando viene soddisfatta una condizione di test specificato.</span><span class="sxs-lookup"><span data-stu-id="f4b57-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4b57-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4b57-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="f4b57-106">Note</span><span class="sxs-lookup"><span data-stu-id="f4b57-106">Remarks</span></span>

<span data-ttu-id="f4b57-107">Il *test-expression* viene valutata; in caso `true`, il *espressione corpo* viene eseguita e l'espressione di test viene valutata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f4b57-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="f4b57-108">Il *corpo-expression* deve avere tipo `unit`.</span><span class="sxs-lookup"><span data-stu-id="f4b57-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="f4b57-109">Se l'espressione di test è `false`, le entità finali dell'iterazione.</span><span class="sxs-lookup"><span data-stu-id="f4b57-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="f4b57-110">Nell'esempio seguente viene illustrato l'utilizzo del `while...do` espressione.</span><span class="sxs-lookup"><span data-stu-id="f4b57-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="f4b57-111">L'output del codice precedente è un flusso di numeri casuale compreso tra 1 e 20, l'ultimo dei quali è 10.</span><span class="sxs-lookup"><span data-stu-id="f4b57-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE]
<span data-ttu-id="f4b57-112">È possibile usare `while...do` nelle espressioni di sequenza e altre espressioni di calcolo, nel qual caso una versione personalizzata del `while...do` espressione viene usata.</span><span class="sxs-lookup"><span data-stu-id="f4b57-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="f4b57-113">Per altre informazioni, vedere [sequenze](sequences.md), [flussi di lavoro asincroni](asynchronous-workflows.md), e [espressioni di calcolo](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f4b57-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4b57-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4b57-114">See also</span></span>

- [<span data-ttu-id="f4b57-115">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f4b57-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f4b57-116">Cicli: espressione `for...in`</span><span class="sxs-lookup"><span data-stu-id="f4b57-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="f4b57-117">Cicli: espressione `for...to`</span><span class="sxs-lookup"><span data-stu-id="f4b57-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
