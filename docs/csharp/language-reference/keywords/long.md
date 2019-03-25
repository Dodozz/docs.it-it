---
title: long - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: a3c2dc725d5747c638acba9311ae78272cf63de0
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186013"
---
# <a name="long-c-reference"></a><span data-ttu-id="d5c1e-102">long (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d5c1e-102">long (C# Reference)</span></span>

<span data-ttu-id="d5c1e-103">`long` denota un tipo integrale che archivia valori in base alla dimensione e all'intervallo visualizzato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="d5c1e-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="d5c1e-104">Type</span></span>|<span data-ttu-id="d5c1e-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="d5c1e-105">Range</span></span>|<span data-ttu-id="d5c1e-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="d5c1e-106">Size</span></span>|<span data-ttu-id="d5c1e-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="d5c1e-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`long`|<span data-ttu-id="d5c1e-108">Da -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="d5c1e-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="d5c1e-109">Numero intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="d5c1e-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="d5c1e-110">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="d5c1e-110">Literals</span></span>

<span data-ttu-id="d5c1e-111">È possibile dichiarare e inizializzare una variabile `long` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>

<span data-ttu-id="d5c1e-112">Nell'esempio seguente, i valori interi uguali a 4.294.967.296 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `long`.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]

> [!NOTE]
> <span data-ttu-id="d5c1e-113">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="d5c1e-114">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="d5c1e-115">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>
- <span data-ttu-id="d5c1e-116">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="d5c1e-117">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="d5c1e-118">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="d5c1e-119">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

<span data-ttu-id="d5c1e-120">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="d5c1e-121">Il suffisso `L` denota un `long`.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="d5c1e-122">L'esempio seguente usa il suffisso `L` per indicare un valore long integer:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-122">The following example uses the `L` suffix to denote a long integer:</span></span>

```csharp
long value = 4294967296L;
```

> [!NOTE]
> <span data-ttu-id="d5c1e-123">È anche possibile usare la lettera minuscola "l" come suffisso.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="d5c1e-124">In questo caso, viene tuttavia generato un avviso del compilatore perché la lettera "l" viene facilmente confusa con la cifra "1".</span><span class="sxs-lookup"><span data-stu-id="d5c1e-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="d5c1e-125">Per maggiore chiarezza, usare la lettera "L".</span><span class="sxs-lookup"><span data-stu-id="d5c1e-125">Use "L" for clarity.</span></span>

<span data-ttu-id="d5c1e-126">Quando si usa il suffisso `L`, il tipo del valore letterale integer viene impostato su `long` o [ulong](../../../csharp/language-reference/keywords/ulong.md) a seconda delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="d5c1e-127">In questo caso è di tipo `long` perché è minore dell'intervallo di [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>

<span data-ttu-id="d5c1e-128">Un uso comune del suffisso è la chiamata di metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="d5c1e-129">I metodi di overload seguenti, ad esempio, hanno parametri di tipo `long` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="d5c1e-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(long l) {}
```

<span data-ttu-id="d5c1e-130">Il suffisso `L` garantisce che venga chiamato l'overload corretto:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-130">The `L` suffix guarantees that the correct overload is called:</span></span>

```csharp
SampleMethod(5);    // Calls the method with the int parameter
SampleMethod(5L);   // Calls the method with the long parameter
```
<span data-ttu-id="d5c1e-131">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="d5c1e-132">int</span><span class="sxs-lookup"><span data-stu-id="d5c1e-132">int</span></span>](int.md)
2. [<span data-ttu-id="d5c1e-133">uint</span><span class="sxs-lookup"><span data-stu-id="d5c1e-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="d5c1e-134">ulong</span><span class="sxs-lookup"><span data-stu-id="d5c1e-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)

<span data-ttu-id="d5c1e-135">Il valore letterale 4294967296 nell'esempio precedente è di tipo `long` perché è esterno all'intervallo di [uint](../../../csharp/language-reference/keywords/uint.md). Per informazioni sullo spazio necessario per l'archiviazione dei tipi integrali, vedere [Tabella dei tipi integrali](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>

<span data-ttu-id="d5c1e-136">Se si usa il tipo `long` con altri tipi integrali nella stessa espressione, l'espressione darà un risultato di tipo `long` (o [bool](../../../csharp/language-reference/keywords/bool.md) nel caso di espressioni relazionali o booleane).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="d5c1e-137">Ad esempio, l'espressione riportata di seguito restituisce `long`:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-137">For example, the following expression evaluates as `long`:</span></span>

```csharp
898L + 88
```

<span data-ttu-id="d5c1e-138">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](../../../csharp/language-reference/keywords/float.md) e [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>

## <a name="conversions"></a><span data-ttu-id="d5c1e-139">Conversioni</span><span class="sxs-lookup"><span data-stu-id="d5c1e-139">Conversions</span></span>

<span data-ttu-id="d5c1e-140">Si verifica una conversione implicita predefinita da `long` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="d5c1e-141">In tutti gli altri casi è necessario usare un cast.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="d5c1e-142">L'istruzione seguente, ad esempio, genera un errore di compilazione se non viene usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>

```csharp
int x = 8L;        // Error: no implicit conversion from long to int
int y = (int)8L;   // OK: explicit conversion to int
```

<span data-ttu-id="d5c1e-143">Si verifica una conversione implicita predefinita da [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) in `long`.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>

<span data-ttu-id="d5c1e-144">Si noti anche che non esiste alcuna conversione implicita dai tipi a virgola mobile a `long`.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="d5c1e-145">L'istruzione seguente, ad esempio, genera un errore di compilazione a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="d5c1e-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
long x = 3.0;         // Error: no implicit conversion from double
long y = (long)3.0;   // OK: explicit conversion
```

## <a name="c-language-specification"></a><span data-ttu-id="d5c1e-146">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d5c1e-146">C# Language Specification</span></span>

<span data-ttu-id="d5c1e-147">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-147">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="d5c1e-148">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-148">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5c1e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5c1e-149">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="d5c1e-150">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d5c1e-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d5c1e-151">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d5c1e-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d5c1e-152">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="d5c1e-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="d5c1e-153">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="d5c1e-153">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="d5c1e-154">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="d5c1e-154">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="d5c1e-155">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="d5c1e-155">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="d5c1e-156">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="d5c1e-156">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
