---
title: Interfacce (F#)
description: Informazioni su come le interfacce di F# specificare set di membri correlati implementati da altre classi.
ms.date: 05/16/2016
ms.openlocfilehash: 6d7f8ee9ea17d2294933f88577c30a96975ae5d4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "47231440"
---
# <a name="interfaces"></a><span data-ttu-id="8711c-103">Interfacce</span><span class="sxs-lookup"><span data-stu-id="8711c-103">Interfaces</span></span>

<span data-ttu-id="8711c-104">*Interfacce* specificare set di membri correlati implementati da altre classi.</span><span class="sxs-lookup"><span data-stu-id="8711c-104">*Interfaces* specify sets of related members that other classes implement.</span></span>

## <a name="syntax"></a><span data-ttu-id="8711c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8711c-105">Syntax</span></span>

```fsharp
// Interface declaration:
[ attributes ]
type [accessibility-modifier] interface-name =
    [ interface ]     [ inherit base-interface-name ...]
    abstract member1 : [ argument-types1 -> ] return-type1
    abstract member2 : [ argument-types2 -> ] return-type2
    ...
[ end ]

// Implementing, inside a class type definition:
interface interface-name with
    member self-identifier.member1argument-list = method-body1
    member self-identifier.member2argument-list = method-body2

// Implementing, by using an object expression:
[ attributes ]
let class-name (argument-list) =
    { new interface-name with
        member self-identifier.member1argument-list = method-body1
        member self-identifier.member2argument-list = method-body2
        [ base-interface-definitions ]
    }
    member-list
```

## <a name="remarks"></a><span data-ttu-id="8711c-106">Note</span><span class="sxs-lookup"><span data-stu-id="8711c-106">Remarks</span></span>

<span data-ttu-id="8711c-107">Le dichiarazioni di interfaccia sono simili alle dichiarazioni di classe, ad eccezione del fatto che nessun membro viene implementato.</span><span class="sxs-lookup"><span data-stu-id="8711c-107">Interface declarations resemble class declarations except that no members are implemented.</span></span> <span data-ttu-id="8711c-108">Al contrario, tutti i membri sono astratti, come indicato dalla parola chiave `abstract`.</span><span class="sxs-lookup"><span data-stu-id="8711c-108">Instead, all the members are abstract, as indicated by the keyword `abstract`.</span></span> <span data-ttu-id="8711c-109">Non si specifica un corpo del metodo per i metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="8711c-109">You do not provide a method body for abstract methods.</span></span> <span data-ttu-id="8711c-110">Tuttavia, è possibile fornire un'implementazione predefinita includendo anche una definizione separata del membro come un metodo con il `default` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="8711c-110">However, you can provide a default implementation by also including a separate definition of the member as a method together with the `default` keyword.</span></span> <span data-ttu-id="8711c-111">In questo modo è equivalente alla creazione di un metodo virtuale in una classe di base in altri linguaggi .NET.</span><span class="sxs-lookup"><span data-stu-id="8711c-111">Doing so is equivalent to creating a virtual method in a base class in other .NET languages.</span></span> <span data-ttu-id="8711c-112">Tale metodo virtuale può essere sottoposto a override nelle classi che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8711c-112">Such a virtual method can be overridden in classes that implement the interface.</span></span>

<span data-ttu-id="8711c-113">L'accessibilità predefinita per le interfacce è `public`.</span><span class="sxs-lookup"><span data-stu-id="8711c-113">The default accessibility for interfaces is `public`.</span></span>

<span data-ttu-id="8711c-114">È facoltativamente possibile assegnare a ogni parametro del metodo un nome usando la normale sintassi di F#:</span><span class="sxs-lookup"><span data-stu-id="8711c-114">You can optionally give each method parameter a name using normal F# syntax:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24032.fs)]

<span data-ttu-id="8711c-115">Nell'esempio precedente `ISprintable` esempio, il `Print` metodo ha un solo parametro di tipo `string` con il nome `format`.</span><span class="sxs-lookup"><span data-stu-id="8711c-115">In the above `ISprintable` example, the `Print` method has a single parameter of the type `string` with the name `format`.</span></span>

<span data-ttu-id="8711c-116">Esistono due modi per implementare le interfacce: utilizzando espressioni di oggetto e utilizzando i tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="8711c-116">There are two ways to implement interfaces: by using object expressions, and by using class types.</span></span> <span data-ttu-id="8711c-117">In entrambi i casi, l'espressione di tipo o un oggetto classe fornisce i corpi dei metodi per i metodi astratti dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8711c-117">In either case, the class type or object expression provides method bodies for abstract methods of the interface.</span></span> <span data-ttu-id="8711c-118">Le implementazioni sono specifiche per ogni tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8711c-118">Implementations are specific to each type that implements the interface.</span></span> <span data-ttu-id="8711c-119">Di conseguenza, i metodi di interfaccia in diversi tipi potrebbero essere diversi da altra.</span><span class="sxs-lookup"><span data-stu-id="8711c-119">Therefore, interface methods on different types might be different from each other.</span></span>

<span data-ttu-id="8711c-120">Le parole chiave `interface` e `end`, sono facoltative che contrassegnano l'inizio e fine della definizione, quando si usa la sintassi leggera.</span><span class="sxs-lookup"><span data-stu-id="8711c-120">The keywords `interface` and `end`, which mark the start and end of the definition, are optional when you use lightweight syntax.</span></span> <span data-ttu-id="8711c-121">Se non si utilizza queste parole chiave, il compilatore prova a dedurre se il tipo è una classe o un'interfaccia analizzando i costrutti che usi.</span><span class="sxs-lookup"><span data-stu-id="8711c-121">If you do not use these keywords, the compiler attempts to infer whether the type is a class or an interface by analyzing the constructs that you use.</span></span> <span data-ttu-id="8711c-122">Se si definisce un membro o altra sintassi di classe, il tipo viene interpretato come una classe.</span><span class="sxs-lookup"><span data-stu-id="8711c-122">If you define a member or use other class syntax, the type is interpreted as a class.</span></span>

<span data-ttu-id="8711c-123">Stile di codifica .NET consiste nell'iniziare tutte le interfacce con una lettera maiuscola `I`.</span><span class="sxs-lookup"><span data-stu-id="8711c-123">The .NET coding style is to begin all interfaces with a capital `I`.</span></span>

## <a name="implementing-interfaces-by-using-class-types"></a><span data-ttu-id="8711c-124">Implementazione delle interfacce usando i tipi di classe</span><span class="sxs-lookup"><span data-stu-id="8711c-124">Implementing Interfaces by Using Class Types</span></span>

<span data-ttu-id="8711c-125">È possibile implementare una o più interfacce in un tipo di classe utilizzando il `interface` parola chiave, il nome dell'interfaccia e il `with` (parola chiave), seguito dalle definizioni del membro di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8711c-125">You can implement one or more interfaces in a class type by using the `interface` keyword, the name of the interface, and the `with` keyword, followed by the interface member definitions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2801.fs)]

<span data-ttu-id="8711c-126">Le implementazioni dell'interfaccia vengono ereditate, pertanto non è necessario che tutte le classi derivate reimplementare li.</span><span class="sxs-lookup"><span data-stu-id="8711c-126">Interface implementations are inherited, so any derived classes do not need to reimplement them.</span></span>

## <a name="calling-interface-methods"></a><span data-ttu-id="8711c-127">Chiamata di metodi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="8711c-127">Calling Interface Methods</span></span>

<span data-ttu-id="8711c-128">I metodi di interfaccia possono essere chiamati solo tramite l'interfaccia, non tramite qualsiasi oggetto del tipo che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8711c-128">Interface methods can be called only through the interface, not through any object of the type that implements the interface.</span></span> <span data-ttu-id="8711c-129">Di conseguenza, potrebbe essere necessario eseguire l'upcast al tipo di interfaccia usando il `:>` operatore o `upcast` operatore per poter chiamare questi metodi.</span><span class="sxs-lookup"><span data-stu-id="8711c-129">Thus, you might have to upcast to the interface type by using the `:>` operator or the `upcast` operator in order to call these methods.</span></span>

<span data-ttu-id="8711c-130">Per chiamare il metodo di interfaccia quando si dispone di un oggetto di tipo `SomeClass`, è necessario eseguire l'upcast di oggetto per il tipo di interfaccia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8711c-130">To call the interface method when you have an object of type `SomeClass`, you must upcast the object to the interface type, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2802.fs)]

<span data-ttu-id="8711c-131">Un'alternativa consiste nel dichiarare un metodo sull'oggetto tale upcasts e chiama il metodo di interfaccia, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8711c-131">An alternative is to declare a method on the object that upcasts and calls the interface method, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2803.fs)]

## <a name="implementing-interfaces-by-using-object-expressions"></a><span data-ttu-id="8711c-132">Implementazione delle interfacce usando le espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="8711c-132">Implementing Interfaces by Using Object Expressions</span></span>

<span data-ttu-id="8711c-133">Le espressioni di oggetto forniscono un modo breve per implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8711c-133">Object expressions provide a short way to implement an interface.</span></span> <span data-ttu-id="8711c-134">Sono utili quando non è necessario creare un tipo denominato, e si desidera semplicemente un oggetto che supporta i metodi di interfaccia senza metodi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="8711c-134">They are useful when you do not have to create a named type, and you just want an object that supports the interface methods, without any additional methods.</span></span> <span data-ttu-id="8711c-135">Nel codice seguente è illustrata un'espressione di oggetto.</span><span class="sxs-lookup"><span data-stu-id="8711c-135">An object expression is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2804.fs)]

## <a name="interface-inheritance"></a><span data-ttu-id="8711c-136">Ereditarietà dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="8711c-136">Interface Inheritance</span></span>

<span data-ttu-id="8711c-137">Le interfacce possono ereditare da una o più interfacce di base.</span><span class="sxs-lookup"><span data-stu-id="8711c-137">Interfaces can inherit from one or more base interfaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2805.fs)]

## <a name="see-also"></a><span data-ttu-id="8711c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8711c-138">See also</span></span>

- [<span data-ttu-id="8711c-139">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="8711c-139">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8711c-140">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="8711c-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="8711c-141">Classi</span><span class="sxs-lookup"><span data-stu-id="8711c-141">Classes</span></span>](classes.md)
