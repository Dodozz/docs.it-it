---
title: 'Procedura: Aggiungere zeri iniziali a un numero'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b48462e79c3e8ef3fdd6e0a91f5abecffc022b5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673034"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="c34a2-102">Procedura: Aggiungere zeri iniziali a un numero</span><span class="sxs-lookup"><span data-stu-id="c34a2-102">How to: Pad a Number with Leading Zeros</span></span>
<span data-ttu-id="c34a2-103">È possibile aggiungere degli zeri iniziali a un numero intero usando la [stringa di formato numerico standard](../../../docs/standard/base-types/standard-numeric-format-strings.md) "D" con un identificatore di precisione.</span><span class="sxs-lookup"><span data-stu-id="c34a2-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="c34a2-104">È possibile aggiungere zeri iniziali sia ai numeri interi che ai numeri a virgola mobile usando una [stringa di formato numerico personalizzata](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span><span class="sxs-lookup"><span data-stu-id="c34a2-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="c34a2-105">In questo argomento viene illustrato come usare entrambi i metodi per aggiungere un numero con gli zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="c34a2-105">This topic shows how to use both methods to pad a number with leading zeros.</span></span>  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="c34a2-106">Per aggiungere un intero con gli zeri iniziali a una lunghezza specifica</span><span class="sxs-lookup"><span data-stu-id="c34a2-106">To pad an integer with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="c34a2-107">Determinare il numero minimo di cifre da visualizzare nel valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="c34a2-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="c34a2-108">Includere eventuali cifre iniziali nel numero.</span><span class="sxs-lookup"><span data-stu-id="c34a2-108">Include any leading digits in this number.</span></span>  
  
2.  <span data-ttu-id="c34a2-109">Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="c34a2-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>  
  
    -   <span data-ttu-id="c34a2-110">Per visualizzare il valore di tipo Integer come valore decimale, chiamare il metodo `ToString(String)` e passare la stringa "D*n*" come valore del parametro `format`, dove *n* rappresenta la lunghezza minima della stringa.</span><span class="sxs-lookup"><span data-stu-id="c34a2-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
    -   <span data-ttu-id="c34a2-111">Per visualizzare il valore di tipo Integer come valore esadecimale, chiamare il metodo `ToString(String)` e passare la stringa "X*n*" come valore del parametro `format`, dove *n* rappresenta la lunghezza minima della stringa.</span><span class="sxs-lookup"><span data-stu-id="c34a2-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>  
  
     <span data-ttu-id="c34a2-112">È anche possibile usare la stringa di formato in un metodo, come <xref:System.String.Format%2A> o <xref:System.Console.WriteLine%2A>, che usa la [formattazione composita](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="c34a2-112">You can also use the format string in a method, such as <xref:System.String.Format%2A> or <xref:System.Console.WriteLine%2A>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="c34a2-113">Il seguente esempio formatta diversi valori di tipo Integer con gli zeri iniziali in modo che la lunghezza totale del numero formattato sia almeno di otto caratteri.</span><span class="sxs-lookup"><span data-stu-id="c34a2-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="c34a2-114">Per aggiungere un intero con un determinato numero di zeri iniziali</span><span class="sxs-lookup"><span data-stu-id="c34a2-114">To pad an integer with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="c34a2-115">Determinare il numero di zeri iniziali da visualizzare nel valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="c34a2-115">Determine how many leading zeros you want the integer value to display.</span></span>  
  
2.  <span data-ttu-id="c34a2-116">Determinare se si vuole visualizzare il valore di tipo Integer come valore decimale o esadecimale.</span><span class="sxs-lookup"><span data-stu-id="c34a2-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span> <span data-ttu-id="c34a2-117">Se si formatta come valore decimale, è necessario usare l'identificatore di formato standard "D", mentre come valore esadecimale è necessario usare l'identificatore di formato "X".</span><span class="sxs-lookup"><span data-stu-id="c34a2-117">Formatting it as a decimal value requires that you use the "D" standard format specifier; formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>  
  
3.  <span data-ttu-id="c34a2-118">Determine la lunghezza della stringa numerica non aggiunta chiamando il metodo `ToString("D").Length` o `ToString("X").Length` del valore di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="c34a2-118">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>  
  
4.  <span data-ttu-id="c34a2-119">Aggiungere il numero di zeri iniziali da includere nella stringa formattata nella lunghezza della stringa numerica non aggiunta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-119">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="c34a2-120">In questo modo si definisce la lunghezza totale della stringa aggiunta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-120">This defines the total length of the padded string.</span></span>  
  
5.  <span data-ttu-id="c34a2-121">Chiamare il metodo `ToString(String)` del valore integer e passare la stringa "D*n*" per le stringhe decimali e la stringa "X*n*" per quelle esadecimali, dove *n* rappresenta la lunghezza totale della stringa aggiunta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-121">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="c34a2-122">È anche possibile usare la stringa di formato "D*n*" o "X*n*" in un metodo che supporta la formattazione composta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-122">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="c34a2-123">Il seguente esempio aggiunge un valore di tipo Integer con cinque zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="c34a2-123">The following example pads an integer value with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="c34a2-124">Per aggiungere un valore numerico con gli zeri iniziali a una lunghezza specifica</span><span class="sxs-lookup"><span data-stu-id="c34a2-124">To pad a numeric value with leading zeros to a specific length</span></span>  
  
1.  <span data-ttu-id="c34a2-125">Determinare il numero di cifre alla sinistra del decimale che deve avere la rappresentazione della stringa del numero.</span><span class="sxs-lookup"><span data-stu-id="c34a2-125">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="c34a2-126">Includere gli eventuali zeri iniziali nel numero totale di cifre.</span><span class="sxs-lookup"><span data-stu-id="c34a2-126">Include any leading zeros in this total number of digits.</span></span>  
  
2.  <span data-ttu-id="c34a2-127">Definire una stringa di formato numerico personalizzata in cui è usato un segnaposto zero ("0") per rappresentare il numero minimo di zeri.</span><span class="sxs-lookup"><span data-stu-id="c34a2-127">Define a custom numeric format string that uses the zero placeholder ("0") to represent the minimum number of zeros.</span></span>  
  
3.  <span data-ttu-id="c34a2-128">Chiamare il metodo `ToString(String)` del numero e passarlo alla stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c34a2-128">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="c34a2-129">È anche possibile usare la stringa di formato personalizzata con un metodo che supporta la formattazione composta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-129">You can also use the custom format string with a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="c34a2-130">Il seguente esempio formatta diversi valori numerici con gli zeri iniziali in modo che la lunghezza totale del numero formattato sia almeno di otto caratteri alla sinistra del decimale.</span><span class="sxs-lookup"><span data-stu-id="c34a2-130">The following example formats several numeric values with leading zeros so that the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="c34a2-131">Per aggiungere un valore numerico con un determinato numero di zeri iniziali</span><span class="sxs-lookup"><span data-stu-id="c34a2-131">To pad a numeric value with a specific number of leading zeros</span></span>  
  
1.  <span data-ttu-id="c34a2-132">Determinare il numero di zeri iniziali che deve avere il valore numerico.</span><span class="sxs-lookup"><span data-stu-id="c34a2-132">Determine how many leading zeros you want the numeric value to have.</span></span>  
  
2.  <span data-ttu-id="c34a2-133">Determine il numero di cifre alla sinistra del decimale nella stringa numerica non aggiunta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-133">Determine the number of digits to the left of the decimal in the unpadded numeric string.</span></span> <span data-ttu-id="c34a2-134">Per eseguire questa operazione:</span><span class="sxs-lookup"><span data-stu-id="c34a2-134">To do this:</span></span>  
  
    1.  <span data-ttu-id="c34a2-135">Determinare se la rappresentazione della stringa di un numero include un simbolo di separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="c34a2-135">Determine whether the string representation of a number includes a decimal point symbol.</span></span>  
  
    2.  <span data-ttu-id="c34a2-136">In questo caso, determinare il numero di caratteri alla sinistra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="c34a2-136">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>  
  
         <span data-ttu-id="c34a2-137">-oppure-</span><span class="sxs-lookup"><span data-stu-id="c34a2-137">-or-</span></span>  
  
         <span data-ttu-id="c34a2-138">In caso contrario, determinare la lunghezza della stringa.</span><span class="sxs-lookup"><span data-stu-id="c34a2-138">If it does not include a decimal point symbol, determine the string's length.</span></span>  
  
3.  <span data-ttu-id="c34a2-139">Creare una stringa di formato personalizzata in cui è usato il segnaposto zero ("0") per ciascuno degli zeri iniziali da visualizzare nella stringa e il segnaposto zero o il segnaposto cifra ("#") per rappresentare ciascuna cifra nella stringa predefinita.</span><span class="sxs-lookup"><span data-stu-id="c34a2-139">Create a custom format string that uses the zero placeholder ("0") for each of the leading zeros to appear in the string, and that uses either the zero placeholder or the digit placeholder ("#") to represent each digit in the default string.</span></span>  
  
4.  <span data-ttu-id="c34a2-140">Fornire la stringa di formato personalizzata come parametro nel metodo `ToString(String)` del numero o in un metodo che supporta la formattazione composta.</span><span class="sxs-lookup"><span data-stu-id="c34a2-140">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>  
  
 <span data-ttu-id="c34a2-141">Il seguente esempio aggiunge due valori <xref:System.Double> con cinque zeri iniziali.</span><span class="sxs-lookup"><span data-stu-id="c34a2-141">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="c34a2-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c34a2-142">See also</span></span>

- [<span data-ttu-id="c34a2-143">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="c34a2-143">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [<span data-ttu-id="c34a2-144">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="c34a2-144">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="c34a2-145">Formattazione composita</span><span class="sxs-lookup"><span data-stu-id="c34a2-145">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
