---
title: Operatore &gt;&gt; - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: fc3d683f212c71620049ec6adee3d20bd5c1437c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239995"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="408cf-102">&gt;&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="408cf-102">&gt;&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="408cf-103">L'operatore di spostamento a destra (`>>`) sposta verso destra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="408cf-103">The right-shift operator (`>>`) shifts its first operand right by the number of bits specified by its second operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="408cf-104">Note</span><span class="sxs-lookup"><span data-stu-id="408cf-104">Remarks</span></span>  
 <span data-ttu-id="408cf-105">Se il primo operando è di tipo [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando (secondo operando e 0x1f).</span><span class="sxs-lookup"><span data-stu-id="408cf-105">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand (second operand & 0x1f).</span></span>  
  
 <span data-ttu-id="408cf-106">Se il primo operando è di tipo [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando (secondo operando e 0x3f).</span><span class="sxs-lookup"><span data-stu-id="408cf-106">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand (second operand & 0x3f).</span></span>  
  
 <span data-ttu-id="408cf-107">Se il primo operando è di tipo [int](../../../csharp/language-reference/keywords/int.md) o [long](../../../csharp/language-reference/keywords/long.md), lo spostamento a destra è uno spostamento aritmetico (i bit più significativi vuoti sono impostati sul bit di segno).</span><span class="sxs-lookup"><span data-stu-id="408cf-107">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [long](../../../csharp/language-reference/keywords/long.md), the right-shift is an arithmetic shift (high-order empty bits are set to the sign bit).</span></span> <span data-ttu-id="408cf-108">Se il primo operando è di tipo [uint](../../../csharp/language-reference/keywords/uint.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md), lo spostamento a destra è uno spostamento logico (i bit più significativi vengono riempiti con zero).</span><span class="sxs-lookup"><span data-stu-id="408cf-108">If the first operand is of type [uint](../../../csharp/language-reference/keywords/uint.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md), the right-shift is a logical shift (high-order bits are zero-filled).</span></span>  
  
 <span data-ttu-id="408cf-109">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `>>`: il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere [int](../../../csharp/language-reference/keywords/int.md). Per altre informazioni, vedere l'argomento relativo all'[operatore](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="408cf-109">User-defined types can overload the `>>` operator; the type of the first operand must be the user-defined type, and the type of the second operand must be [int](../../../csharp/language-reference/keywords/int.md). For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="408cf-110">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="408cf-110">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="408cf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="408cf-111">Example</span></span>  
 [!code-csharp[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="408cf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="408cf-112">See Also</span></span>

- [<span data-ttu-id="408cf-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="408cf-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="408cf-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="408cf-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="408cf-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="408cf-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
