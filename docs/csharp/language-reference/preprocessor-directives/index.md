---
title: Direttive per il preprocessore C#
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: 54067777ed2e92eea263b17cce0d4cdf13ed731d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689320"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="d33fe-102">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="d33fe-102">C# preprocessor directives</span></span>
<span data-ttu-id="d33fe-103">Questa sezione contiene informazioni sulle seguenti direttive per il preprocessore C#:</span><span class="sxs-lookup"><span data-stu-id="d33fe-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="d33fe-104">#if</span><span class="sxs-lookup"><span data-stu-id="d33fe-104">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)
- [<span data-ttu-id="d33fe-105">#else</span><span class="sxs-lookup"><span data-stu-id="d33fe-105">#else</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md)
- [<span data-ttu-id="d33fe-106">#elif</span><span class="sxs-lookup"><span data-stu-id="d33fe-106">#elif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)
- [<span data-ttu-id="d33fe-107">#endif</span><span class="sxs-lookup"><span data-stu-id="d33fe-107">#endif</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)
- [<span data-ttu-id="d33fe-108">#define</span><span class="sxs-lookup"><span data-stu-id="d33fe-108">#define</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md)
- [<span data-ttu-id="d33fe-109">#undef</span><span class="sxs-lookup"><span data-stu-id="d33fe-109">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)
- [<span data-ttu-id="d33fe-110">#warning</span><span class="sxs-lookup"><span data-stu-id="d33fe-110">#warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)
- [<span data-ttu-id="d33fe-111">#error</span><span class="sxs-lookup"><span data-stu-id="d33fe-111">#error</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)
- [<span data-ttu-id="d33fe-112">#line</span><span class="sxs-lookup"><span data-stu-id="d33fe-112">#line</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-line.md)
- [<span data-ttu-id="d33fe-113">#region</span><span class="sxs-lookup"><span data-stu-id="d33fe-113">#region</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-region.md)
- [<span data-ttu-id="d33fe-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="d33fe-114">#endregion</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md)
- [<span data-ttu-id="d33fe-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="d33fe-115">#pragma</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma.md)
- [<span data-ttu-id="d33fe-116">avviso #pragma</span><span class="sxs-lookup"><span data-stu-id="d33fe-116">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)
- [<span data-ttu-id="d33fe-117">checksum #pragma</span><span class="sxs-lookup"><span data-stu-id="d33fe-117">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

<span data-ttu-id="d33fe-118">Per altre informazioni ed esempi, vedere i singoli argomenti.</span><span class="sxs-lookup"><span data-stu-id="d33fe-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="d33fe-119">Anche se il compilatore non ha un preprocessore indipendente, le direttive descritte in questa sezione vengono elaborate come se ne esistesse uno.</span><span class="sxs-lookup"><span data-stu-id="d33fe-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="d33fe-120">Vengono usate come supporto nella compilazione condizionale.</span><span class="sxs-lookup"><span data-stu-id="d33fe-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="d33fe-121">A differenza delle direttive di C e C++, non è possibile usare queste direttive per creare macro.</span><span class="sxs-lookup"><span data-stu-id="d33fe-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="d33fe-122">Una direttiva del preprocessore deve essere l'unica istruzione su una riga.</span><span class="sxs-lookup"><span data-stu-id="d33fe-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33fe-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d33fe-123">See also</span></span>

- [<span data-ttu-id="d33fe-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d33fe-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d33fe-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d33fe-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
