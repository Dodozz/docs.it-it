---
title: Confronto tra puntatori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 25bc1c7b701c36d2daf1918986eb6a8e56980990
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635143"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="b4b36-102">Confronto tra puntatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b4b36-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="b4b36-103">Per confrontare puntatori di qualsiasi tipo, è possibile applicare gli operatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4b36-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="b4b36-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="b4b36-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="b4b36-105">Gli operatori di confronto consentono di confrontare gli indirizzi dei due operandi come se fossero Unsigned Integer.</span><span class="sxs-lookup"><span data-stu-id="b4b36-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4b36-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4b36-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="b4b36-107">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="b4b36-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="b4b36-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4b36-108">See also</span></span>

- [<span data-ttu-id="b4b36-109">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b4b36-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b4b36-110">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b4b36-110">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="b4b36-111">Modifica dei puntatori</span><span class="sxs-lookup"><span data-stu-id="b4b36-111">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="b4b36-112">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="b4b36-112">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="b4b36-113">Tipi</span><span class="sxs-lookup"><span data-stu-id="b4b36-113">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="b4b36-114">unsafe</span><span class="sxs-lookup"><span data-stu-id="b4b36-114">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="b4b36-115">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="b4b36-115">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="b4b36-116">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b4b36-116">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
