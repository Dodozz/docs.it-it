---
title: 'Esempi di sintassi di Query basate sul metodo: Raggruppamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: d414218604887fca2d69a02b40dfa87f13961aae
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825381"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="e1445-102">Esempi di sintassi di Query basate sul metodo: Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="e1445-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="e1445-103">Gli esempi in questo argomento mostrano come usare il `GroupBy` metodo di query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="e1445-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="e1445-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e1445-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e1445-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="e1445-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="e1445-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1445-106">Example</span></span>  
 <span data-ttu-id="e1445-107">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Address` raggruppati in base al codice postale.</span><span class="sxs-lookup"><span data-stu-id="e1445-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="e1445-108">I risultati vengono proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="e1445-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="e1445-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1445-109">Example</span></span>  
 <span data-ttu-id="e1445-110">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Contact` raggruppati in base alla prima lettera del cognome del contatto.</span><span class="sxs-lookup"><span data-stu-id="e1445-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="e1445-111">I risultati vengono anche ordinati in base alla prima lettera del cognome e proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="e1445-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="e1445-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1445-112">Example</span></span>  
 <span data-ttu-id="e1445-113">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `SalesOrderHeader` raggruppati in base all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="e1445-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="e1445-114">Viene restituito anche il numero di vendite per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="e1445-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e1445-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1445-115">See also</span></span>
- [<span data-ttu-id="e1445-116">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e1445-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
