---
title: Conversioni di puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 13330e5417f75a3108e31af415465c2ed6f118d9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241957"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="d31cc-102">Conversioni di puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d31cc-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="d31cc-103">Nella tabella seguente sono illustrate le conversioni di puntatori implicite predefinite.</span><span class="sxs-lookup"><span data-stu-id="d31cc-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="d31cc-104">Le conversioni implicite possono avere luogo in numerose situazioni, ad esempio le chiamate di metodi e le istruzioni di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d31cc-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="d31cc-105">Conversioni di puntatori implicite</span><span class="sxs-lookup"><span data-stu-id="d31cc-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="d31cc-106">Da</span><span class="sxs-lookup"><span data-stu-id="d31cc-106">From</span></span>|<span data-ttu-id="d31cc-107">A</span><span class="sxs-lookup"><span data-stu-id="d31cc-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d31cc-108">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-108">Any pointer type</span></span>|<span data-ttu-id="d31cc-109">void\*</span><span class="sxs-lookup"><span data-stu-id="d31cc-109">void\*</span></span>|  
|<span data-ttu-id="d31cc-110">Null</span><span class="sxs-lookup"><span data-stu-id="d31cc-110">null</span></span>|<span data-ttu-id="d31cc-111">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="d31cc-112">La conversione di puntatori esplicita consente di usare un'espressione cast per eseguire conversioni nei casi in cui non è possibile la conversione implicita.</span><span class="sxs-lookup"><span data-stu-id="d31cc-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="d31cc-113">La tabella seguente illustra queste conversioni.</span><span class="sxs-lookup"><span data-stu-id="d31cc-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="d31cc-114">Conversioni di puntatori esplicite</span><span class="sxs-lookup"><span data-stu-id="d31cc-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="d31cc-115">Da</span><span class="sxs-lookup"><span data-stu-id="d31cc-115">From</span></span>|<span data-ttu-id="d31cc-116">A</span><span class="sxs-lookup"><span data-stu-id="d31cc-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="d31cc-117">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-117">Any pointer type</span></span>|<span data-ttu-id="d31cc-118">Qualsiasi altro tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-118">Any other pointer type</span></span>|  
|<span data-ttu-id="d31cc-119">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="d31cc-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="d31cc-120">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-120">Any pointer type</span></span>|  
|<span data-ttu-id="d31cc-121">Qualsiasi tipo di puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-121">Any pointer type</span></span>|<span data-ttu-id="d31cc-122">sbyte, byte, short, ushort, int, uint, long o ulong</span><span class="sxs-lookup"><span data-stu-id="d31cc-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d31cc-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="d31cc-123">Example</span></span>  
 <span data-ttu-id="d31cc-124">Nell'esempio seguente, un puntatore a `int` viene convertito in un puntatore a `byte`.</span><span class="sxs-lookup"><span data-stu-id="d31cc-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="d31cc-125">Osservare come il puntatore punti al byte della variabile con l'indirizzo più basso.</span><span class="sxs-lookup"><span data-stu-id="d31cc-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="d31cc-126">Quando si incrementa successivamente il risultato, fino a raggiungere la dimensione di `int` (4 byte), è possibile visualizzare i byte rimanenti della variabile.</span><span class="sxs-lookup"><span data-stu-id="d31cc-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d31cc-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d31cc-127">See Also</span></span>

- [<span data-ttu-id="d31cc-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d31cc-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d31cc-129">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="d31cc-129">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="d31cc-130">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="d31cc-130">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="d31cc-131">Tipi</span><span class="sxs-lookup"><span data-stu-id="d31cc-131">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="d31cc-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="d31cc-132">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="d31cc-133">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="d31cc-133">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="d31cc-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="d31cc-134">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
