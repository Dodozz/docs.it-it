---
title: Caricamento di dati in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 26b77269b21e1b365f81746ba2df66d7df91677e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504324"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="92a0b-102">Caricamento di dati in un dataset</span><span class="sxs-lookup"><span data-stu-id="92a0b-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="92a0b-103">Oggetto <xref:System.Data.DataSet> oggetto debba essere inserito per primi prima di eseguire query su di esso con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="92a0b-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="92a0b-104">Sono disponibili diversi modi per popolare <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="92a0b-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="92a0b-105">Ad esempio, è possibile usare [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] per eseguire query sul database e caricare i risultati nel <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="92a0b-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="92a0b-106">Per altre informazioni, vedere [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="92a0b-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="92a0b-107">Per caricare i dati in <xref:System.Data.DataSet>, è inoltre usare la classe <xref:System.Data.Common.DataAdapter> per recuperare i dati dal database,</span><span class="sxs-lookup"><span data-stu-id="92a0b-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="92a0b-108">Questa procedura è illustrata nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="92a0b-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92a0b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="92a0b-109">Example</span></span>  
 <span data-ttu-id="92a0b-110">In questo esempio viene usato un oggetto <xref:System.Data.Common.DataAdapter> per eseguire una query sul database AdventureWorks relativa alle informazioni sulle vendite dell'anno 2002. I risultati vengono quindi caricati in un oggetto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="92a0b-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="92a0b-111">Dopo il <xref:System.Data.DataSet> è stato popolato, è possibile scrivere query su di esso con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="92a0b-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="92a0b-112">Il `FillDataSet` metodo in questo esempio viene usato nelle query di esempio nella [LINQ to DataSet esempi](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="92a0b-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="92a0b-113">Per altre informazioni, vedere [esecuzione di query su set di dati](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="92a0b-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="92a0b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92a0b-114">See also</span></span>

- [<span data-ttu-id="92a0b-115">Panoramica di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="92a0b-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="92a0b-116">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="92a0b-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="92a0b-117">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="92a0b-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
