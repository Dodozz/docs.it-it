---
title: 'Esempi di sintassi di Query basate sul metodo: Proiezione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: c1cad442ba2e6d2567c2e4936d7d8b3cd49b0424
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152416"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="6d588-102">Esempi di sintassi di Query basate sul metodo: Proiezione</span><span class="sxs-lookup"><span data-stu-id="6d588-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="6d588-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Select%2A> e <xref:System.Linq.Enumerable.SelectMany%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="6d588-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using method-based query syntax.</span></span> <span data-ttu-id="6d588-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6d588-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6d588-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="6d588-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="6d588-106">Seleziona</span><span class="sxs-lookup"><span data-stu-id="6d588-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="6d588-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d588-107">Example</span></span>  
 <span data-ttu-id="6d588-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per proiettare le proprietà `Product.Name` e `Product.ProductID` in una sequenza di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="6d588-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="6d588-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d588-109">Example</span></span>  
 <span data-ttu-id="6d588-110">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Select%2A> per restituire una sequenza dei soli nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="6d588-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="6d588-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="6d588-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="6d588-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d588-112">Example</span></span>  
 <span data-ttu-id="6d588-113">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini in cui `TotalDue` è minore di 500,00.</span><span class="sxs-lookup"><span data-stu-id="6d588-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="6d588-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d588-114">Example</span></span>  
 <span data-ttu-id="6d588-115">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini effettuati a partire dall'1 ottobre 2002.</span><span class="sxs-lookup"><span data-stu-id="6d588-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6d588-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d588-116">See Also</span></span>  
 [<span data-ttu-id="6d588-117">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="6d588-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
