---
title: Come accedere a un elemento di matrice tramite un puntatore - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 57b1bebb95c1b3f24e550d554fe369d931d6f6b4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241801"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="09e65-102">Come accedere a un elemento di matrice tramite un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="09e65-102">How to access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="09e65-103">In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="09e65-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="09e65-104">L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="09e65-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="09e65-105">L'operazione p[e] è equivalente a \*(p+e).</span><span class="sxs-lookup"><span data-stu-id="09e65-105">The operation p[e] is equivalent to \*(p+e).</span></span> <span data-ttu-id="09e65-106">Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="09e65-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="09e65-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="09e65-107">Example</span></span>

<span data-ttu-id="09e65-108">In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="09e65-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="09e65-109">La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="09e65-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="09e65-110">Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="09e65-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="09e65-111">**Lettere maiuscole:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**lettere minuscole:**
**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="09e65-111">**Uppercase letters:**
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**
**Lowercase letters:**
**abcdefghijklmnopqrstuvwxyz**</span></span>

## <a name="see-also"></a><span data-ttu-id="09e65-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09e65-112">See also</span></span>

- [<span data-ttu-id="09e65-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="09e65-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="09e65-114">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="09e65-114">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="09e65-115">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="09e65-115">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="09e65-116">Tipi</span><span class="sxs-lookup"><span data-stu-id="09e65-116">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="09e65-117">unsafe</span><span class="sxs-lookup"><span data-stu-id="09e65-117">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="09e65-118">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="09e65-118">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="09e65-119">stackalloc</span><span class="sxs-lookup"><span data-stu-id="09e65-119">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
