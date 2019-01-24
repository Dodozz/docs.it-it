---
title: 'Esempi di sintassi di Query basate sul metodo: Raggruppamento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 7ade24ecee5a69403f3264a62fbdffdcd9decd3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634476"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="786d5-102">Esempi di sintassi di Query basate sul metodo: Raggruppamento</span><span class="sxs-lookup"><span data-stu-id="786d5-102">Method-Based Query Syntax Examples: Grouping</span></span>
<span data-ttu-id="786d5-103">Gli esempi in questo argomento mostrano come usare il `GroupBy` metodo di query il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="786d5-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="786d5-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="786d5-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="786d5-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="786d5-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="786d5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="786d5-106">Example</span></span>  
 <span data-ttu-id="786d5-107">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Address` raggruppati in base al codice postale.</span><span class="sxs-lookup"><span data-stu-id="786d5-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="786d5-108">I risultati vengono proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="786d5-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="786d5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="786d5-109">Example</span></span>  
 <span data-ttu-id="786d5-110">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `Contact` raggruppati in base alla prima lettera del cognome del contatto.</span><span class="sxs-lookup"><span data-stu-id="786d5-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="786d5-111">I risultati vengono anche ordinati in base alla prima lettera del cognome e proiettati in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="786d5-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="786d5-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="786d5-112">Example</span></span>  
 <span data-ttu-id="786d5-113">Nell'esempio seguente viene usato il metodo `GroupBy` per restituire oggetti `SalesOrderHeader` raggruppati in base all'ID cliente.</span><span class="sxs-lookup"><span data-stu-id="786d5-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="786d5-114">Viene restituito anche il numero di vendite per ogni cliente.</span><span class="sxs-lookup"><span data-stu-id="786d5-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="786d5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="786d5-115">See also</span></span>
- [<span data-ttu-id="786d5-116">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="786d5-116">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
