---
title: Esecuzione di query sul database
ms.date: 03/30/2017
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
ms.openlocfilehash: fdcfaa3fc0d08df07027d44399612fb688b920d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918034"
---
# <a name="querying-the-database"></a><span data-ttu-id="921f3-102">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="921f3-102">Querying the Database</span></span>
<span data-ttu-id="921f3-103">In questo gruppo di argomenti viene descritto come sviluppare ed eseguire query nei progetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="921f3-103">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="921f3-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="921f3-104">In This Section</span></span>  
 [<span data-ttu-id="921f3-105">Procedura: Eseguire query delle informazioni</span><span class="sxs-lookup"><span data-stu-id="921f3-105">How to: Query for Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-query-for-information.md)  
 <span data-ttu-id="921f3-106">Viene illustrato brevemente che le query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] corrispondono fondamentalmente alle query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] in generale.</span><span class="sxs-lookup"><span data-stu-id="921f3-106">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries generally.</span></span>  
  
 [<span data-ttu-id="921f3-107">Procedura: Recuperare le informazioni in sola lettura</span><span class="sxs-lookup"><span data-stu-id="921f3-107">How to: Retrieve Information As Read-Only</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="921f3-108">Viene descritto come migliorare le prestazioni di esecuzione delle query quando non sono pianificate modifiche dei dati.</span><span class="sxs-lookup"><span data-stu-id="921f3-108">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="921f3-109">Procedura: Controllare la quantità di dati correlati recuperata</span><span class="sxs-lookup"><span data-stu-id="921f3-109">How to: Control How Much Related Data Is Retrieved</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="921f3-110">Viene descritto come controllare quali dati correlati vengono recuperati insieme con la destinazione principale.</span><span class="sxs-lookup"><span data-stu-id="921f3-110">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="921f3-111">Procedura: Filtrare dati correlati</span><span class="sxs-lookup"><span data-stu-id="921f3-111">How to: Filter Related Data</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-related-data.md)  
 <span data-ttu-id="921f3-112">Viene descritto come recuperare dati correlati usando una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="921f3-112">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="921f3-113">Procedura: Disattivare il caricamento posticipato</span><span class="sxs-lookup"><span data-stu-id="921f3-113">How to: Turn Off Deferred Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="921f3-114">Viene descritto come disattivare il caricamento posticipato (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="921f3-114">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="921f3-115">Procedura: Eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="921f3-115">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="921f3-116">Viene descritto come inviare query usando il linguaggio SQL.</span><span class="sxs-lookup"><span data-stu-id="921f3-116">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="921f3-117">Procedura: Store e riutilizzare query</span><span class="sxs-lookup"><span data-stu-id="921f3-117">How to: Store and Reuse Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="921f3-118">Viene descritto come compilare una query una volta e usarla quindi più volte con parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="921f3-118">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="921f3-119">Procedura: Gestire le chiavi Composite nelle query</span><span class="sxs-lookup"><span data-stu-id="921f3-119">How to: Handle Composite Keys in Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="921f3-120">Viene descritto come includere più di una colonna in una query in cui l'operatore accetta un solo argomento.</span><span class="sxs-lookup"><span data-stu-id="921f3-120">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="921f3-121">Procedura: Recuperare molti oggetti contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="921f3-121">How to: Retrieve Many Objects At Once</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="921f3-122">Viene descritto come usare <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="921f3-122">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="921f3-123">Procedura: Filtrare a livello di DataContext</span><span class="sxs-lookup"><span data-stu-id="921f3-123">How to: Filter at the DataContext Level</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="921f3-124">Viene descritto un diverso utilizzo di <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="921f3-124">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="921f3-125">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="921f3-125">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="921f3-126">Vengono forniti molti esempi di query.</span><span class="sxs-lookup"><span data-stu-id="921f3-126">Provides many examples of queries.</span></span>
