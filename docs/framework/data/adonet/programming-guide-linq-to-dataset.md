---
title: Guida per programmatori (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 977aedd7-0084-46a0-b56f-345787a55da1
ms.openlocfilehash: 6f6ab1634769a54bd8dbafe8c9d41b11ff787d50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636482"
---
# <a name="programming-guide-linq-to-dataset"></a><span data-ttu-id="4c6b6-102">Guida per programmatori (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="4c6b6-102">Programming Guide (LINQ to DataSet)</span></span>
<span data-ttu-id="4c6b6-103">Contenuto della sezione vengono fornite informazioni di carattere concettuale ed esempi per programmare con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6b6-103">This section provides conceptual information and examples for programming with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c6b6-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4c6b6-104">In This Section</span></span>  
 [<span data-ttu-id="4c6b6-105">Query in LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4c6b6-105">Queries in LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-106">Vengono fornite informazioni sulla scrittura di query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6b6-106">Provides information about how to write [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="4c6b6-107">Esecuzione di query su oggetti DataSet</span><span class="sxs-lookup"><span data-stu-id="4c6b6-107">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-108">Viene descritto come eseguire una query su oggetti <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-108">Describes how to query <xref:System.Data.DataSet> objects.</span></span>  
  
 [<span data-ttu-id="4c6b6-109">Confronto di DataRows</span><span class="sxs-lookup"><span data-stu-id="4c6b6-109">Comparing DataRows</span></span>](../../../../docs/framework/data/adonet/comparing-datarows-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-110">Viene descritto come usare l'oggetto <xref:System.Data.DataRowComparer> per confrontare righe di dati.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-110">Describes how to use the <xref:System.Data.DataRowComparer> object to compare data rows.</span></span>  
  
 [<span data-ttu-id="4c6b6-111">Creazione di un oggetto DataTable da una query</span><span class="sxs-lookup"><span data-stu-id="4c6b6-111">Creating a DataTable From a Query</span></span>](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-112">Vengono fornite informazioni sulla creazione di un <xref:System.Data.DataTable> da un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query usando il <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="4c6b6-112">Provides information about creating a <xref:System.Data.DataTable> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [<span data-ttu-id="4c6b6-113">Procedura: Implementare CopyToDataTable\<T > in cui il tipo generico T non è un DataRow</span><span class="sxs-lookup"><span data-stu-id="4c6b6-113">How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow</span></span>](../../../../docs/framework/data/adonet/implement-copytodatatable-where-type-not-a-datarow.md)  
 <span data-ttu-id="4c6b6-114">Viene descritto come implementare un metodo `CopyToDataTable<T>` personalizzato in cui il parametro generico T non è di tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-114">Describes how to implement a custom `CopyToDataTable<T>` method where the generic parameter T is not of type <xref:System.Data.DataRow>.</span></span>  
  
 [<span data-ttu-id="4c6b6-115">Metodi generici Field e SetField</span><span class="sxs-lookup"><span data-stu-id="4c6b6-115">Generic Field and SetField Methods</span></span>](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-116">Vengono fornite informazioni sui metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> generici.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-116">Provides information about the generic <xref:System.Data.DataRowExtensions.Field%2A> and <xref:System.Data.DataRowExtensions.SetField%2A> methods.</span></span>  
  
 [<span data-ttu-id="4c6b6-117">Data binding e LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4c6b6-117">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-118">Viene descritto il processo di associazione dati usando l'oggetto <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-118">Describes databinding using the <xref:System.Data.DataView> object.</span></span>  
  
 [<span data-ttu-id="4c6b6-119">Debug di query di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4c6b6-119">Debugging LINQ to DataSet Queries</span></span>](../../../../docs/framework/data/adonet/debugging-linq-to-dataset-queries.md)  
 <span data-ttu-id="4c6b6-120">Fornisce informazioni sul debug e risoluzione dei problemi [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] le query.</span><span class="sxs-lookup"><span data-stu-id="4c6b6-120">Provides information about debugging and troubleshooting [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] queries.</span></span>  
  
 [<span data-ttu-id="4c6b6-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4c6b6-121">Security</span></span>](../../../../docs/framework/data/adonet/security-linq-to-dataset.md)  
 <span data-ttu-id="4c6b6-122">Vengono illustrati i problemi di sicurezza in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6b6-122">Describes security issues in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span>  
  
 [<span data-ttu-id="4c6b6-123">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4c6b6-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 <span data-ttu-id="4c6b6-124">Vengono forniti esempi di query in cui vengono usati operatori [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c6b6-124">Provides query examples that use the [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] operators.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c6b6-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4c6b6-125">Reference</span></span>  
 <xref:System.Data.DataRowComparer>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataView>  
  
## <a name="see-also"></a><span data-ttu-id="4c6b6-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c6b6-126">See also</span></span>

- [<span data-ttu-id="4c6b6-127">LINQ e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4c6b6-127">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="4c6b6-128">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="4c6b6-128">Language Integrated Query (LINQ)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
