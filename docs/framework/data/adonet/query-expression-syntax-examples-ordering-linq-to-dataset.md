---
title: 'Esempi di sintassi delle espressioni di query: Ordinamento (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: b8f605eaa3a186ebb6bad7800d6576bd4d5a34b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203899"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="d0d35-102">Esempi di sintassi delle espressioni di query: Ordinamento (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d0d35-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="d0d35-103">Negli esempi di questo argomento viene illustrato come usare i metodi <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> e <xref:System.Linq.Enumerable.ThenByDescending%2A> per eseguire una query su <xref:System.Data.DataSet> e ordinare i risultati usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="d0d35-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="d0d35-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d0d35-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="d0d35-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d0d35-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d0d35-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="d0d35-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="d0d35-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d0d35-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="d0d35-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="d0d35-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0d35-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0d35-109">Example</span></span>  
 <span data-ttu-id="d0d35-110">In questo esempio viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per restituire un elenco di contatti ordinati in base al cognome.</span><span class="sxs-lookup"><span data-stu-id="d0d35-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="d0d35-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0d35-111">Example</span></span>  
 <span data-ttu-id="d0d35-112">In questo esempio viene usato <xref:System.Linq.Enumerable.OrderBy%2A> per ordinare un elenco di contatti in base alla lunghezza del cognome.</span><span class="sxs-lookup"><span data-stu-id="d0d35-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="d0d35-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="d0d35-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0d35-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0d35-114">Example</span></span>  
 <span data-ttu-id="d0d35-115">In questo esempio viene usato `orderby… descending` (`Order By … Descending`), equivalente al metodo <xref:System.Linq.Enumerable.OrderByDescending%2A>, per ordinare il listino prezzi dal massimo al minimo.</span><span class="sxs-lookup"><span data-stu-id="d0d35-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="d0d35-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="d0d35-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0d35-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0d35-117">Example</span></span>  
 <span data-ttu-id="d0d35-118">In questo esempio viene usato <xref:System.Linq.Enumerable.Reverse%2A> per creare un elenco di ordini in cui il valore di `OrderDate` è precedente al 20 febbraio 2002.</span><span class="sxs-lookup"><span data-stu-id="d0d35-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="d0d35-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="d0d35-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0d35-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0d35-120">Example</span></span>  
 <span data-ttu-id="d0d35-121">In questo esempio viene usato `OrderBy… Descending`, equivalente al metodo <xref:System.Linq.Enumerable.ThenByDescending%2A>, per ordinare un elenco di prodotti dapprima in base al nome e quindi in base al prezzo di listino, dal massimo al minimo.</span><span class="sxs-lookup"><span data-stu-id="d0d35-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="d0d35-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0d35-122">See also</span></span>

- [<span data-ttu-id="d0d35-123">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="d0d35-123">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="d0d35-124">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d0d35-124">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="d0d35-125">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="d0d35-125">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d0d35-126">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0d35-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
