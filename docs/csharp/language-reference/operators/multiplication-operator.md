---
title: '* Operatore * - Riferimenti per C#'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333733"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4cd95-102">Operatore \* (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4cd95-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="4cd95-103">L'operatore di moltiplicazione (`*`) calcola il prodotto degli operandi.</span><span class="sxs-lookup"><span data-stu-id="4cd95-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="4cd95-104">Tutti i tipi numerici hanno operatori di moltiplicazione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4cd95-104">All numeric types have predefined multiplication operators.</span></span>

<span data-ttu-id="4cd95-105">`*` funge anche da operatore di dereferenziazione, che consente la lettura e scrittura in un puntatore.</span><span class="sxs-lookup"><span data-stu-id="4cd95-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cd95-106">Note</span><span class="sxs-lookup"><span data-stu-id="4cd95-106">Remarks</span></span>

<span data-ttu-id="4cd95-107">L'operatore `*` viene anche usato per dichiarare i tipi di puntatore e dereferenziare i puntatori.</span><span class="sxs-lookup"><span data-stu-id="4cd95-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="4cd95-108">Questo operatore può essere usato solo in contesti non sicuri, che sono identificati dall'uso della parola chiave [unsafe](../keywords/unsafe.md) e richiedono l'opzione [/unsafe](../compiler-options/unsafe-compiler-option.md) del compilatore.</span><span class="sxs-lookup"><span data-stu-id="4cd95-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../keywords/unsafe.md) keyword, and requiring the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="4cd95-109">L'operatore di dereferenziazione è noto anche come operatore di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="4cd95-109">The dereference operator is also known as the indirection operator.</span></span>

<span data-ttu-id="4cd95-110">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `*` (vedere [operator](../keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="4cd95-110">User-defined types can overload the binary `*` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="4cd95-111">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="4cd95-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="4cd95-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cd95-112">Example</span></span>

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a><span data-ttu-id="4cd95-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cd95-113">Example</span></span>

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a><span data-ttu-id="4cd95-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cd95-114">See also</span></span>

- [<span data-ttu-id="4cd95-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="4cd95-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4cd95-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4cd95-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4cd95-117">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="4cd95-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="4cd95-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="4cd95-118">C# Operators</span></span>](index.md)