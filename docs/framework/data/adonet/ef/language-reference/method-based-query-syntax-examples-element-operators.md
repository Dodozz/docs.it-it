---
title: 'Esempi di sintassi delle query basate su metodo: Operatori di elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 3656ea6d2d9602c3790ab4113b5c2f153b4f7c73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188591"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="ffcaf-102">Esempi di sintassi delle query basate su metodo: Operatori di elemento</span><span class="sxs-lookup"><span data-stu-id="ffcaf-102">Method-Based Query Syntax Examples: Element Operators</span></span>
<span data-ttu-id="ffcaf-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.First%2A> metodo di query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="ffcaf-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="ffcaf-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ffcaf-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ffcaf-105">L'esempio in questo argomento Usa quanto segue `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="ffcaf-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="ffcaf-106">First</span><span class="sxs-lookup"><span data-stu-id="ffcaf-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="ffcaf-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ffcaf-107">Example</span></span>  
 <span data-ttu-id="ffcaf-108">L'esempio seguente usa il <xref:System.Linq.Enumerable.First%2A> metodo per trovare il primo indirizzo di posta elettronica che inizia con la parola 'caroline'.</span><span class="sxs-lookup"><span data-stu-id="ffcaf-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ffcaf-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffcaf-109">See also</span></span>

- [<span data-ttu-id="ffcaf-110">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="ffcaf-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
