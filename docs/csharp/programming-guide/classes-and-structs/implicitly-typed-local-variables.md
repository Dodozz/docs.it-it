---
title: Variabili locali tipizzate in modo implicito - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 9c6f7ae5d7a579abead2a62f8fdc7c63e5c53328
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222702"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="936c5-102">Variabili locali tipizzate in modo implicito - Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="936c5-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="936c5-103">Le variabili locali possono essere dichiarate senza specificare un tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="936c5-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="936c5-104">La parola chiave `var` indica al compilatore di dedurre il tipo della variabile dall'espressione sul lato destro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="936c5-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="936c5-105">Il tipo dedotto può essere un tipo predefinito, un tipo anonimo, un tipo definito dall'utente o un tipo definito nella libreria di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="936c5-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="936c5-106">Per altre informazioni su come inizializzare matrici con `var`, vedere [Matrici tipizzate in modo implicito](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="936c5-107">Gli esempi seguenti illustrano svariati modi in cui le variabili locali possono essere dichiarate con `var`:</span><span class="sxs-lookup"><span data-stu-id="936c5-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="936c5-108">È importante comprendere che la parola chiave `var` non significa "variant" e che non indica che la variabile è debolmente tipizzata o ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="936c5-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="936c5-109">Significa semplicemente che il compilatore determina e assegna il tipo più adatto.</span><span class="sxs-lookup"><span data-stu-id="936c5-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="936c5-110">È possibile usare la parola chiave `var` nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="936c5-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="936c5-111">Per variabili locali (variabili dichiarate nell'ambito del metodo), come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="936c5-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="936c5-112">In un'istruzione di inizializzazione [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for(var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="936c5-113">In un'istruzione di inizializzazione [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach(var item in list){...}
    ```

- <span data-ttu-id="936c5-114">In un'istruzione [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="936c5-115">Per altre informazioni, vedere [Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="936c5-116">var e tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="936c5-116">var and anonymous types</span></span>

<span data-ttu-id="936c5-117">In molti casi l'uso di `var` è facoltativo ed è solo una convenzione sintattica.</span><span class="sxs-lookup"><span data-stu-id="936c5-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="936c5-118">Se però una variabile viene inizializzata con un tipo anonimo e si deve accedere alle proprietà dell'oggetto in un momento successivo, è necessario dichiarare la variabile come `var`.</span><span class="sxs-lookup"><span data-stu-id="936c5-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="936c5-119">Si tratta di uno scenario comune nelle espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="936c5-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="936c5-120">Per altre informazioni, vedere [Tipi anonimi](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="936c5-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="936c5-121">Dal punto di vista del codice sorgente, un tipo anonimo non ha nome.</span><span class="sxs-lookup"><span data-stu-id="936c5-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="936c5-122">Se una variabile di query è stata inizializzata con `var`, l'unico modo per accedere alle proprietà nella sequenza di oggetti restituita è usare `var` come tipo della variabile di iterazione nell'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="936c5-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="936c5-123">Note</span><span class="sxs-lookup"><span data-stu-id="936c5-123">Remarks</span></span>

<span data-ttu-id="936c5-124">Alle dichiarazioni di variabili tipizzate in modo implicito si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="936c5-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="936c5-125">La parola chiave `var` può essere usata solo quando una variabile locale viene dichiarata e inizializzata nella stessa istruzione. La variabile non può essere inizializzata su null, su un gruppo di metodi o su una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="936c5-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="936c5-126">Non è possibile usare `var` nei campi nell'ambito della classe.</span><span class="sxs-lookup"><span data-stu-id="936c5-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="936c5-127">Le variabili dichiarate tramite `var` non possono essere usate nell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="936c5-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="936c5-128">In altre parole, questa espressione è valida: `: int i = (i = 20);`. Questa invece genera un errore in fase di compilazione: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="936c5-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="936c5-129">Non è possibile inizializzare più variabili tipizzate in modo implicito nella stessa istruzione.</span><span class="sxs-lookup"><span data-stu-id="936c5-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="936c5-130">Se un tipo denominato `var` rientra nell'ambito, la parola chiave `var` si risolverà in tale nome di tipo e non verrà trattata come parte di una dichiarazione di variabile locale tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="936c5-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="936c5-131">`var` può anche risultare utile con le espressioni di query in cui è difficile determinare con esattezza il tipo costruito della variabile della query,</span><span class="sxs-lookup"><span data-stu-id="936c5-131">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="936c5-132">ad esempio con il raggruppamento e l'ordinamento di operazioni.</span><span class="sxs-lookup"><span data-stu-id="936c5-132">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="936c5-133">La parola chiave `var` può essere utile anche quando il tipo specifico della variabile risulta difficile da digitare con la tastiera, è ovvio o non migliora la leggibilità del codice.</span><span class="sxs-lookup"><span data-stu-id="936c5-133">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="936c5-134">`var` è utile in tal senso ad esempio con i tipi generici annidati, quali quelli usati con le operazioni di gruppo.</span><span class="sxs-lookup"><span data-stu-id="936c5-134">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="936c5-135">Nella query seguente il tipo della variabile di query è `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="936c5-135">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="936c5-136">Purché ciò sia chiaro a tutti coloro che devono gestire il codice, l'uso della tipizzazione implicita per ragioni di praticità e brevità non costituisce un problema.</span><span class="sxs-lookup"><span data-stu-id="936c5-136">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="936c5-137">L'uso di `var`, tuttavia, può quanto meno rendere più difficoltosa la comprensione del codice per gli altri sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="936c5-137">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="936c5-138">Nella documentazione di C# `var` viene quindi in genere usata solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="936c5-138">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="936c5-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="936c5-139">See also</span></span>

- [<span data-ttu-id="936c5-140">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="936c5-140">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="936c5-141">Matrici tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="936c5-141">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="936c5-142">Procedura: Usare variabili e matrici locali tipizzate in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="936c5-142">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="936c5-143">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="936c5-143">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="936c5-144">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="936c5-144">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="936c5-145">var</span><span class="sxs-lookup"><span data-stu-id="936c5-145">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="936c5-146">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="936c5-146">LINQ Query Expressions</span></span>](../linq-query-expressions/index.md)
- [<span data-ttu-id="936c5-147">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="936c5-147">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="936c5-148">for</span><span class="sxs-lookup"><span data-stu-id="936c5-148">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="936c5-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="936c5-149">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="936c5-150">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="936c5-150">using Statement</span></span>](../../language-reference/keywords/using-statement.md)