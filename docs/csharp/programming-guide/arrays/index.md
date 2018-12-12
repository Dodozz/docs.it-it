---
title: Matrici - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: cf684d2ec7ae7282b1ab68817357773f0f96c9ae
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245652"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="289ca-102">Matrici (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="289ca-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="289ca-103">È possibile archiviare più variabili dello stesso tipo in una struttura di dati a matrice.</span><span class="sxs-lookup"><span data-stu-id="289ca-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="289ca-104">Una matrice viene dichiarata specificando il tipo degli elementi.</span><span class="sxs-lookup"><span data-stu-id="289ca-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="289ca-105">L'esempio seguente consente di creare matrici unidimensionali, multidimensionali e irregolari:</span><span class="sxs-lookup"><span data-stu-id="289ca-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## <a name="array-overview"></a><span data-ttu-id="289ca-106">Panoramica delle matrici</span><span class="sxs-lookup"><span data-stu-id="289ca-106">Array Overview</span></span>

 <span data-ttu-id="289ca-107">Le matrici hanno le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="289ca-107">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="289ca-108">Una matrice può essere [unidimensionale](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [multidimensionale](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) o [irregolare](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="289ca-108">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="289ca-109">Il numero di dimensioni e la lunghezza di ogni dimensione sono definiti durante la creazione dell'istanza della matrice.</span><span class="sxs-lookup"><span data-stu-id="289ca-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="289ca-110">Questi valori non possono essere modificati per la durata dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="289ca-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="289ca-111">I valori predefiniti degli elementi numerici della matrice sono impostati su zero, mentre gli elementi di riferimento sono impostati su null.</span><span class="sxs-lookup"><span data-stu-id="289ca-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="289ca-112">Una matrice irregolare è una matrice di matrici, quindi i relativi elementi sono tipi di riferimento inizializzati su `null`.</span><span class="sxs-lookup"><span data-stu-id="289ca-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="289ca-113">Le matrici sono a indice zero. Una matrice con `n` elementi viene indicizzata da `0` a `n-1`.</span><span class="sxs-lookup"><span data-stu-id="289ca-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="289ca-114">Gli elementi di una matrice possono essere di qualsiasi tipo, anche di tipo matrice.</span><span class="sxs-lookup"><span data-stu-id="289ca-114">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="289ca-115">I tipi matrice sono [tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) derivati dal tipo di base astratto <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="289ca-115">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="289ca-116">Poiché questo tipo implementa <xref:System.Collections.IEnumerable> e <xref:System.Collections.Generic.IEnumerable%601>, è possibile usare l'iterazione [foreach](../../../csharp/language-reference/keywords/foreach-in.md) su tutte le matrici in C#.</span><span class="sxs-lookup"><span data-stu-id="289ca-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="289ca-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="289ca-117">Related Sections</span></span>  
  
-   [<span data-ttu-id="289ca-118">Matrici come oggetti</span><span class="sxs-lookup"><span data-stu-id="289ca-118">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="289ca-119">Uso di foreach con matrici</span><span class="sxs-lookup"><span data-stu-id="289ca-119">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="289ca-120">Passaggio di matrici come argomenti</span><span class="sxs-lookup"><span data-stu-id="289ca-120">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="289ca-121">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="289ca-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="289ca-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="289ca-122">See Also</span></span>

- [<span data-ttu-id="289ca-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="289ca-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="289ca-124">Raccolte</span><span class="sxs-lookup"><span data-stu-id="289ca-124">Collections</span></span>](../../../csharp/programming-guide/concepts/collections.md)
