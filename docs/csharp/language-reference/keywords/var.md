---
title: var - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: f0e8b0e416cb32a57a83224ab6627c9ad520ec80
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240216"
---
# <a name="var-c-reference"></a><span data-ttu-id="3cbb7-102">var (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3cbb7-102">var (C# Reference)</span></span>
<span data-ttu-id="3cbb7-103">A partire da Visual C# 3.0, le variabili dichiarate in corrispondenza dell'ambito del metodo possono contenere un oggetto `var` di"tipo" implicito.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="3cbb7-104">Una variabile locale tipizzata in modo implicito è fortemente tipizzata come se si fosse dichiarato il tipo stesso, ma è il compilatore a determinare il tipo.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="3cbb7-105">Le due dichiarazioni seguenti di `i` sono equivalenti dal punto di vista funzionale:</span><span class="sxs-lookup"><span data-stu-id="3cbb7-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```csharp  
var i = 10; // Implicitly typed. 
int i = 10; // Explicitly typed. 
```  
  
 <span data-ttu-id="3cbb7-106">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) e [Relazioni tra i tipi nelle operazioni di query LINQ](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="3cbb7-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cbb7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3cbb7-107">Example</span></span>  
 <span data-ttu-id="3cbb7-108">L'esempio seguente illustra due espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-108">The following example shows two query expressions.</span></span> <span data-ttu-id="3cbb7-109">Nella prima espressione l'uso di `var` è consentito, ma non necessario, perché il tipo del risultato della query può essere dichiarato in modo esplicito come `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="3cbb7-110">Nella seconda espressione, tuttavia, `var` consente che il risultato sia una raccolta di tipi anonimi e il nome di tale tipo non è accessibile tranne che al compilatore stesso.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-110">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="3cbb7-111">L'uso di `var` elimina la necessità di creare una nuova classe per il risultato.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-111">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="3cbb7-112">Si noti che nel secondo esempio anche la variabile di iterazione `foreach``item` deve essere tipizzata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="3cbb7-112">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3cbb7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cbb7-113">See Also</span></span>

- [<span data-ttu-id="3cbb7-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3cbb7-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3cbb7-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3cbb7-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3cbb7-116">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="3cbb7-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
