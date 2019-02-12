---
title: 'Esempi di sintassi di espressione di query: Operatori di join (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: 1e435ba0a5d2c8d26593dca432ce0cb6430d5752
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56094139"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="7c5f3-102">Esempi di sintassi di espressione di query: Operatori di join (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-102">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="7c5f3-103">La creazione di un join è un'operazione importante in query destinate a origini dati che non presentano relazioni esplorabili tra loro, ad esempio le tabelle di database relazionali.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="7c5f3-104">Per join di due origini dati si intende l'associazione degli oggetti di un'origine dati con oggetti che condividono un attributo comune nell'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="7c5f3-105">Per altre informazioni, vedere [panoramica degli operatori Query Standard (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) oppure [panoramica degli operatori di Query Standard (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7c5f3-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="7c5f3-106">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.GroupJoin%2A> e <xref:System.Linq.Enumerable.Join%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="7c5f3-107">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="7c5f3-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="7c5f3-108">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7c5f3-109">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="7c5f3-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="7c5f3-110">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="7c5f3-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="7c5f3-111">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="7c5f3-111">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="7c5f3-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c5f3-112">Example</span></span>  
 <span data-ttu-id="7c5f3-113">In questo esempio viene eseguito <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle `SalesOrderHeader` e `SalesOrderDetail` per individuare il numero di ordini per cliente.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-113">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="7c5f3-114">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-114">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="7c5f3-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c5f3-115">Example</span></span>  
 <span data-ttu-id="7c5f3-116">In questo esempio viene eseguito <xref:System.Linq.Enumerable.GroupJoin%2A> sulle tabelle `Contact` e `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-116">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="7c5f3-117">Questa operazione equivale a un left outer join, che restituisce ogni elemento della prima origine dati (a sinistra), anche se nell'altra origine dati non sono presenti elementi correlati.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-117">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="7c5f3-118">Join</span><span class="sxs-lookup"><span data-stu-id="7c5f3-118">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="7c5f3-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c5f3-119">Example</span></span>  
 <span data-ttu-id="7c5f3-120">In questo esempio viene eseguito un join sulle tabelle `SalesOrderHeader` e `SalesOrderDetail` per ottenere gli ordini effettuati online dal mese di agosto.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-120">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="7c5f3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c5f3-121">See also</span></span>
- [<span data-ttu-id="7c5f3-122">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="7c5f3-122">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="7c5f3-123">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7c5f3-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="7c5f3-124">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-124">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="7c5f3-125">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-125">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
