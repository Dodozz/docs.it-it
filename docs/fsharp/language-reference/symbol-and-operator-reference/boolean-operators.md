---
title: Operatori booleani (F#)
description: Scopri gli operatori booleani che sono disponibili nel linguaggio di programmazione F#.
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45638480"
---
# <a name="boolean-operators"></a><span data-ttu-id="a0b36-103">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="a0b36-103">Boolean Operators</span></span>

<span data-ttu-id="a0b36-104">In questo argomento viene descritto il supporto per gli operatori booleani nel linguaggio F#.</span><span class="sxs-lookup"><span data-stu-id="a0b36-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="a0b36-105">Riepilogo degli operatori booleani</span><span class="sxs-lookup"><span data-stu-id="a0b36-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="a0b36-106">Nella tabella seguente sono riepilogati gli operatori booleani che sono disponibili nel linguaggio F#.</span><span class="sxs-lookup"><span data-stu-id="a0b36-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="a0b36-107">L'unico tipo supportato da questi operatori è il `bool` tipo.</span><span class="sxs-lookup"><span data-stu-id="a0b36-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="a0b36-108">Operatore</span><span class="sxs-lookup"><span data-stu-id="a0b36-108">Operator</span></span>|<span data-ttu-id="a0b36-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0b36-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="a0b36-110">Negazione booleana</span><span class="sxs-lookup"><span data-stu-id="a0b36-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="a0b36-111">OR booleano</span><span class="sxs-lookup"><span data-stu-id="a0b36-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="a0b36-112">AND booleano</span><span class="sxs-lookup"><span data-stu-id="a0b36-112">Boolean AND</span></span>|

<span data-ttu-id="a0b36-113">Il booleani AND e OR operatori seguire *valutazione di corto circuito*, vale a dire, tali operatori valutano l'espressione a destra dell'operatore solo quando è necessario determinare il risultato complessivo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="a0b36-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="a0b36-114">La seconda espressione del `&&` operatore viene valutato solo se la prima espressione viene valutata `true`; la seconda espressione delle `||` operatore viene valutato solo se la prima espressione viene valutata `false`.</span><span class="sxs-lookup"><span data-stu-id="a0b36-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0b36-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0b36-115">See also</span></span>

- [<span data-ttu-id="a0b36-116">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="a0b36-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="a0b36-117">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="a0b36-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a0b36-118">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="a0b36-118">Symbol and Operator Reference</span></span>](index.md)
