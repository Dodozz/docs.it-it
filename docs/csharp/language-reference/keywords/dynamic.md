---
title: dynamic - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: d2aef5b2ed291aab917573408abf26b9fbedfbd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540325"
---
# <a name="dynamic-c-reference"></a><span data-ttu-id="9d1da-102">dynamic (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="9d1da-102">dynamic (C# Reference)</span></span>

<span data-ttu-id="9d1da-103">`dynamic` abilita le operazioni in cui il tipo appare per ignorare il controllo del tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="9d1da-104">Queste operazioni vengono risolte in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="9d1da-105">Il tipo `dynamic` semplifica l'accesso alle API COM, ad esempio le API di automazione di Office, e anche ad API dinamiche come le librerie di IronPython e al modello DOM (Document Object Model) HTML.</span><span class="sxs-lookup"><span data-stu-id="9d1da-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="9d1da-106">Il tipo `dynamic` si comporta come tipo `object` nella maggior parte dei casi.</span><span class="sxs-lookup"><span data-stu-id="9d1da-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="9d1da-107">Tuttavia, le operazioni che contengono espressioni di tipo `dynamic` non vengono risolte o il tipo non viene verificato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="9d1da-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="9d1da-108">Il compilatore raggruppa le informazioni sull'operazione e tali informazioni successivamente vengono usate per valutare l'operazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="9d1da-109">Come parte del processo, le variabili di tipo `dynamic` vengono compilate in variabili di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="9d1da-110">Di conseguenza, il tipo `dynamic` esiste solo in fase di compilazione, non in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="9d1da-111">Nell'esempio seguente vengono messe a confronto una variabile di tipo `dynamic` e una variabile di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="9d1da-112">Per verificare il tipo di ogni variabile in fase di compilazione, posizionare il puntatore del mouse su `dyn` o `obj` nelle istruzioni `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="9d1da-113">IntelliSense visualizza **dynamic** per `dyn` e **object** per `obj`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="9d1da-114">Le istruzioni `WriteLine` visualizzano i tipi in fase di esecuzione di `dyn` e `obj`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-114">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="9d1da-115">A questo punto, entrambe hanno lo stesso tipo, un numero intero.</span><span class="sxs-lookup"><span data-stu-id="9d1da-115">At that point, both have the same type, integer.</span></span> <span data-ttu-id="9d1da-116">Viene generato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="9d1da-116">The following output is produced:</span></span>

`System.Int32`

`System.Int32`

<span data-ttu-id="9d1da-117">Per vedere la differenza tra `dyn` e `obj` in fase di compilazione, aggiungere le due righe seguenti tra le dichiarazioni e le istruzioni `WriteLine` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="9d1da-117">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="9d1da-118">Viene segnalato un errore del compilatore per il tentativo di aggiunta di un numero intero e di un oggetto nell'espressione `obj + 3`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-118">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="9d1da-119">Tuttavia non vengono segnalati errori per `dyn + 3`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-119">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="9d1da-120">L'espressione che contiene `dyn` non viene controllata in fase di compilazione perché il tipo di `dyn` è `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="9d1da-120">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

## <a name="context"></a><span data-ttu-id="9d1da-121">Contesto</span><span class="sxs-lookup"><span data-stu-id="9d1da-121">Context</span></span>

<span data-ttu-id="9d1da-122">La parola chiave `dynamic` può apparire direttamente o come componente di un tipo costruito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d1da-122">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>

- <span data-ttu-id="9d1da-123">Nelle dichiarazioni, come tipo di proprietà, campo, indicizzatore, parametro, valore restituito, variabile locale o vincolo di tipo.</span><span class="sxs-lookup"><span data-stu-id="9d1da-123">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="9d1da-124">La definizione di classe seguente usa `dynamic` in molte dichiarazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="9d1da-124">The following class definition uses `dynamic` in several different declarations.</span></span>

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- <span data-ttu-id="9d1da-125">Nelle conversioni di tipo esplicito, ad esempio il tipo di destinazione di una conversione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-125">In explicit type conversions, as the target type of a conversion.</span></span>

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- <span data-ttu-id="9d1da-126">In qualsiasi contesto in cui i tipi vengono usati come valori, ad esempio sul lato destro di un operatore `is` o un operatore `as`, o come argomento di `typeof` come parte di un tipo costruito.</span><span class="sxs-lookup"><span data-stu-id="9d1da-126">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="9d1da-127">Ad esempio, `dynamic` può essere usato nelle espressioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9d1da-127">For example, `dynamic` can be used in the following expressions.</span></span>

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a><span data-ttu-id="9d1da-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d1da-128">Example</span></span>

<span data-ttu-id="9d1da-129">Nell'esempio seguente viene usato `dynamic` in diverse dichiarazioni.</span><span class="sxs-lookup"><span data-stu-id="9d1da-129">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="9d1da-130">Il metodo `Main` confronta anche il controllo dei tipi in fase di compilazione con il controllo dei tipi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d1da-130">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

<span data-ttu-id="9d1da-131">Per altre informazioni ed esempi, vedere [Uso del tipo dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="9d1da-131">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d1da-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d1da-132">See also</span></span>

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [<span data-ttu-id="9d1da-133">Uso del tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="9d1da-133">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="9d1da-134">object</span><span class="sxs-lookup"><span data-stu-id="9d1da-134">object</span></span>](../../../csharp/language-reference/keywords/object.md)
- [<span data-ttu-id="9d1da-135">is</span><span class="sxs-lookup"><span data-stu-id="9d1da-135">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="9d1da-136">as</span><span class="sxs-lookup"><span data-stu-id="9d1da-136">as</span></span>](../../../csharp/language-reference/keywords/as.md)
- [<span data-ttu-id="9d1da-137">typeof</span><span class="sxs-lookup"><span data-stu-id="9d1da-137">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="9d1da-138">Procedura: Eseguire il cast sicuro con i criteri di ricerca e gli operatori as e is</span><span class="sxs-lookup"><span data-stu-id="9d1da-138">How to: Safely cast Using pattern matching, as, and is Operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="9d1da-139">Procedura dettagliata: Creazione e uso di oggetti dinamici</span><span class="sxs-lookup"><span data-stu-id="9d1da-139">Walkthrough: Creating and Using Dynamic Objects</span></span>](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
