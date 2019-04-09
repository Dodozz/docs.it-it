---
title: 'Esempi di sintassi delle query basate su metodo: Operatori sui set (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: 48aa6044f39be93f144b6c4af5137b131dda0b30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085818"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="76741-102">Esempi di sintassi delle query basate su metodo: Operatori sui set (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="76741-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="76741-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, e <xref:System.Linq.Enumerable.Union%2A> operatori per eseguire operazioni di confronto basate su valore su set di righe di dati.[ Il caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) visualizzare [confronto di DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) per altre informazioni su <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="76741-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md) See [Comparing DataRows](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="76741-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="76741-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="76741-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="76741-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="76741-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="76741-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="76741-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="76741-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="76741-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="76741-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="76741-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="76741-109">Example</span></span>  
 <span data-ttu-id="76741-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Distinct%2A> per rimuovere elementi duplicati in una sequenza.</span><span class="sxs-lookup"><span data-stu-id="76741-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="76741-111">Eccezione</span><span class="sxs-lookup"><span data-stu-id="76741-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="76741-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="76741-112">Example</span></span>  
 <span data-ttu-id="76741-113">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Except%2A> per restituire i contatti presenti nella prima tabella ma non nella seconda.</span><span class="sxs-lookup"><span data-stu-id="76741-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="76741-114">Interseca</span><span class="sxs-lookup"><span data-stu-id="76741-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="76741-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="76741-115">Example</span></span>  
 <span data-ttu-id="76741-116">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Intersect%2A> per restituire i contatti presenti in entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="76741-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="76741-117">Unione</span><span class="sxs-lookup"><span data-stu-id="76741-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="76741-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="76741-118">Example</span></span>  
 <span data-ttu-id="76741-119">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Union%2A> per restituire contatti univoci presenti nelle due tabelle.</span><span class="sxs-lookup"><span data-stu-id="76741-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="76741-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76741-120">See also</span></span>

- [<span data-ttu-id="76741-121">Caricamento di dati in un dataset</span><span class="sxs-lookup"><span data-stu-id="76741-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="76741-122">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="76741-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="76741-123">Cenni preliminari sugli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="76741-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="76741-124">Cenni preliminari sugli operatori di Query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76741-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
