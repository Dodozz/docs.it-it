---
title: "Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM - Guida per programmatori C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
ms.openlocfilehash: 58b3b2646fec0284dc3e04c152b183ce05e05932
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245376"
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="10d48-102">Procedura: Usare proprietà indicizzate nella programmazione dell'interoperabilità COM (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="10d48-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="10d48-103">Le *proprietà indicizzate* migliorano l'uso delle proprietà COM dotate di parametri nella programmazione C#.</span><span class="sxs-lookup"><span data-stu-id="10d48-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="10d48-104">Tali proprietà operano congiuntamente ad altre funzionalità di Visual C#, ad esempio gli [argomenti denominati e facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), un nuovo tipo ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)) e le [informazioni sul tipo incorporate](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), per migliorare la programmazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="10d48-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="10d48-105">Nelle versioni precedenti di C# i metodi sono accessibili come proprietà solo se il metodo `get` non dispone di parametri e il metodo `set` ha un unico parametro valore.</span><span class="sxs-lookup"><span data-stu-id="10d48-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="10d48-106">Non tutte le proprietà COM soddisfano tuttavia tali restrizioni.</span><span class="sxs-lookup"><span data-stu-id="10d48-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="10d48-107">Ad esempio, la proprietà <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> di Excel possiede una funzione di accesso `get` che richiede un parametro per il nome dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="10d48-107">For example, the Excel <xref:Microsoft.Office.Interop.Excel.Range.Range%2A> property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="10d48-108">In passato, poiché non era possibile accedere direttamente alla proprietà `Range`, era necessario usare il metodo`get_Range`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="10d48-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 <span data-ttu-id="10d48-109">Le proprietà indicizzate consentono invece di scrivere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="10d48-109">Indexed properties enable you to write the following instead:</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="10d48-110">Nell'esempio precedente viene usata anche la funzionalità degli [argomenti facoltativi](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), che consente di omettere `Type.Missing`.</span><span class="sxs-lookup"><span data-stu-id="10d48-110">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="10d48-111">Analogamente, per impostare il valore della proprietà `Value` di un oggetto <xref:Microsoft.Office.Interop.Excel.Range> in Visual C# 2008 e versioni precedenti, sono necessari due argomenti.</span><span class="sxs-lookup"><span data-stu-id="10d48-111">Similarly to set the value of the `Value` property of a <xref:Microsoft.Office.Interop.Excel.Range> object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="10d48-112">Uno specifica un argomento per un parametro facoltativo che specifica il tipo del valore dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="10d48-112">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="10d48-113">L'altro indica il valore per la proprietà `Value`.</span><span class="sxs-lookup"><span data-stu-id="10d48-113">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="10d48-114">Queste tecniche vengono illustrate negli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="10d48-114">The following examples illustrate these techniques.</span></span> <span data-ttu-id="10d48-115">Entrambe impostano il valore della cella A1 su `Name`.</span><span class="sxs-lookup"><span data-stu-id="10d48-115">Both set the value of the A1 cell to `Name`.</span></span>
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 <span data-ttu-id="10d48-116">Le proprietà indicizzate consentono invece di scrivere il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="10d48-116">Indexed properties enable you to write the following code instead.</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 <span data-ttu-id="10d48-117">Non è possibile creare proprietà indicizzate personalizzate.</span><span class="sxs-lookup"><span data-stu-id="10d48-117">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="10d48-118">La funzionalità supporta solo l'utilizzo di proprietà indicizzate esistenti.</span><span class="sxs-lookup"><span data-stu-id="10d48-118">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10d48-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="10d48-119">Example</span></span>  
 <span data-ttu-id="10d48-120">L'esempio seguente illustra un esempio completo.</span><span class="sxs-lookup"><span data-stu-id="10d48-120">The following code shows a complete example.</span></span> <span data-ttu-id="10d48-121">Per altre informazioni su come configurare un progetto che accede all'API di Office, vedere [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="10d48-121">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="10d48-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10d48-122">See Also</span></span>

- [<span data-ttu-id="10d48-123">Argomenti denominati e facoltativi</span><span class="sxs-lookup"><span data-stu-id="10d48-123">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
- [<span data-ttu-id="10d48-124">dynamic</span><span class="sxs-lookup"><span data-stu-id="10d48-124">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
- [<span data-ttu-id="10d48-125">Uso del tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="10d48-125">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [<span data-ttu-id="10d48-126">Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="10d48-126">How to: Use Named and Optional Arguments in Office Programming</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
- [<span data-ttu-id="10d48-127">Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#</span><span class="sxs-lookup"><span data-stu-id="10d48-127">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
- [<span data-ttu-id="10d48-128">Procedura dettagliata: Programmazione Office</span><span class="sxs-lookup"><span data-stu-id="10d48-128">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
