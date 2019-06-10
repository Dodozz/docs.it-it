---
title: Record
description: Informazioni su come F# i record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.
ms.date: 06/09/2019
ms.openlocfilehash: cfb8de8272b479571119ae4cf91ea1d6fd5db73c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816196"
---
# <a name="records"></a><span data-ttu-id="df6ee-103">Record</span><span class="sxs-lookup"><span data-stu-id="df6ee-103">Records</span></span>

<span data-ttu-id="df6ee-104">I record rappresentano aggregazioni semplici di valori denominati, facoltativamente con membri.</span><span class="sxs-lookup"><span data-stu-id="df6ee-104">Records represent simple aggregates of named values, optionally with members.</span></span> <span data-ttu-id="df6ee-105">Reti virtuali possono essere tipi riferimento o struct.</span><span class="sxs-lookup"><span data-stu-id="df6ee-105">They can either be structs or reference types.</span></span>  <span data-ttu-id="df6ee-106">Si tratta di tipi di riferimento per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="df6ee-106">They are reference types by default.</span></span>

## <a name="syntax"></a><span data-ttu-id="df6ee-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df6ee-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] typename =
    { [ mutable ] label1 : type1;
      [ mutable ] label2 : type2;
      ... }
    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="df6ee-108">Note</span><span class="sxs-lookup"><span data-stu-id="df6ee-108">Remarks</span></span>

<span data-ttu-id="df6ee-109">Nella sintassi precedente *nomeTipo* è il nome del tipo di record, *label1* e *label2* sono nomi di valori, detti *etichette*, e *type1* e *type2* sono i tipi di questi valori.</span><span class="sxs-lookup"><span data-stu-id="df6ee-109">In the previous syntax, *typename* is the name of the record type, *label1* and *label2* are names of values, referred to as *labels*, and *type1* and *type2* are the types of these values.</span></span> <span data-ttu-id="df6ee-110">*elenco di membri* è riportato l'elenco facoltativo di membri per il tipo.</span><span class="sxs-lookup"><span data-stu-id="df6ee-110">*member-list* is the optional list of members for the type.</span></span>  <span data-ttu-id="df6ee-111">È possibile usare il `[<Struct>]` attributo per creare un record di struct, anziché un record che è un tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="df6ee-111">You can use the `[<Struct>]` attribute to create a struct record rather than a record which is a reference type.</span></span>

<span data-ttu-id="df6ee-112">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="df6ee-112">Following are some examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1901.fs)]

<span data-ttu-id="df6ee-113">Una volta ogni etichetta in una riga separata, il punto e virgola è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="df6ee-113">When each label is on a separate line, the semicolon is optional.</span></span>

<span data-ttu-id="df6ee-114">È possibile impostare i valori nelle espressioni dette *espressioni di record*.</span><span class="sxs-lookup"><span data-stu-id="df6ee-114">You can set values in expressions known as *record expressions*.</span></span> <span data-ttu-id="df6ee-115">Il compilatore deduce il tipo dalle etichette usato (se le etichette sono sufficientemente distinte da quelli di altri tipi di record).</span><span class="sxs-lookup"><span data-stu-id="df6ee-115">The compiler infers the type from the labels used (if the labels are sufficiently distinct from those of other record types).</span></span> <span data-ttu-id="df6ee-116">Le parentesi graffe ({}) racchiudono l'espressione di record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-116">Braces ({ }) enclose the record expression.</span></span> <span data-ttu-id="df6ee-117">Il codice seguente illustra un'espressione di record che inizializza un record con tre elementi di float con etichette `x`, `y` e `z`.</span><span class="sxs-lookup"><span data-stu-id="df6ee-117">The following code shows a record expression that initializes a record with three float elements with labels `x`, `y` and `z`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1907.fs)]

<span data-ttu-id="df6ee-118">Non utilizzare la forma abbreviata se è possibile che un altro tipo che ha anche le stesse etichette.</span><span class="sxs-lookup"><span data-stu-id="df6ee-118">Do not use the shortened form if there could be another type that also has the same labels.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1903.fs)]

<span data-ttu-id="df6ee-119">Le etichette del tipo dichiarato più di recente hanno la precedenza rispetto a quelli del tipo dichiarato in precedenza, pertanto nell'esempio precedente `mypoint3D` viene dedotto come `Point3D`.</span><span class="sxs-lookup"><span data-stu-id="df6ee-119">The labels of the most recently declared type take precedence over those of the previously declared type, so in the preceding example, `mypoint3D` is inferred to be `Point3D`.</span></span> <span data-ttu-id="df6ee-120">È possibile specificare in modo esplicito il tipo di record, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="df6ee-120">You can explicitly specify the record type, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1908.fs)]

<span data-ttu-id="df6ee-121">I metodi possono essere definiti per i tipi di record in modo analogo ai tipi di classe.</span><span class="sxs-lookup"><span data-stu-id="df6ee-121">Methods can be defined for record types just as for class types.</span></span>

## <a name="creating-records-by-using-record-expressions"></a><span data-ttu-id="df6ee-122">Creazione di record utilizzando espressioni di Record</span><span class="sxs-lookup"><span data-stu-id="df6ee-122">Creating Records by Using Record Expressions</span></span>

<span data-ttu-id="df6ee-123">È possibile inizializzare i record con le etichette che sono definite nel record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-123">You can initialize records by using the labels that are defined in the record.</span></span> <span data-ttu-id="df6ee-124">Un'espressione che esegue questa operazione è detta una *espressione di record*.</span><span class="sxs-lookup"><span data-stu-id="df6ee-124">An expression that does this is referred to as a *record expression*.</span></span> <span data-ttu-id="df6ee-125">Usare le parentesi graffe per racchiudere l'espressione di record e usare il punto e virgola come delimitatore.</span><span class="sxs-lookup"><span data-stu-id="df6ee-125">Use braces to enclose the record expression and use the semicolon as a delimiter.</span></span>

<span data-ttu-id="df6ee-126">Nell'esempio seguente viene illustrato come creare un record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-126">The following example shows how to create a record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1904.fs)]

<span data-ttu-id="df6ee-127">I punti e virgola dopo l'ultimo campo nell'espressione di record e nella definizione del tipo sono facoltativi, indipendentemente dal fatto che i campi sono tutti in un'unica riga.</span><span class="sxs-lookup"><span data-stu-id="df6ee-127">The semicolons after the last field in the record expression and in the type definition are optional, regardless of whether the fields are all in one line.</span></span>

<span data-ttu-id="df6ee-128">Quando si crea un record, è necessario fornire valori per ogni campo.</span><span class="sxs-lookup"><span data-stu-id="df6ee-128">When you create a record, you must supply values for each field.</span></span> <span data-ttu-id="df6ee-129">È possibile fare riferimento ai valori di altri campi nell'espressione di inizializzazione per tutti i campi.</span><span class="sxs-lookup"><span data-stu-id="df6ee-129">You cannot refer to the values of other fields in the initialization expression for any field.</span></span>

<span data-ttu-id="df6ee-130">Nel codice seguente, il tipo di `myRecord2` viene dedotto dai nomi dei campi.</span><span class="sxs-lookup"><span data-stu-id="df6ee-130">In the following code, the type of `myRecord2` is inferred from the names of the fields.</span></span> <span data-ttu-id="df6ee-131">Facoltativamente, è possibile specificare il nome del tipo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="df6ee-131">Optionally, you can specify the type name explicitly.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="df6ee-132">Un'altra forma di costruzione di record può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="df6ee-132">Another form of record construction can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span> <span data-ttu-id="df6ee-133">La riga di codice seguente illustra questa soluzione.</span><span class="sxs-lookup"><span data-stu-id="df6ee-133">The following line of code illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

<span data-ttu-id="df6ee-134">Questa forma di espressione di record viene chiamata il *copiare e aggiornare l'espressione di record*.</span><span class="sxs-lookup"><span data-stu-id="df6ee-134">This form of the record expression is called the *copy and update record expression*.</span></span>

<span data-ttu-id="df6ee-135">I record non sono modificabili per impostazione predefinita. Tuttavia, è possibile creare facilmente record modificati tramite un'espressione di copia e l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="df6ee-135">Records are immutable by default; however, you can easily create modified records by using a copy and update expression.</span></span> <span data-ttu-id="df6ee-136">È possibile specificare in modo esplicito un campo modificabile.</span><span class="sxs-lookup"><span data-stu-id="df6ee-136">You can also explicitly specify a mutable field.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1909.fs)]

<span data-ttu-id="df6ee-137">Non usare l'attributo DefaultValue con i campi di record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-137">Don't use the DefaultValue attribute with record fields.</span></span> <span data-ttu-id="df6ee-138">Un approccio migliore è definire le istanze predefinite di record con i campi che vengono inizializzati sui valori predefiniti e quindi utilizzare una copia e aggiornare l'espressione di record per impostare tutti i campi che differiscono dai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="df6ee-138">A better approach is to define default instances of records with fields that are initialized to default values and then use a copy and update record expression to set any fields that differ from the default values.</span></span>

```fsharp
// Rather than use [<DefaultValue>], define a default record.
type MyRecord =
    { Field1 : int
      Field2 : int }

let defaultRecord1 = { Field1 = 0; Field2 = 0 }
let defaultRecord2 = { Field1 = 1; Field2 = 25 }

// Use the with keyword to populate only a few chosen fields
// and leave the rest with default values.
let rr3 = { defaultRecord1 with Field2 = 42 }
```

## <a name="creating-mutually-recursive-records"></a><span data-ttu-id="df6ee-139">La creazione di record ricorsiva si escludono a vicenda</span><span class="sxs-lookup"><span data-stu-id="df6ee-139">Creating Mutually Recursive Records</span></span>

<span data-ttu-id="df6ee-140">Un intervallo di tempo durante la creazione di un record, è possibile fare in modo che dipendono da un altro tipo che si vuole definire in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="df6ee-140">Sometime when creating a record, you may want to have it depend on another type that you would like to define afterwards.</span></span> <span data-ttu-id="df6ee-141">Si tratta di un errore di compilazione se non si definiscono i tipi di record siano reciprocamente ricorsiva.</span><span class="sxs-lookup"><span data-stu-id="df6ee-141">This is a compile error unless you define the record types to be mutually recursive.</span></span>

<span data-ttu-id="df6ee-142">Definizione dei record ricorsivo si escludono a vicenda viene eseguita con il `and` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="df6ee-142">Defining mutually recursive records is done with the `and` keyword.</span></span> <span data-ttu-id="df6ee-143">Ciò consente di collegare i tipi di 2 o più record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-143">This lets you link 2 or more record types together.</span></span>

<span data-ttu-id="df6ee-144">Ad esempio, il codice seguente definisce una `Person` e `Address` tipo ricorsive reciproche:</span><span class="sxs-lookup"><span data-stu-id="df6ee-144">For example, the following code defines a `Person` and `Address` type as mutually recursive:</span></span>

```fsharp
// Create a Person type and use the Address type that is not defined
type Person =
  { Name: string
    Age: int
    Address: Address }
// Define the Address type which is used in the Person record
and Address =
  { Line1: string
    Line2: string
    PostCode: string }
```

<span data-ttu-id="df6ee-145">Se si dovesse definire l'esempio precedente senza i `and` (parola chiave), quindi, non sarà possibile compilare.</span><span class="sxs-lookup"><span data-stu-id="df6ee-145">If you were to define the previous example without the `and` keyword, then it would not compile.</span></span> <span data-ttu-id="df6ee-146">Il `and` parola chiave è obbligatoria per le definizioni di ricorsivo si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="df6ee-146">The `and` keyword is required for mutually recursive definitions.</span></span>

## <a name="pattern-matching-with-records"></a><span data-ttu-id="df6ee-147">Criteri di ricerca con i record</span><span class="sxs-lookup"><span data-stu-id="df6ee-147">Pattern Matching with Records</span></span>

<span data-ttu-id="df6ee-148">I record sono utilizzabili con criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="df6ee-148">Records can be used with pattern matching.</span></span> <span data-ttu-id="df6ee-149">È possibile specificare in modo esplicito alcuni campi e specificare le variabili per gli altri campi che verranno assegnati quando viene rilevata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="df6ee-149">You can specify some fields explicitly and provide variables for other fields that will be assigned when a match occurs.</span></span> <span data-ttu-id="df6ee-150">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="df6ee-150">The following code example illustrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1910.fs)]

<span data-ttu-id="df6ee-151">L'output di questo codice è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="df6ee-151">The output of this code is as follows.</span></span>

```
Point is at the origin.
Point is on the x-axis. Value is 100.000000.
Point is at (10.000000, 0.000000, -1.000000).
```

## <a name="differences-between-records-and-classes"></a><span data-ttu-id="df6ee-152">Differenze tra classi e i record</span><span class="sxs-lookup"><span data-stu-id="df6ee-152">Differences Between Records and Classes</span></span>

<span data-ttu-id="df6ee-153">Campi del record differiscono dalle classi vengono esposti automaticamente come proprietà e sono utilizzati nella creazione e alla copia dei record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-153">Record fields differ from classes in that they are automatically exposed as properties, and they are used in the creation and copying of records.</span></span> <span data-ttu-id="df6ee-154">Costruzione di record è diversa anche dalla costruzione della classe.</span><span class="sxs-lookup"><span data-stu-id="df6ee-154">Record construction also differs from class construction.</span></span> <span data-ttu-id="df6ee-155">In un tipo di record, è possibile definire un costruttore.</span><span class="sxs-lookup"><span data-stu-id="df6ee-155">In a record type, you cannot define a constructor.</span></span> <span data-ttu-id="df6ee-156">Al contrario, si applica la sintassi di costruzione descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="df6ee-156">Instead, the construction syntax described in this topic applies.</span></span> <span data-ttu-id="df6ee-157">Classi di avere alcuna relazione diretta tra i parametri del costruttore, campi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="df6ee-157">Classes have no direct relationship between constructor parameters, fields, and properties.</span></span>

<span data-ttu-id="df6ee-158">Come i tipi di struttura e unione, record hanno una semantica di uguaglianza strutturale.</span><span class="sxs-lookup"><span data-stu-id="df6ee-158">Like union and structure types, records have structural equality semantics.</span></span> <span data-ttu-id="df6ee-159">Le classi hanno riferimenti semantica di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="df6ee-159">Classes have reference equality semantics.</span></span> <span data-ttu-id="df6ee-160">Nell'esempio di codice seguente viene illustrata questa possibilità.</span><span class="sxs-lookup"><span data-stu-id="df6ee-160">The following code example demonstrates this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1911.fs)]

<span data-ttu-id="df6ee-161">Come indicato di seguito è riportato l'output di questo codice:</span><span class="sxs-lookup"><span data-stu-id="df6ee-161">The output of this code is as follows:</span></span>

```
The records are equal.
```

<span data-ttu-id="df6ee-162">Se si scrittura lo stesso codice con le classi, i due oggetti di classe sarebbe diversi perché i due valori rappresenterebbe due oggetti nell'heap e potrebbero essere confrontati solo gli indirizzi (a meno che il tipo di classe esegue l'override di `System.Object.Equals` (metodo)).</span><span class="sxs-lookup"><span data-stu-id="df6ee-162">If you write the same code with classes, the two class objects would be unequal because the two values would represent two objects on the heap and only the addresses would be compared (unless the class type overrides the `System.Object.Equals` method).</span></span>

<span data-ttu-id="df6ee-163">Se è necessario fare riferimento l'uguaglianza dei record, aggiungere l'attributo `[<ReferenceEquality>]` sopra il record.</span><span class="sxs-lookup"><span data-stu-id="df6ee-163">If you need reference equality for records, add the attribute `[<ReferenceEquality>]` above the record.</span></span>

## <a name="see-also"></a><span data-ttu-id="df6ee-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df6ee-164">See also</span></span>

- [<span data-ttu-id="df6ee-165">Tipi F#</span><span class="sxs-lookup"><span data-stu-id="df6ee-165">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="df6ee-166">Classi</span><span class="sxs-lookup"><span data-stu-id="df6ee-166">Classes</span></span>](classes.md)
- [<span data-ttu-id="df6ee-167">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="df6ee-167">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="df6ee-168">Reference-Equality</span><span class="sxs-lookup"><span data-stu-id="df6ee-168">Reference-Equality</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.referenceequalityattribute-class-%5bfsharp%5d)
- [<span data-ttu-id="df6ee-169">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="df6ee-169">Pattern Matching</span></span>](pattern-matching.md)
