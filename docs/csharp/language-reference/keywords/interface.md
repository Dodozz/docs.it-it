---
title: interface (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 4adc7ba106e0044ba6aff94ea3180d9c8e3ded7b
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "48872943"
---
# <a name="interface-c-reference"></a><span data-ttu-id="c485b-102">interface (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c485b-102">interface (C# Reference)</span></span>

<span data-ttu-id="c485b-103">Un'interfaccia contiene solo le firme di [metodi](../../programming-guide/classes-and-structs/methods.md), [proprietà](../../programming-guide/classes-and-structs/properties.md), [eventi](../../programming-guide/events/index.md) o [indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="c485b-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="c485b-104">Una classe o uno struct che implementa l'interfaccia deve implementarne i membri specificati nella definizione dell'interfaccia stessa.</span><span class="sxs-lookup"><span data-stu-id="c485b-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="c485b-105">Nell'esempio seguente, la classe `ImplementationClass` deve implementare un metodo denominato `SampleMethod` che è privo di parametri e restituisce `void`.</span><span class="sxs-lookup"><span data-stu-id="c485b-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="c485b-106">Per altre informazioni e altri esempi, vedere [Interfacce](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="c485b-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c485b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c485b-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="c485b-108">Un'interfaccia può essere membro di uno spazio dei nomi o di una classe e contenere firme dei seguenti membri:</span><span class="sxs-lookup"><span data-stu-id="c485b-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="c485b-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="c485b-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="c485b-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c485b-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="c485b-111">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="c485b-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="c485b-112">Eventi</span><span class="sxs-lookup"><span data-stu-id="c485b-112">Events</span></span>](event.md)

<span data-ttu-id="c485b-113">Un'interfaccia può ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="c485b-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="c485b-114">Quando un elenco di tipi di base contiene interfacce e una classe di base, la classe di base deve precedere le interfacce.</span><span class="sxs-lookup"><span data-stu-id="c485b-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="c485b-115">Una classe che implementa un'interfaccia può implementare in modo esplicito i membri di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c485b-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="c485b-116">Non è possibile accedere a un membro implementato in modo esplicito tramite un'istanza di classe, ma solo tramite un'istanza dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c485b-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="c485b-117">Per altri dettagli e altri esempi di codice sull'implementazione esplicita delle interfacce, vedere [Implementazione esplicita dell'interfaccia](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="c485b-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="c485b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c485b-118">Example</span></span>

<span data-ttu-id="c485b-119">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c485b-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="c485b-120">In questo esempio l'interfaccia contiene la dichiarazione di proprietà e la classe contiene l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="c485b-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="c485b-121">Qualsiasi istanza di una classe che implementa `IPoint` presenta proprietà `x` e `y` di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="c485b-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="c485b-122">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c485b-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c485b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c485b-123">See also</span></span>

- [<span data-ttu-id="c485b-124">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c485b-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c485b-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c485b-125">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="c485b-126">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c485b-126">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="c485b-127">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="c485b-127">Reference Types</span></span>](reference-types.md)  
- [<span data-ttu-id="c485b-128">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c485b-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)  
- [<span data-ttu-id="c485b-129">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="c485b-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)  
- [<span data-ttu-id="c485b-130">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="c485b-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)  
- [<span data-ttu-id="c485b-131">class</span><span class="sxs-lookup"><span data-stu-id="c485b-131">class</span></span>](class.md)  
- [<span data-ttu-id="c485b-132">struct</span><span class="sxs-lookup"><span data-stu-id="c485b-132">struct</span></span>](struct.md)  
- [<span data-ttu-id="c485b-133">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c485b-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
