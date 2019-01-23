---
title: 'Esempi di sintassi di Query basate sul metodo: Partizionamento (LINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a582c53f-f203-44ae-a797-d7f169a4fbb5
ms.openlocfilehash: a18f19ead84d3b91b3ddd724360f3800abe286b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524741"
---
# <a name="method-based-query-syntax-examples-partitioning-linq"></a><span data-ttu-id="50438-102">Esempi di sintassi di Query basate sul metodo: Partizionamento (LINQ</span><span class="sxs-lookup"><span data-stu-id="50438-102">Method-Based Query Syntax Examples: Partitioning (LINQ</span></span>
<span data-ttu-id="50438-103">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.TakeWhile%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="50438-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>, <xref:System.Linq.Enumerable.Take%2A>, and <xref:System.Linq.Enumerable.TakeWhile%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="50438-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="50438-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="50438-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="50438-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="50438-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="50438-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="50438-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="50438-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="50438-108">Skip</span><span class="sxs-lookup"><span data-stu-id="50438-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="50438-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-109">Example</span></span>  
 <span data-ttu-id="50438-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti i contatti ad eccezione dei primi cinque della tabella `Contact`.</span><span class="sxs-lookup"><span data-stu-id="50438-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP LINQ to DataSet Examples#SkipSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="50438-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-111">Example</span></span>  
 <span data-ttu-id="50438-112">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Skip%2A> per ottenere tutti gli indirizzi di Seattle ad eccezione dei primi due.</span><span class="sxs-lookup"><span data-stu-id="50438-112">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="skipwhile"></a><span data-ttu-id="50438-113">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="50438-113">SkipWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="50438-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-114">Example</span></span>  
 <span data-ttu-id="50438-115">In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.SkipWhile%2A> per restituire i prodotti della tabella `Product` il cui prezzo di listino è maggiore di 300.00.</span><span class="sxs-lookup"><span data-stu-id="50438-115">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.SkipWhile%2A> methods to return products from the `Product` table with a list price greater than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipwhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SkipWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipwhilesimple_mq)]  
  
## <a name="take"></a><span data-ttu-id="50438-116">Take</span><span class="sxs-lookup"><span data-stu-id="50438-116">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="50438-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-117">Example</span></span>  
 <span data-ttu-id="50438-118">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere solo i primi cinque contatti della tabella `Contact`.</span><span class="sxs-lookup"><span data-stu-id="50438-118">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the `Contact` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP LINQ to DataSet Examples#TakeSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="50438-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-119">Example</span></span>  
 <span data-ttu-id="50438-120">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Take%2A> per ottenere i primi tre indirizzi di Seattle.</span><span class="sxs-lookup"><span data-stu-id="50438-120">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="takewhile"></a><span data-ttu-id="50438-121">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="50438-121">TakeWhile</span></span>  
  
### <a name="example"></a><span data-ttu-id="50438-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="50438-122">Example</span></span>  
 <span data-ttu-id="50438-123">In questo esempio vengono usati i metodi <xref:System.Linq.Enumerable.OrderBy%2A> e <xref:System.Linq.Enumerable.TakeWhile%2A> per restituire i prodotti della tabella `Product` il cui prezzo di listino è minore di 300.00.</span><span class="sxs-lookup"><span data-stu-id="50438-123">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.TakeWhile%2A> to return products from the `Product` table with a list price less than 300.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takewhilesimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#TakeWhileSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takewhilesimple_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="50438-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50438-124">See also</span></span>
- [<span data-ttu-id="50438-125">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="50438-125">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="50438-126">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="50438-126">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="50438-127">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="50438-127">Standard Query Operators Overview</span></span>](https://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)
