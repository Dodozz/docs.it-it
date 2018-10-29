---
title: Parola chiave protected (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- protected
- protected_CSharpKeyword
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
ms.openlocfilehash: cc3c8f81edb68fb26be560c8635e30dfd6e7b372
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50183178"
---
# <a name="protected-c-reference"></a><span data-ttu-id="89577-102">protected (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="89577-102">protected (C# Reference)</span></span>

<span data-ttu-id="89577-103">La parola chiave `protected` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="89577-103">The `protected` keyword is a member access modifier.</span></span>

 > <span data-ttu-id="89577-104">Questa pagina illustra l'accesso `protected`.</span><span class="sxs-lookup"><span data-stu-id="89577-104">This page covers `protected` access.</span></span> <span data-ttu-id="89577-105">La parola chiave `protected` fa anche parte dei modificatori di accesso [`protected internal`](protected-internal.md) e [`private protected`](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="89577-105">The `protected` keyword is also part of the [`protected internal`](protected-internal.md) and [`private protected`](private-protected.md) access modifiers.</span></span>

<span data-ttu-id="89577-106">Un membro protetto è accessibile all'interno della classe di appartenenza e dalle istanze della classe derivata.</span><span class="sxs-lookup"><span data-stu-id="89577-106">A protected member is accessible within its class and by derived class instances.</span></span>

<span data-ttu-id="89577-107">Per un confronto di `protected` con altri modificatori di accesso, vedere [Livelli di accessibilità](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="89577-107">For a comparison of `protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="89577-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="89577-108">Example</span></span>

<span data-ttu-id="89577-109">Un membro protetto di una classe di base è accessibile in una classe derivata solo se viene eseguito l'accesso tramite il tipo di classe derivata.</span><span class="sxs-lookup"><span data-stu-id="89577-109">A protected member of a base class is accessible in a derived class only if the access occurs through the derived class type.</span></span> <span data-ttu-id="89577-110">Si consideri il segmento di codice di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="89577-110">For example, consider the following code segment:</span></span>

[!code-csharp[csrefKeywordsModifiers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#11)]

<span data-ttu-id="89577-111">L'istruzione `a.x = 10` genera un errore perché usata all'interno del metodo statico Main e non in un'istanza della classe B.</span><span class="sxs-lookup"><span data-stu-id="89577-111">The statement `a.x = 10` generates an error because it is made within the static method Main, and not an instance of class B.</span></span>

<span data-ttu-id="89577-112">I membri struct non possono essere protetti perché struct non può essere ereditato.</span><span class="sxs-lookup"><span data-stu-id="89577-112">Struct members cannot be protected because the struct cannot be inherited.</span></span>

## <a name="example"></a><span data-ttu-id="89577-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="89577-113">Example</span></span>

<span data-ttu-id="89577-114">In questo esempio la classe `DerivedPoint` è derivata da `Point`.</span><span class="sxs-lookup"><span data-stu-id="89577-114">In this example, the class `DerivedPoint` is derived from `Point`.</span></span> <span data-ttu-id="89577-115">Pertanto, è possibile accedere i membri protetti della classe di base direttamente dalla classe derivata.</span><span class="sxs-lookup"><span data-stu-id="89577-115">Therefore, you can access the protected members of the base class directly from the derived class.</span></span>

[!code-csharp[csrefKeywordsModifiers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#12)]  

<span data-ttu-id="89577-116">Se si impostano i livelli di accesso di `x` e `y` su [privato](private.md), il compilatore genererà i messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="89577-116">If you change the access levels of `x` and `y` to [private](private.md), the compiler will issue the error messages:</span></span>

`'Point.y' is inaccessible due to its protection level.`

`'Point.x' is inaccessible due to its protection level.`

## <a name="c-language-specification"></a><span data-ttu-id="89577-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="89577-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="89577-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89577-118">See also</span></span>

- [<span data-ttu-id="89577-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="89577-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="89577-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="89577-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="89577-121">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="89577-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="89577-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="89577-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="89577-123">Livelli di accessibilità</span><span class="sxs-lookup"><span data-stu-id="89577-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="89577-124">Modificatori</span><span class="sxs-lookup"><span data-stu-id="89577-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="89577-125">public</span><span class="sxs-lookup"><span data-stu-id="89577-125">public</span></span>](public.md)
- [<span data-ttu-id="89577-126">private</span><span class="sxs-lookup"><span data-stu-id="89577-126">private</span></span>](private.md)
- [<span data-ttu-id="89577-127">internal</span><span class="sxs-lookup"><span data-stu-id="89577-127">internal</span></span>](internal.md)
- <span data-ttu-id="89577-128">[Problemi di sicurezza per le parole chiave virtuali interne](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="89577-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>