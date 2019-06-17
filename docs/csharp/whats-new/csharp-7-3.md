---
title: Novità di C# 7.3
description: Panoramica delle nuove funzionalità in C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: aca5c1b82253c02eccf24af1e5c45d0203d0b1b8
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832703"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="1d833-103">Novità di C# 7.3</span><span class="sxs-lookup"><span data-stu-id="1d833-103">What's new in C# 7.3</span></span>

<span data-ttu-id="1d833-104">Esistono due temi principali per C# versione 7.3.</span><span class="sxs-lookup"><span data-stu-id="1d833-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="1d833-105">Un tema comprende funzionalità che consentono al codice gestito di offrire prestazioni altrettanto elevate di quelle del codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1d833-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="1d833-106">Il secondo tema comprende miglioramenti incrementali delle funzionalità esistenti.</span><span class="sxs-lookup"><span data-stu-id="1d833-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="1d833-107">Inoltre, in questa versione sono state aggiunte nuove opzioni del compilatore.</span><span class="sxs-lookup"><span data-stu-id="1d833-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="1d833-108">Le nuove funzionalità seguenti supportano il tema del miglioramento delle prestazioni per il codice gestito:</span><span class="sxs-lookup"><span data-stu-id="1d833-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="1d833-109">È possibile accedere a campi fissi senza blocco.</span><span class="sxs-lookup"><span data-stu-id="1d833-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="1d833-110">È possibile riassegnare le variabili locali `ref`.</span><span class="sxs-lookup"><span data-stu-id="1d833-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="1d833-111">È possibile usare gli inizializzatori nelle matrici `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="1d833-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="1d833-112">È possibile usare istruzioni `fixed` con qualsiasi tipo che supporta un modello.</span><span class="sxs-lookup"><span data-stu-id="1d833-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="1d833-113">È possibile usare vincoli generici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1d833-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="1d833-114">Sono stati apportati i miglioramenti seguenti alle funzionalità esistenti:</span><span class="sxs-lookup"><span data-stu-id="1d833-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="1d833-115">È possibile testare `==` e `!=` con i tipi di tupla.</span><span class="sxs-lookup"><span data-stu-id="1d833-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="1d833-116">È possibile usare le variabili di espressione in più posizioni.</span><span class="sxs-lookup"><span data-stu-id="1d833-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="1d833-117">È possibile associare gli attributi al campo sottostante delle proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1d833-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="1d833-118">È stata migliorata la risoluzione del metodo quando gli argomenti sono diversi da `in`.</span><span class="sxs-lookup"><span data-stu-id="1d833-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="1d833-119">La risoluzione dell'overload ora presenta un minor numero di casi ambigui.</span><span class="sxs-lookup"><span data-stu-id="1d833-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="1d833-120">Le nuove opzioni del compilatore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d833-120">The new compiler options are:</span></span>

- <span data-ttu-id="1d833-121">`-publicsign` per abilitare la firma degli assembly con software open source.</span><span class="sxs-lookup"><span data-stu-id="1d833-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="1d833-122">`-pathmap` per fornire un mapping per le directory di origine.</span><span class="sxs-lookup"><span data-stu-id="1d833-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="1d833-123">Il resto di questo articolo fornisce informazioni dettagliate e collegamenti a risorse aggiuntive per ciascuno dei miglioramenti.</span><span class="sxs-lookup"><span data-stu-id="1d833-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="1d833-124">Miglioramento dell'efficienza del codice gestito</span><span class="sxs-lookup"><span data-stu-id="1d833-124">Enabling more efficient safe code</span></span>

<span data-ttu-id="1d833-125">È possibile scrivere codice C# in modo gestito con prestazioni altrettanto elevate di quelle del codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1d833-125">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="1d833-126">Il codice gestito evita classi di errori come sovraccarichi del buffer, puntatori errati e altri errori di accesso alla memoria.</span><span class="sxs-lookup"><span data-stu-id="1d833-126">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="1d833-127">Queste nuove funzionalità espandono le capacità del codice gestito verificabile.</span><span class="sxs-lookup"><span data-stu-id="1d833-127">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="1d833-128">È possibile scrivere una parte più ampia del codice usando costrutti gestiti.</span><span class="sxs-lookup"><span data-stu-id="1d833-128">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="1d833-129">Queste funzionalità rendono più semplice tale attività.</span><span class="sxs-lookup"><span data-stu-id="1d833-129">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="1d833-130">I campi di indicizzazione `fixed` non richiedono il blocco</span><span class="sxs-lookup"><span data-stu-id="1d833-130">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="1d833-131">Si prenda in considerazione lo struct seguente:</span><span class="sxs-lookup"><span data-stu-id="1d833-131">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="1d833-132">Nelle versioni precedenti di C# era necessario bloccare una variabile per accedere a uno dei valori Integer che fanno parte di `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="1d833-132">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="1d833-133">Il codice seguente viene ora compilato senza bloccare la variabile `p` in un'istruzione `fixed` separata:</span><span class="sxs-lookup"><span data-stu-id="1d833-133">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="1d833-134">La variabile `p` accede a un elemento `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="1d833-134">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="1d833-135">Non è necessario dichiarare una variabile `int*` distinta.</span><span class="sxs-lookup"><span data-stu-id="1d833-135">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="1d833-136">Si noti che è comunque necessario un contesto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="1d833-136">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="1d833-137">Nelle versioni precedenti di C# era necessario dichiarare un secondo puntatore fisso:</span><span class="sxs-lookup"><span data-stu-id="1d833-137">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="1d833-138">Per altre informazioni, vedere l'articolo sull'[istruzione `fixed`](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-138">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="1d833-139">Le variabili locali `ref` possono essere riassegnate</span><span class="sxs-lookup"><span data-stu-id="1d833-139">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="1d833-140">Ora è possibile riassegnare le variabili locali `ref` per fare riferimento a istanze diverse dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1d833-140">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="1d833-141">Il codice seguente ora consente di eseguire la compilazione:</span><span class="sxs-lookup"><span data-stu-id="1d833-141">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="1d833-142">Per altre informazioni, vedere l'articolo sui [valori restituiti `ref` e le variabili locali `ref`](../programming-guide/classes-and-structs/ref-returns.md), oltre all'articolo su [`foreach`](../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-142">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="1d833-143">Le matrici `stackalloc` supportano gli inizializzatori</span><span class="sxs-lookup"><span data-stu-id="1d833-143">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="1d833-144">In precedenza era possibile specificare i valori per gli elementi in una matrice al momento dell'inizializzazione:</span><span class="sxs-lookup"><span data-stu-id="1d833-144">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="1d833-145">Ora la stessa sintassi può essere applicata alle matrici dichiarate con `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="1d833-145">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="1d833-146">Per altre informazioni, vedere l'articolo [Operatore `stackalloc`](../language-reference/operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-146">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="1d833-147">L'istruzione `fixed` è supportata da più tipi</span><span class="sxs-lookup"><span data-stu-id="1d833-147">More types support the `fixed` statement</span></span>

<span data-ttu-id="1d833-148">L'istruzione `fixed` supportava un set di tipi limitato.</span><span class="sxs-lookup"><span data-stu-id="1d833-148">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="1d833-149">A partire da C# 7.3, qualsiasi tipo che contiene un metodo `GetPinnableReference()` che restituisce `ref T` oppure `ref readonly T` può essere `fixed`.</span><span class="sxs-lookup"><span data-stu-id="1d833-149">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="1d833-150">L'aggiunta di questa funzionalità implica che è possibile usare `fixed` con <xref:System.Span%601?displayProperty=nameWithType> e i tipi correlati.</span><span class="sxs-lookup"><span data-stu-id="1d833-150">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="1d833-151">Per altre informazioni, vedere l'articolo sull'[istruzione `fixed`](../language-reference/keywords/fixed-statement.md) nelle informazioni di riferimento sul linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1d833-151">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="1d833-152">Miglioramento dei vincoli generici</span><span class="sxs-lookup"><span data-stu-id="1d833-152">Enhanced generic constraints</span></span>

<span data-ttu-id="1d833-153">Ora è possibile specificare il tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> come vincoli di classe di base per un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="1d833-153">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="1d833-154">È anche possibile usare il nuovo vincolo `unmanaged` per specificare che un parametro di tipo deve essere un **tipo non gestito**.</span><span class="sxs-lookup"><span data-stu-id="1d833-154">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="1d833-155">Un **tipo non gestito** è un tipo che non è un tipo riferimento e non contiene alcun tipo riferimento a nessun livello di annidamento.</span><span class="sxs-lookup"><span data-stu-id="1d833-155">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="1d833-156">Per altre informazioni, vedere gli articoli su [vincoli generici `where`](../language-reference/keywords/where-generic-type-constraint.md) e [vincoli sui parametri di tipo](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-156">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="1d833-157">L'aggiunta di questi vincoli ai tipi esistenti è una [modifica incompatibile](version-update-considerations.md#incompatible-changes).</span><span class="sxs-lookup"><span data-stu-id="1d833-157">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="1d833-158">I tipi generici chiusi potrebbero non soddisfare più questi nuovi vincoli.</span><span class="sxs-lookup"><span data-stu-id="1d833-158">Closed generic types may no longer meet these new constraints.</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="1d833-159">Miglioramenti delle funzionalità esistenti</span><span class="sxs-lookup"><span data-stu-id="1d833-159">Make existing features better</span></span>

<span data-ttu-id="1d833-160">Il secondo tema comprende i miglioramenti delle funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1d833-160">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="1d833-161">Queste funzionalità migliorano la produttività durante la creazione di codice in C#.</span><span class="sxs-lookup"><span data-stu-id="1d833-161">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="1d833-162">Le tuple supportano `==` e `!=`</span><span class="sxs-lookup"><span data-stu-id="1d833-162">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="1d833-163">I tipi di tupla di C# ora supportano `==` e `!=`.</span><span class="sxs-lookup"><span data-stu-id="1d833-163">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="1d833-164">Per altre informazioni, vedere la sezione relativa all'[uguaglianza](../tuples.md#equality-and-tuples) nell'articolo sulle [tuple](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-164">For more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="1d833-165">Associare gli attributi al campo sottostante per le proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="1d833-165">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="1d833-166">Questa sintassi ora è supportata:</span><span class="sxs-lookup"><span data-stu-id="1d833-166">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="1d833-167">L'attributo `SomeThingAboutFieldAttribute` viene applicato al campo sottostante generato dal compilatore per `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="1d833-167">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="1d833-168">Per altre informazioni, vedere la sezione relativa agli [attributi](../programming-guide/concepts/attributes/index.md) nella Guida per programmatori C#.</span><span class="sxs-lookup"><span data-stu-id="1d833-168">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="1d833-169">Risoluzione dell'overload del metodo `in`</span><span class="sxs-lookup"><span data-stu-id="1d833-169">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="1d833-170">Quando si aggiungeva il modificatore dell'argomento `in`, questi due metodi causavano un'ambiguità:</span><span class="sxs-lookup"><span data-stu-id="1d833-170">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="1d833-171">Ora l'overload in base al valore (il primo nell'esempio precedente) è migliore dalla versione con il riferimento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="1d833-171">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="1d833-172">Per chiamare la versione con l'argomento di riferimento di sola lettura, è necessario includere il modificatore `in` durante la chiamata del metodo.</span><span class="sxs-lookup"><span data-stu-id="1d833-172">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="1d833-173">Questo comportamento è stato implementato come una correzione di bug.</span><span class="sxs-lookup"><span data-stu-id="1d833-173">This was implemented as a bug fix.</span></span> <span data-ttu-id="1d833-174">Non si tratta più di una situazione ambigua anche quando la versione del linguaggio è impostata su "7.2".</span><span class="sxs-lookup"><span data-stu-id="1d833-174">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="1d833-175">Per altre informazioni, vedere l'articolo sul [modificatore di parametro `in`](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-175">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="1d833-176">Estensione delle variabili di espressione negli inizializzatori</span><span class="sxs-lookup"><span data-stu-id="1d833-176">Extend expression variables in initializers</span></span>

<span data-ttu-id="1d833-177">La sintassi aggiunta in C# 7.0 per consentire le dichiarazioni di variabili `out` è stata estesa in modo da includere inizializzatori di campo, inizializzatori di proprietà, inizializzatori di costruttore e clausole di query.</span><span class="sxs-lookup"><span data-stu-id="1d833-177">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="1d833-178">Questo consente l'uso di codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1d833-178">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="1d833-179">Miglioramento dei candidati per l'overload</span><span class="sxs-lookup"><span data-stu-id="1d833-179">Improved overload candidates</span></span>

<span data-ttu-id="1d833-180">In ogni versione, le regole di risoluzione dell'overload vengono aggiornate per gestire le situazioni in cui le chiamate di metodi ambigui presentano una scelta "ovvia".</span><span class="sxs-lookup"><span data-stu-id="1d833-180">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="1d833-181">Questa versione aggiunge tre nuove regole per aiutare il compilatore a selezionare la scelta ovvia:</span><span class="sxs-lookup"><span data-stu-id="1d833-181">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="1d833-182">Quando un gruppo di metodi contiene sia membri di istanza che membri statici, il compilatore ignora i membri di istanza se il metodo è stato richiamato senza un contesto o un ricevitore di istanza.</span><span class="sxs-lookup"><span data-stu-id="1d833-182">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="1d833-183">Se il metodo è stato richiamato con un ricevitore di istanza, il compilatore ignora i membri statici.</span><span class="sxs-lookup"><span data-stu-id="1d833-183">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="1d833-184">Quando non è presente alcun ricevitore, il compilatore include solo i membri statici in un contesto statico. In caso contrario, include sia i membri statici che quelli di istanza.</span><span class="sxs-lookup"><span data-stu-id="1d833-184">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="1d833-185">Quando il ricevitore è in modo ambiguo un'istanza o un tipo, il compilatore include entrambi.</span><span class="sxs-lookup"><span data-stu-id="1d833-185">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="1d833-186">Un contesto statico, in cui non è possibile usare un ricevitore di istanza `this` implicito, include il corpo dei membri in cui non è definito `this`, ad esempio i membri statici, nonché i punti in cui non può essere usato `this`, ad esempio gli inizializzatori di campo e gli inizializzatori di costruttore.</span><span class="sxs-lookup"><span data-stu-id="1d833-186">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="1d833-187">Quando un gruppo di metodi include alcuni metodi generici i cui argomenti di tipo non soddisfano i vincoli, questi membri vengono rimossi dal set di candidati.</span><span class="sxs-lookup"><span data-stu-id="1d833-187">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="1d833-188">Per la conversione di un gruppo di metodi, i metodi candidati il cui tipo restituito non corrisponde al quello del delegato vengono rimossi dal set.</span><span class="sxs-lookup"><span data-stu-id="1d833-188">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="1d833-189">Sarà possibile notare questa modifica solo perché saranno presenti meno errori del compilatore per overload di metodi ambigui quando si sa con certezza quale metodo è preferibile.</span><span class="sxs-lookup"><span data-stu-id="1d833-189">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="1d833-190">Nuove opzioni del compilatore</span><span class="sxs-lookup"><span data-stu-id="1d833-190">New compiler options</span></span>

<span data-ttu-id="1d833-191">Le nuove opzioni del compilatore supportano nuovi scenari di compilazione e DevOps per i programmi in C#.</span><span class="sxs-lookup"><span data-stu-id="1d833-191">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="1d833-192">Firma pubblica o open source</span><span class="sxs-lookup"><span data-stu-id="1d833-192">Public or Open Source signing</span></span>

<span data-ttu-id="1d833-193">L'opzione del compilatore `-publicsign` indica al compilatore di firmare l'assembly usando una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1d833-193">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="1d833-194">L'assembly viene contrassegnato come firmato, ma la firma proviene dalla chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1d833-194">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="1d833-195">Questa opzione consente di compilare assembly firmati da progetti open source con una chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="1d833-195">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="1d833-196">Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -publicsign](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-196">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="1d833-197">pathmap</span><span class="sxs-lookup"><span data-stu-id="1d833-197">pathmap</span></span>

<span data-ttu-id="1d833-198">L'opzione del compilatore `-pathmap` indica al compilatore di sostituire i percorsi di origine dall'ambiente di compilazione con i percorsi di origine mappati.</span><span class="sxs-lookup"><span data-stu-id="1d833-198">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="1d833-199">L'opzione `-pathmap` controlla il percorso di origine scritto dal compilatore nei file PDB o per <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1d833-199">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="1d833-200">Per altre informazioni, vedere l'articolo sull'[opzione del compilatore -pathmap](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1d833-200">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
