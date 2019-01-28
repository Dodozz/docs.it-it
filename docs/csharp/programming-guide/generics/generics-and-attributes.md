---
title: Generics e attributi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 5b65ae794e99602fc84f674be5ec0502d4588a59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607702"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="88739-102">Generics e attributi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="88739-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="88739-103">Gli attributi possono essere applicati a tipi generici allo stesso modo che ai tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="88739-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="88739-104">Per altre informazioni sull'applicazione di attributi, vedere [Attributi](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="88739-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="88739-105">Gli attributi personalizzati sono consentiti solo per fare riferimento a tipi generici aperti, che sono tipi generici per cui non è specificato alcun argomento tipo, e tipi generici costruiti chiusi, che specificano argomenti per tutti i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="88739-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="88739-106">Gli esempi seguenti usano questo attributo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="88739-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 <span data-ttu-id="88739-107">Un attributo può fare riferimento a un tipo generico aperto:</span><span class="sxs-lookup"><span data-stu-id="88739-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 <span data-ttu-id="88739-108">Specificare più parametri di tipo usando il numero appropriato di virgole.</span><span class="sxs-lookup"><span data-stu-id="88739-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="88739-109">In questo esempio `GenericClass2` include due parametri di tipo:</span><span class="sxs-lookup"><span data-stu-id="88739-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 <span data-ttu-id="88739-110">Un attributo può fare riferimento a un tipo generico costruito chiuso:</span><span class="sxs-lookup"><span data-stu-id="88739-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 <span data-ttu-id="88739-111">Un attributo che fa riferimento a un parametro di tipo generico provoca un errore in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="88739-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 <span data-ttu-id="88739-112">Un tipo generico non può ereditare da <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="88739-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 <span data-ttu-id="88739-113">Per ottenere informazioni su un tipo generico o un parametro di tipo in fase di esecuzione, è possibile usare i metodi di <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="88739-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="88739-114">Per altre informazioni, vedere [Generics e reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="88739-114">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88739-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88739-115">See also</span></span>

- [<span data-ttu-id="88739-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="88739-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="88739-117">Generics</span><span class="sxs-lookup"><span data-stu-id="88739-117">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="88739-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="88739-118">Attributes</span></span>](../../../../docs/standard/attributes/index.md)
