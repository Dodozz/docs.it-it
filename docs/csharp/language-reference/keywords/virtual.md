---
title: virtual - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: eede3359b195661ff89a387e9b226bc970c27942
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612571"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="19576-102">virtual (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="19576-102">virtual (C# Reference)</span></span>

<span data-ttu-id="19576-103">La parola chiave `virtual` viene usata per modificare una dichiarazione di metodo, proprietà, indicizzatore o evento e consentire che sia sottoposta a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="19576-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="19576-104">Ad esempio, questo metodo può essere sottoposto a override da qualsiasi classe che lo eredita:</span><span class="sxs-lookup"><span data-stu-id="19576-104">For example, this method can be overridden by any class that inherits it:</span></span>

```csharp
public virtual double Area() 
{
    return x * y;
}
```

<span data-ttu-id="19576-105">L'implementazione di un membro virtuale può essere modificata da un [membro di sostituzione](override.md) di una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="19576-105">The implementation of a virtual member can be changed by an [overriding member](override.md) in a derived class.</span></span> <span data-ttu-id="19576-106">Per altre informazioni sull'uso della parola chiave `virtual`, vedere [Controllo delle versioni con le parole chiave Override e New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) e [Sapere quando utilizzare le parole chiave Override e New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="19576-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="19576-107">Note</span><span class="sxs-lookup"><span data-stu-id="19576-107">Remarks</span></span>

<span data-ttu-id="19576-108">Quando viene richiamato un metodo virtuale, il tipo di runtime dell'oggetto viene controllato per verificare la presenza di un membro di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="19576-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="19576-109">Viene chiamato il membro di sostituzione nella classe più derivata e potrebbe trattarsi del membro originale, se nessuna classe derivata ha eseguito l'override del membro.</span><span class="sxs-lookup"><span data-stu-id="19576-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>

<span data-ttu-id="19576-110">Per impostazione predefinita, i metodi sono non virtuali.</span><span class="sxs-lookup"><span data-stu-id="19576-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="19576-111">Non è possibile eseguire l'override di un metodo non virtuale.</span><span class="sxs-lookup"><span data-stu-id="19576-111">You cannot override a non-virtual method.</span></span>

<span data-ttu-id="19576-112">Non è possibile usare il modificatore `virtual` con i modificatori `static`, `abstract`, `private` o `override`.</span><span class="sxs-lookup"><span data-stu-id="19576-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="19576-113">L'esempio seguente illustra una proprietà virtuale:</span><span class="sxs-lookup"><span data-stu-id="19576-113">The following example shows a virtual property:</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="19576-114">Le proprietà virtuali si comportano come i metodi astratti, ad eccezione delle differenze nella sintassi di dichiarazione e di chiamata.</span><span class="sxs-lookup"><span data-stu-id="19576-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>

- <span data-ttu-id="19576-115">Non è possibile usare il modificatore `virtual` su una proprietà static.</span><span class="sxs-lookup"><span data-stu-id="19576-115">It is an error to use the `virtual` modifier on a static property.</span></span>

- <span data-ttu-id="19576-116">Una proprietà virtuale ereditata può essere sottoposta a override in una classe derivata includendo una dichiarazione di proprietà che usa il modificatore `override`.</span><span class="sxs-lookup"><span data-stu-id="19576-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>

## <a name="example"></a><span data-ttu-id="19576-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="19576-117">Example</span></span>

<span data-ttu-id="19576-118">In questo esempio la classe `Shape` contiene le due coordinate `x`, `y`e il metodo virtuale `Area()`.</span><span class="sxs-lookup"><span data-stu-id="19576-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="19576-119">Le classi di forma diversa, ad esempio `Circle`, `Cylinder` e `Sphere`, ereditano la classe `Shape` e la superficie viene calcolata per ogni figura.</span><span class="sxs-lookup"><span data-stu-id="19576-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="19576-120">Ogni classe derivata ha la propria implementazione di override di `Area()`.</span><span class="sxs-lookup"><span data-stu-id="19576-120">Each derived class has its own override implementation of `Area()`.</span></span>

<span data-ttu-id="19576-121">Si noti che le classi ereditate `Circle`, `Sphere` e `Cylinder` usano tutte costruttori che inizializzano la classe di base, come illustrato nella seguente dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="19576-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

<span data-ttu-id="19576-122">Il programma seguente calcola e visualizza l'area appropriata per ogni figura richiamando l'implementazione corretta del metodo `Area()` in base all'oggetto associato al metodo.</span><span class="sxs-lookup"><span data-stu-id="19576-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a><span data-ttu-id="19576-123">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="19576-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="19576-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19576-124">See also</span></span>

- [<span data-ttu-id="19576-125">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="19576-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="19576-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="19576-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="19576-127">Modificatori</span><span class="sxs-lookup"><span data-stu-id="19576-127">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="19576-128">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="19576-128">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="19576-129">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="19576-129">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
- [<span data-ttu-id="19576-130">abstract</span><span class="sxs-lookup"><span data-stu-id="19576-130">abstract</span></span>](abstract.md)
- [<span data-ttu-id="19576-131">override</span><span class="sxs-lookup"><span data-stu-id="19576-131">override</span></span>](override.md)
- [<span data-ttu-id="19576-132">new</span><span class="sxs-lookup"><span data-stu-id="19576-132">new</span></span>](new.md)