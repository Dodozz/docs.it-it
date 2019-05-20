---
title: Parola chiave uint - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: 9a60460f67f9b6cf0b57d40ebf2789536e870d75
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633152"
---
# <a name="uint-c-reference"></a><span data-ttu-id="cfd0b-102">uint (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="cfd0b-102">uint (C# Reference)</span></span>

<span data-ttu-id="cfd0b-103">La parola chiave `uint` rappresenta un tipo integrale che archivia valori in base alla dimensione e all'intervallo mostrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="cfd0b-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="cfd0b-104">Type</span></span>|<span data-ttu-id="cfd0b-105">Intervallo</span><span class="sxs-lookup"><span data-stu-id="cfd0b-105">Range</span></span>|<span data-ttu-id="cfd0b-106">Dimensione</span><span class="sxs-lookup"><span data-stu-id="cfd0b-106">Size</span></span>|<span data-ttu-id="cfd0b-107">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="cfd0b-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`uint`|<span data-ttu-id="cfd0b-108">Da 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="cfd0b-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="cfd0b-109">Intero senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="cfd0b-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|

<span data-ttu-id="cfd0b-110">**Nota** Il tipo `uint` non è conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="cfd0b-111">Usare `int`, laddove possibile.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-111">Use `int` whenever possible.</span></span>

## <a name="literals"></a><span data-ttu-id="cfd0b-112">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="cfd0b-112">Literals</span></span>

<span data-ttu-id="cfd0b-113">È possibile dichiarare e inizializzare una variabile `uint` assegnandole un valore letterale decimale, un valore letterale esadecimale o (a partire da C# 7.0) un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="cfd0b-114">Se il valore letterale integer è esterno all'intervallo di `uint`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="cfd0b-115">Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `uint`.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> <span data-ttu-id="cfd0b-116">Viene usato il prefisso `0x` o `0X` per identificare un valore letterale esadecimale e il prefisso `0b` o `0B` per identificare un valore letterale binario.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-116">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="cfd0b-117">I valori letterali decimali non hanno prefissi.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-117">Decimal literals have no prefix.</span></span>

<span data-ttu-id="cfd0b-118">A partire da C# 7.0, sono state aggiunte alcune funzionalità che migliorano la leggibilità:</span><span class="sxs-lookup"><span data-stu-id="cfd0b-118">Starting with C# 7.0, a couple of features have been added to enhance readability:</span></span>

- <span data-ttu-id="cfd0b-119">C# 7.0 consente l'utilizzo del carattere di sottolineatura (`_`) come separatore di cifre.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-119">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="cfd0b-120">C# 7.2 consente l'utilizzo di `_` dopo il prefisso, come separatore di cifre per un valore letterale binario o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-120">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="cfd0b-121">In un valore letterale decimale non è consentito l'utilizzo di un carattere di sottolineatura iniziale.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-121">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="cfd0b-122">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-122">Some examples are shown below.</span></span>

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

<span data-ttu-id="cfd0b-123">Valori letterali integer possono anche includere un suffisso che denota il tipo.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-123">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="cfd0b-124">Il suffisso `U` o 'u' denota un valore `uint` o `ulong`, a seconda del valore numerico del valore letterale.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-124">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="cfd0b-125">L'esempio seguente usa il suffisso `u` per indicare un intero senza segno di entrambi i tipi.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-125">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="cfd0b-126">Si noti che il primo valore letterale è `uint` perché il relativo valore è minore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, mentre il secondo è `ulong` perché il relativo valore è maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-126">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

<span data-ttu-id="cfd0b-127">Se un valore letterale integer non ha alcun suffisso, il suo tipo corrisponderà al primo dei tipi seguenti in cui il suo valore può essere rappresentato:</span><span class="sxs-lookup"><span data-stu-id="cfd0b-127">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. [<span data-ttu-id="cfd0b-128">int</span><span class="sxs-lookup"><span data-stu-id="cfd0b-128">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="cfd0b-129">long</span><span class="sxs-lookup"><span data-stu-id="cfd0b-129">long</span></span>](long.md)
4. [<span data-ttu-id="cfd0b-130">ulong</span><span class="sxs-lookup"><span data-stu-id="cfd0b-130">ulong</span></span>](ulong.md)

## <a name="conversions"></a><span data-ttu-id="cfd0b-131">Conversioni</span><span class="sxs-lookup"><span data-stu-id="cfd0b-131">Conversions</span></span>

<span data-ttu-id="cfd0b-132">Si verifica una conversione implicita predefinita da `uint` a [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0b-132">There is a predefined implicit conversion from `uint` to [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md), or [decimal](decimal.md).</span></span> <span data-ttu-id="cfd0b-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cfd0b-133">For example:</span></span>

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

<span data-ttu-id="cfd0b-134">Viene eseguita una conversione implicita predefinita da [byte](byte.md), [ushort](ushort.md) o [char](char.md) a `uint`.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-134">There is a predefined implicit conversion from [byte](byte.md), [ushort](ushort.md), or [char](char.md) to `uint`.</span></span> <span data-ttu-id="cfd0b-135">In tutti gli altri casi è necessario ricorrere a un cast.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-135">Otherwise you must use a cast.</span></span> <span data-ttu-id="cfd0b-136">Nella seguente istruzione di assegnazione, ad esempio, verrà generato un errore di compilazione senza un cast:</span><span class="sxs-lookup"><span data-stu-id="cfd0b-136">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

<span data-ttu-id="cfd0b-137">Si noti inoltre che non avviene alcuna conversione implicita dai tipi a virgola mobile in `uint`.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-137">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="cfd0b-138">Ad esempio, l'istruzione seguente genera un errore di compilazione, a meno che non venga usato un cast esplicito:</span><span class="sxs-lookup"><span data-stu-id="cfd0b-138">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

<span data-ttu-id="cfd0b-139">Per informazioni sulle espressioni aritmetiche con tipi a virgola mobile e tipi integrali, vedere [float](float.md) e [double](double.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0b-139">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](float.md) and [double](double.md).</span></span>

<span data-ttu-id="cfd0b-140">Per altre informazioni sulle regole di conversione numeriche implicite, vedere [Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0b-140">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cfd0b-141">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cfd0b-141">C# language specification</span></span>

<span data-ttu-id="cfd0b-142">Per altre informazioni, vedere [Tipi integrali](~/_csharplang/spec/types.md#integral-types) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="cfd0b-142">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="cfd0b-143">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="cfd0b-143">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfd0b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfd0b-144">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="cfd0b-145">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="cfd0b-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cfd0b-146">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="cfd0b-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cfd0b-147">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="cfd0b-147">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cfd0b-148">Tabella dei tipi integrali</span><span class="sxs-lookup"><span data-stu-id="cfd0b-148">Integral Types Table</span></span>](integral-types-table.md)
- [<span data-ttu-id="cfd0b-149">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="cfd0b-149">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="cfd0b-150">Tabella delle conversioni numeriche implicite</span><span class="sxs-lookup"><span data-stu-id="cfd0b-150">Implicit Numeric Conversions Table</span></span>](implicit-numeric-conversions-table.md)
- [<span data-ttu-id="cfd0b-151">Tabella delle conversioni numeriche esplicite</span><span class="sxs-lookup"><span data-stu-id="cfd0b-151">Explicit Numeric Conversions Table</span></span>](explicit-numeric-conversions-table.md)
