---
title: Funzioni di conversione del tipo (Visual Basic)
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: cbc9891170cde4b993a5dc890ed71c07a6f59f9e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129558"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="25118-102">Funzioni di conversione del tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25118-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="25118-103">Queste funzioni vengono compilate inline, vale a dire che il codice di conversione fa parte del codice che valuta l'espressione.</span><span class="sxs-lookup"><span data-stu-id="25118-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="25118-104">In alcuni casi non vi è alcuna chiamata a una procedura per eseguire la conversione, che migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="25118-105">Ogni funzione converte un'espressione per un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="25118-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25118-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25118-106">Syntax</span></span>  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a><span data-ttu-id="25118-107">Parte</span><span class="sxs-lookup"><span data-stu-id="25118-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="25118-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="25118-108">Required.</span></span> <span data-ttu-id="25118-109">Qualsiasi espressione del tipo di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="25118-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="25118-110">Restituire il tipo di dati di valore</span><span class="sxs-lookup"><span data-stu-id="25118-110">Return Value Data Type</span></span>  
 <span data-ttu-id="25118-111">Il nome della funzione determina il tipo di dati del valore restituito, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="25118-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="25118-112">Nome della funzione</span><span class="sxs-lookup"><span data-stu-id="25118-112">Function name</span></span>|<span data-ttu-id="25118-113">Tipo di dati restituito</span><span class="sxs-lookup"><span data-stu-id="25118-113">Return data type</span></span>|<span data-ttu-id="25118-114">Intervallo per `expression` argomento</span><span class="sxs-lookup"><span data-stu-id="25118-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="25118-115">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="25118-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="25118-116">Qualunque `Char` o `String` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="25118-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="25118-117">Tipo di dati Byte</span><span class="sxs-lookup"><span data-stu-id="25118-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="25118-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-119">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di byte con il `CByte` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-120">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="25118-121">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="25118-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="25118-122">Qualunque `Char` o `String` espressione; solo primo carattere di un `String` viene convertito; valore può essere 0 e 65535 (senza segno).</span><span class="sxs-lookup"><span data-stu-id="25118-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="25118-123">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="25118-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="25118-124">Qualsiasi rappresentazione valida di una data e ora.</span><span class="sxs-lookup"><span data-stu-id="25118-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="25118-125">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="25118-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="25118-126">-1.79769313486231570 e + 308 e - fino a 4.94065645841246544-324 per valori negativi. Fino a 4.94065645841246544-324 e 1.79769313486231570 e + 308 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="25118-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="25118-127">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="25118-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="25118-128">+ /-79.228.162.514.264.337.593.543.950.335 per i numeri da zero a scalabilità, ovvero numeri senza cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="25118-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="25118-129">Per i numeri con 28 posizioni decimali, l'intervallo è + /-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="25118-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="25118-130">Il minor numero possibile di diverso da zero è 0,0000000000000000000000000001 (+ /-1E-28).</span><span class="sxs-lookup"><span data-stu-id="25118-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="25118-131">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="25118-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="25118-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (da -2.147.483.648) attraverso <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="25118-133">A partire da 15.8 Visual Basic, Visual Basic ottimizza le prestazioni della virgola mobile per la conversione di integer con il `CInt` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-134">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="25118-135">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="25118-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="25118-136"><xref:System.Int64.MaxValue?displayProperty=nameWithType> (da -9.223.372.036.854.775.808) attraverso <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-136"><xref:System.Int64.MaxValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-137">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di integer a 64 bit con la `CLng` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-138">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="25118-139">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="25118-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="25118-140">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="25118-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="25118-141">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="25118-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="25118-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (da -128) attraverso <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-143">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di byte con segno con il `CSByte` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-144">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="25118-145">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="25118-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="25118-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) attraverso <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-147">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di integer a 16 bit con la `CShort` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-148">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="25118-149">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="25118-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="25118-150">-3,402823E+38 a - 1,401298E-45 per valori negativi. 1,401298E-45 a 3,402823E+38 per valori positivi.</span><span class="sxs-lookup"><span data-stu-id="25118-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="25118-151">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="25118-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="25118-152">Restituisce relativi `CStr` dipendono il `expression` argomento.</span><span class="sxs-lookup"><span data-stu-id="25118-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="25118-153">Visualizzare [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="25118-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="25118-154">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="25118-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="25118-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-156">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero senza segno con il `CUInt` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-157">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="25118-158">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="25118-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="25118-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-160">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero lungo senza segno con il `CULng` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-161">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="25118-162">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="25118-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="25118-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="25118-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="25118-164">A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero senza segno a 16 bit con la `CUShort` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="25118-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="25118-165">Vedere le [CInt esempio](#cint-example) sezione per un esempio.</span><span class="sxs-lookup"><span data-stu-id="25118-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="25118-166"><sup>1</sup> parti frazionarie possono essere soggetta a un tipo speciale di arrotondamento chiamato *arrotondamento*.</span><span class="sxs-lookup"><span data-stu-id="25118-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="25118-167">Per ulteriori informazioni, vedere "la sezione Osservazioni".</span><span class="sxs-lookup"><span data-stu-id="25118-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25118-168">Note</span><span class="sxs-lookup"><span data-stu-id="25118-168">Remarks</span></span>  
 <span data-ttu-id="25118-169">Di norma, è consigliabile usare le funzioni di conversione di tipo Visual Basic anziché i metodi .NET Framework, ad esempio `ToString()`, ad esempio nel <xref:System.Convert> classe o in una classe o struttura di tipo individuale.</span><span class="sxs-lookup"><span data-stu-id="25118-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="25118-170">Le funzioni di Visual Basic sono progettate per l'interazione ottimale con codice Visual Basic e rendono il codice sorgente più breve e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="25118-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="25118-171">Inoltre, i metodi di conversione di .NET Framework non restituiscono sempre gli stessi risultati di funzioni di Visual Basic, ad esempio quando si convertono `Boolean` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="25118-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="25118-172">Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="25118-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  


<span data-ttu-id="25118-173">A partire da Visual Basic 15.8, le prestazioni della conversione a virgola mobile-virgola-a numero intero sono ottimizzata quando si passa il <xref:System.Single> oppure <xref:System.Double> valore restituito dai metodi seguenti per una delle funzioni di conversione di integer (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="25118-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="25118-174">Questa ottimizzazione consente al codice che esegue un numero elevato di conversioni di integer per eseguire un massimo di due volte più veloci.</span><span class="sxs-lookup"><span data-stu-id="25118-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="25118-175">L'esempio seguente illustra queste conversioni ottimizzate di Mobile-virgola-a-integer:</span><span class="sxs-lookup"><span data-stu-id="25118-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="25118-176">Comportamento</span><span class="sxs-lookup"><span data-stu-id="25118-176">Behavior</span></span>  
  
-   <span data-ttu-id="25118-177">**Coercizione.**</span><span class="sxs-lookup"><span data-stu-id="25118-177">**Coercion.**</span></span> <span data-ttu-id="25118-178">In generale, è possibile utilizzare le funzioni di conversione di tipi di dati per assegnare il risultato di un'operazione a un particolare tipo di dati anziché il tipo di dati predefinito.</span><span class="sxs-lookup"><span data-stu-id="25118-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="25118-179">Ad esempio, usare `CDec` forzare operazioni aritmetiche decimali nei casi in cui con precisione singola e precisione doppia o calcoli di interi normalmente avverrebbero.</span><span class="sxs-lookup"><span data-stu-id="25118-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="25118-180">**Conversioni non riuscite.**</span><span class="sxs-lookup"><span data-stu-id="25118-180">**Failed Conversions.**</span></span> <span data-ttu-id="25118-181">Se il `expression` passati alla funzione è compreso nell'intervallo del tipo di dati a cui si desidera convertire, un <xref:System.OverflowException> si verifica.</span><span class="sxs-lookup"><span data-stu-id="25118-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="25118-182">**Parti frazionarie.**</span><span class="sxs-lookup"><span data-stu-id="25118-182">**Fractional Parts.**</span></span> <span data-ttu-id="25118-183">Quando si converte un valore non integrale in un valore integrale digita, le funzioni di conversione di valori integer (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, e `CUShort`) rimuovere il frazionari parte e arrotondare il valore all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="25118-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="25118-184">Se la parte frazionaria è identica 0,5, le funzioni di conversione di valori integer arrotondano per l'intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="25118-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="25118-185">Ad esempio 0,5 verrà arrotondato a 0 e 1,5 e 2,5 che entrambi arrotondato a 2.</span><span class="sxs-lookup"><span data-stu-id="25118-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="25118-186">Questa operazione è denominata *arrotondamento*, e il suo scopo consiste nel compensare la distorsione che può accumularsi quando aggiungono molti tali numeri.</span><span class="sxs-lookup"><span data-stu-id="25118-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="25118-187">`CInt` e `CLng` differiscono dalle <xref:Microsoft.VisualBasic.Conversion.Int%2A> e <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funzioni, che troncano, anziché round, la parte frazionaria di un numero.</span><span class="sxs-lookup"><span data-stu-id="25118-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="25118-188">È inoltre `Fix` e `Int` restituiscono sempre un valore del tipo di dati stesso di quello passato.</span><span class="sxs-lookup"><span data-stu-id="25118-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="25118-189">**Conversioni di data/ora.**</span><span class="sxs-lookup"><span data-stu-id="25118-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="25118-190">Usare il <xref:Microsoft.VisualBasic.Information.IsDate%2A> funzione per determinare se un valore può essere convertito in una data e ora.</span><span class="sxs-lookup"><span data-stu-id="25118-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="25118-191">`CDate` riconosce i valori letterali di data e ora, ma i valori non numerici.</span><span class="sxs-lookup"><span data-stu-id="25118-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="25118-192">La conversione di Visual Basic 6.0 `Date` valore per un `Date` valore in Visual Basic 2005 o versioni successive, è possibile usare il <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="25118-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="25118-193">**Neutro valori data/ora.**</span><span class="sxs-lookup"><span data-stu-id="25118-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="25118-194">Il [tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene sempre le informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="25118-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="25118-195">Ai fini di conversione del tipo, Visual Basic considera come 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) su un valore neutro per il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="25118-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="25118-196">Se si converte un `Date` valore da una stringa, `CStr` non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="25118-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="25118-197">Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30: 12:00:00 AM"; le informazioni sulla data viene eliminate.</span><span class="sxs-lookup"><span data-stu-id="25118-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="25118-198">Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con le funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (funzione).</span><span class="sxs-lookup"><span data-stu-id="25118-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="25118-199">**Sensibilità delle impostazioni cultura.**</span><span class="sxs-lookup"><span data-stu-id="25118-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="25118-200">Le funzioni di conversione di tipo che interessa le stringhe di eseguono conversioni in base alle impostazioni cultura correnti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="25118-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="25118-201">Ad esempio, `CDate` riconosce i formati di data in base alle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="25118-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="25118-202">È necessario specificare il giorno, mese e anno nell'ordine corretto per le impostazioni locali, o alla data potrà essere interpretata erroneamente.</span><span class="sxs-lookup"><span data-stu-id="25118-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="25118-203">Se contiene una stringa di giorno della settimana, ad esempio "Wednesday", un formato di data estesa non è riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="25118-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="25118-204">Se è necessario convertire a o da una rappresentazione di stringa di un valore in un formato diverso da quello specificato dalle impostazioni locali, è possibile usare le funzioni di conversione di tipo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="25118-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="25118-205">A questo scopo, usare il `ToString(IFormatProvider)` e `Parse(String, IFormatProvider)` metodi del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="25118-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="25118-206">Ad esempio, usare <xref:System.Double.Parse%2A?displayProperty=nameWithType> quando si converte una stringa in un `Double`e usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` in una stringa.</span><span class="sxs-lookup"><span data-stu-id="25118-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="25118-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="25118-207">CType Function</span></span>  
 <span data-ttu-id="25118-208">Il [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) accetta un secondo argomento `typename`e assegna `expression` a `typename`, dove `typename` può essere qualsiasi tipo di dati, struttura, classe o interfaccia a cui è presente una conversione valida.</span><span class="sxs-lookup"><span data-stu-id="25118-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="25118-209">Per un confronto delle `CType` con l'altra tipo parole chiave di conversione, vedere [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="25118-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="25118-210">Esempio CBool</span><span class="sxs-lookup"><span data-stu-id="25118-210">CBool Example</span></span>  
 <span data-ttu-id="25118-211">L'esempio seguente usa il `CBool` funzione per convertire le espressioni `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="25118-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="25118-212">Se un'espressione restituisce un valore diverso da zero, `CBool` restituisce `True`; in caso contrario, restituisce `False`.</span><span class="sxs-lookup"><span data-stu-id="25118-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="25118-213">Esempio CByte</span><span class="sxs-lookup"><span data-stu-id="25118-213">CByte Example</span></span>  
 <span data-ttu-id="25118-214">L'esempio seguente usa il `CByte` funzione per convertire un'espressione in un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="25118-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="25118-215">Esempio di CChar</span><span class="sxs-lookup"><span data-stu-id="25118-215">CChar Example</span></span>  
 <span data-ttu-id="25118-216">L'esempio seguente usa il `CChar` funzione per convertire il primo carattere di una `String` espressione da un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="25118-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="25118-217">L'argomento di input per `CChar` deve essere del tipo di dati `Char` o `String`.</span><span class="sxs-lookup"><span data-stu-id="25118-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="25118-218">Non è possibile usare `CChar` per convertire un numero in un carattere, in quanto `CChar` non può accettare un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="25118-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="25118-219">Nell'esempio seguente ottiene un numero che rappresenta un punto di codice (codice di carattere) e lo converte nel carattere corrispondente.</span><span class="sxs-lookup"><span data-stu-id="25118-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="25118-220">Usa il <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> funzione per ottenere la stringa di cifre `CInt` per convertire la stringa al tipo `Integer`, e `ChrW` effettuare la conversione al tipo `Char`.</span><span class="sxs-lookup"><span data-stu-id="25118-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="25118-221">Esempio CDate</span><span class="sxs-lookup"><span data-stu-id="25118-221">CDate Example</span></span>  
 <span data-ttu-id="25118-222">L'esempio seguente usa il `CDate` funzione per convertire le stringhe a `Date` valori.</span><span class="sxs-lookup"><span data-stu-id="25118-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="25118-223">In generale, non è consigliabile impostare come hardcoded date e ore sotto forma di stringhe (come illustrato in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="25118-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="25118-224">Usare valori letterali di data e ora, ad esempio #Feb 12, 1969 # e # 4:45:23 PM # invece.</span><span class="sxs-lookup"><span data-stu-id="25118-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="25118-225">Esempio CDbl</span><span class="sxs-lookup"><span data-stu-id="25118-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="25118-226">Esempio CDec</span><span class="sxs-lookup"><span data-stu-id="25118-226">CDec Example</span></span>  
 <span data-ttu-id="25118-227">L'esempio seguente usa il `CDec` funzione per convertire un valore numerico a `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="25118-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="25118-228">Esempio CInt</span><span class="sxs-lookup"><span data-stu-id="25118-228">CInt Example</span></span>  
 <span data-ttu-id="25118-229">L'esempio seguente usa il `CInt` funzione per convertire un valore a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="25118-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  

## <a name="clng-example"></a><span data-ttu-id="25118-230">Esempio CLng</span><span class="sxs-lookup"><span data-stu-id="25118-230">CLng Example</span></span>
 <span data-ttu-id="25118-231">L'esempio seguente usa il `CLng` funzione per convertire i valori per `Long`.</span><span class="sxs-lookup"><span data-stu-id="25118-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="25118-232">CObj esempio</span><span class="sxs-lookup"><span data-stu-id="25118-232">CObj Example</span></span>  
 <span data-ttu-id="25118-233">L'esempio seguente usa il `CObj` funzione per convertire un valore numerico a `Object`.</span><span class="sxs-lookup"><span data-stu-id="25118-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="25118-234">Il `Object` variabile contiene solo un puntatore a quattro byte, che fa riferimento al `Double` valore assegnato a esso.</span><span class="sxs-lookup"><span data-stu-id="25118-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="25118-235">Esempio di CSByte</span><span class="sxs-lookup"><span data-stu-id="25118-235">CSByte Example</span></span>  
 <span data-ttu-id="25118-236">L'esempio seguente usa il `CSByte` funzione per convertire un valore numerico a `SByte`.</span><span class="sxs-lookup"><span data-stu-id="25118-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="25118-237">Esempio di CShort</span><span class="sxs-lookup"><span data-stu-id="25118-237">CShort Example</span></span>  
 <span data-ttu-id="25118-238">L'esempio seguente usa il `CShort` funzione per convertire un valore numerico a `Short`.</span><span class="sxs-lookup"><span data-stu-id="25118-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="25118-239">Esempio di CSng</span><span class="sxs-lookup"><span data-stu-id="25118-239">CSng Example</span></span>  
 <span data-ttu-id="25118-240">L'esempio seguente usa il `CSng` funzione per convertire i valori per `Single`.</span><span class="sxs-lookup"><span data-stu-id="25118-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="25118-241">Esempio di funzione CStr</span><span class="sxs-lookup"><span data-stu-id="25118-241">CStr Example</span></span>  
 <span data-ttu-id="25118-242">L'esempio seguente usa il `CStr` funzione per convertire un valore numerico a `String`.</span><span class="sxs-lookup"><span data-stu-id="25118-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="25118-243">L'esempio seguente usa il `CStr` funzione per convertire `Date` valori `String` valori.</span><span class="sxs-lookup"><span data-stu-id="25118-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="25118-244">`CStr` Visualizza sempre un `Date` valore nel formato breve standard per le impostazioni locali correnti, ad esempio, "6/15/2003 4 35 47 PM".</span><span class="sxs-lookup"><span data-stu-id="25118-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="25118-245">Tuttavia `CStr` Elimina il *valori neutri* 1/1/0001 per la data e 00:00:00 per l'ora.</span><span class="sxs-lookup"><span data-stu-id="25118-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="25118-246">Per informazioni dettagliate sui valori restituiti dal `CStr`, vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="25118-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="25118-247">Esempio di CUInt</span><span class="sxs-lookup"><span data-stu-id="25118-247">CUInt Example</span></span>  
 <span data-ttu-id="25118-248">L'esempio seguente usa il `CUInt` funzione per convertire un valore numerico a `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="25118-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="25118-249">Esempio di CULng</span><span class="sxs-lookup"><span data-stu-id="25118-249">CULng Example</span></span>  
 <span data-ttu-id="25118-250">L'esempio seguente usa il `CULng` funzione per convertire un valore numerico a `ULong`.</span><span class="sxs-lookup"><span data-stu-id="25118-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="25118-251">Esempio di CUShort</span><span class="sxs-lookup"><span data-stu-id="25118-251">CUShort Example</span></span>  
 <span data-ttu-id="25118-252">L'esempio seguente usa il `CUShort` funzione per convertire un valore numerico a `UShort`.</span><span class="sxs-lookup"><span data-stu-id="25118-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="25118-253">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25118-253">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="25118-254">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="25118-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="25118-255">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25118-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
