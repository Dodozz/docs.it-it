---
title: Proprietà dell'interfaccia - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: c51064f9bb5e834648e0086fd8d28f9c0bd84b61
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241587"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="2f7d4-102">Proprietà dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2f7d4-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="2f7d4-103">Le proprietà possono essere dichiarate su una [interfaccia](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="2f7d4-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="2f7d4-104">Nell'esempio seguente viene illustrata la funzione di accesso di una proprietà di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="2f7d4-104">The following is an example of an interface property accessor:</span></span>  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 <span data-ttu-id="2f7d4-105">La funzione di accesso di una proprietà di interfaccia non ha un corpo.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="2f7d4-106">Lo scopo delle funzioni di accesso, pertanto, è quello di indicare se la proprietà è in lettura-scrittura, in sola lettura o in sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f7d4-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f7d4-107">Example</span></span>  
 <span data-ttu-id="2f7d4-108">Nell'esempio seguente l'interfaccia `IEmployee` include una proprietà in lettura-scrittura, `Name`, e una proprietà in sola lettura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="2f7d4-109">La classe `Employee` implementa l'interfaccia `IEmployee` e usa le due proprietà.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="2f7d4-110">Il programma legge il nome di un nuovo dipendente e il numero corrente di dipendenti e quindi visualizza il nome del dipendente e il relativo numero calcolato.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="2f7d4-111">È possibile usare il nome completo della proprietà, che fa riferimento all'interfaccia in cui il membro è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="2f7d4-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2f7d4-112">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="2f7d4-113">Questo meccanismo è denominato [Implementazione esplicita dell'interfaccia](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="2f7d4-113">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="2f7d4-114">Se la classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce includono la proprietà `Name`, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="2f7d4-115">In altre parole, la dichiarazione di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="2f7d4-115">That is, the following property declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="2f7d4-116">implementa la proprietà `Name` nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="2f7d4-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 <span data-ttu-id="2f7d4-117">implementa la proprietà `Name` nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="2f7d4-117">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="2f7d4-118">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="2f7d4-118">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="2f7d4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f7d4-119">See Also</span></span>

- [<span data-ttu-id="2f7d4-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2f7d4-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2f7d4-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="2f7d4-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="2f7d4-122">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="2f7d4-122">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
- [<span data-ttu-id="2f7d4-123">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="2f7d4-123">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
- [<span data-ttu-id="2f7d4-124">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="2f7d4-124">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
- [<span data-ttu-id="2f7d4-125">Interfacce</span><span class="sxs-lookup"><span data-stu-id="2f7d4-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
