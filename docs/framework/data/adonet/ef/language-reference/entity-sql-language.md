---
title: Linguaggio Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: f12a20f85a0449778614d3098f69d3da90902c95
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50048443"
---
# <a name="entity-sql-language"></a><span data-ttu-id="5eadf-102">Linguaggio Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5eadf-102">Entity SQL Language</span></span>
<span data-ttu-id="5eadf-103">Entity SQL è un linguaggio di query indipendente da archiviazione che è simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="5eadf-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="5eadf-104">Entity SQL consente di eseguire una query su dati di entità, come oggetti o in un form tabulare.</span><span class="sxs-lookup"><span data-stu-id="5eadf-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="5eadf-105">L'utilizzo di Entity SQL è indicato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5eadf-105">You should consider using Entity SQL in the following cases:</span></span>  
  
-   <span data-ttu-id="5eadf-106">Quando è necessario creare una query dinamicamente in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="5eadf-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="5eadf-107">In questo caso, si dovrebbero usare anche i metodi del generatore di query di <xref:System.Data.Objects.ObjectQuery%601> anziché costruire una stringa di query Entity SQL in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="5eadf-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
-   <span data-ttu-id="5eadf-108">Quando si desidera definire una query come parte della definizione del modello.</span><span class="sxs-lookup"><span data-stu-id="5eadf-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="5eadf-109">Solo Entity SQL è supportato in un modello di dati.</span><span class="sxs-lookup"><span data-stu-id="5eadf-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="5eadf-110">Per altre informazioni, vedere [elemento QueryView (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="5eadf-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
-   <span data-ttu-id="5eadf-111">Quando si usa EntityClient per restituire dati di entità di sola lettura come set di righe usando un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="5eadf-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="5eadf-112">Per altre informazioni, vedere [EntityClient Provider per Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="5eadf-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
-   <span data-ttu-id="5eadf-113">Se si è già esperti nei linguaggi di query basati su SQL, Entity SQL potrebbe essere la soluzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="5eadf-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="5eadf-114">Uso di Entity SQL con il provider EntityClient</span><span class="sxs-lookup"><span data-stu-id="5eadf-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="5eadf-115">Se si desidera usare Entity SQL con il provider EntityClient, vedere gli argomenti seguenti per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="5eadf-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="5eadf-116">Provider EntityClient per Entity Framework</span><span class="sxs-lookup"><span data-stu-id="5eadf-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="5eadf-117">Procedura: Compilare una stringa di connessione EntityConnection</span><span class="sxs-lookup"><span data-stu-id="5eadf-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="5eadf-118">Procedura: Eseguire una query che restituisce risultati PrimitiveType</span><span class="sxs-lookup"><span data-stu-id="5eadf-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="5eadf-119">Procedura: Eseguire una query che restituisce risultati StructuralType</span><span class="sxs-lookup"><span data-stu-id="5eadf-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="5eadf-120">Procedura: Eseguire una query che restituisce risultati RefType</span><span class="sxs-lookup"><span data-stu-id="5eadf-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="5eadf-121">Procedura: Eseguire una query che restituisce tipi complessi</span><span class="sxs-lookup"><span data-stu-id="5eadf-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="5eadf-122">Procedura: Eseguire una query che restituisce raccolte annidate</span><span class="sxs-lookup"><span data-stu-id="5eadf-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="5eadf-123">Procedura: Eseguire una query Entity SQL con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="5eadf-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="5eadf-124">Procedura: Eseguire una stored procedure con parametri tramite EntityCommand</span><span class="sxs-lookup"><span data-stu-id="5eadf-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="5eadf-125">Procedura: Eseguire una query polimorfica</span><span class="sxs-lookup"><span data-stu-id="5eadf-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="5eadf-126">Procedura: Esplorare relazioni con l'operatore Navigate</span><span class="sxs-lookup"><span data-stu-id="5eadf-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="5eadf-127">Uso di Entity SQL con le query di oggetto</span><span class="sxs-lookup"><span data-stu-id="5eadf-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="5eadf-128">Se si desidera usare Entity SQL con query di oggetto, vedere gli argomenti seguenti per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="5eadf-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="5eadf-129">Procedura: eseguire una Query che restituisce oggetti di tipo di entità</span><span class="sxs-lookup"><span data-stu-id="5eadf-129">How to: Execute a Query that Returns Entity Type Objects</span></span>](https://msdn.microsoft.com/library/f73e137d-1534-42bb-9e31-99ca42c19b48)  
  
 [<span data-ttu-id="5eadf-130">Procedura: eseguire una Query con parametri</span><span class="sxs-lookup"><span data-stu-id="5eadf-130">How to: Execute a Parameterized Query</span></span>](https://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
  
 [<span data-ttu-id="5eadf-131">Procedura: esplorare relazioni tramite proprietà di navigazione</span><span class="sxs-lookup"><span data-stu-id="5eadf-131">How to: Navigate Relationships Using Navigation Properties</span></span>](https://msdn.microsoft.com/library/b1d71c7d-16a7-4b46-96ac-690176bd5057)  
  
 [<span data-ttu-id="5eadf-132">Procedura: chiamare una funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="5eadf-132">How to: Call a User-Defined Function</span></span>](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)  
  
 [<span data-ttu-id="5eadf-133">Procedura: filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="5eadf-133">How to: Filter Data</span></span>](https://msdn.microsoft.com/library/776f8556-3350-4572-804a-b1513515c1b2)  
  
 [<span data-ttu-id="5eadf-134">Procedura: ordinare dati</span><span class="sxs-lookup"><span data-stu-id="5eadf-134">How to: Sort Data</span></span>](https://msdn.microsoft.com/library/c05f2506-cb9d-4ebc-822b-300042ad53e7)  
  
 [<span data-ttu-id="5eadf-135">Procedura: raggruppare i dati</span><span class="sxs-lookup"><span data-stu-id="5eadf-135">How to: Group Data</span></span>](https://msdn.microsoft.com/library/df801d9d-9a8a-4157-97a6-5016b18998e1)  
  
 [<span data-ttu-id="5eadf-136">Procedura: aggregare dati</span><span class="sxs-lookup"><span data-stu-id="5eadf-136">How to: Aggregate Data</span></span>](https://msdn.microsoft.com/library/4cf04ce8-3c0f-4f88-9d97-8fac8622598d)  
  
 [<span data-ttu-id="5eadf-137">Procedura: eseguire una Query che restituisce oggetti di tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="5eadf-137">How to: Execute a Query that Returns Anonymous Type Objects</span></span>](https://msdn.microsoft.com/library/3b264025-e911-4d73-90ce-992d2b9d189d)  
  
 [<span data-ttu-id="5eadf-138">Procedura: eseguire una Query che restituisce una raccolta di tipi primitivi</span><span class="sxs-lookup"><span data-stu-id="5eadf-138">How to: Execute a Query that Returns a Collection of Primitive Types</span></span>](https://msdn.microsoft.com/library/115b52c0-4f27-4253-8991-284b450000b5)  
  
 [<span data-ttu-id="5eadf-139">Procedura: eseguire Query su oggetti correlati in un oggetto EntityCollection</span><span class="sxs-lookup"><span data-stu-id="5eadf-139">How to: Query Related Objects in an EntityCollection</span></span>](https://msdn.microsoft.com/library/11ce946f-16f8-4c1d-9d80-f740853807ba)  
  
 [<span data-ttu-id="5eadf-140">Procedura: ordinare l'unione di due query</span><span class="sxs-lookup"><span data-stu-id="5eadf-140">How to: Order the Union of Two Queries</span></span>](https://msdn.microsoft.com/library/853c583a-eaba-4400-830d-be974e735313)  
  
 [<span data-ttu-id="5eadf-141">Procedura: spostarsi tra Query i risultati</span><span class="sxs-lookup"><span data-stu-id="5eadf-141">How to: Page Through Query Results</span></span>](https://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
  
## <a name="in-this-section"></a><span data-ttu-id="5eadf-142">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5eadf-142">In This Section</span></span>  
 [<span data-ttu-id="5eadf-143">Panoramica di Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5eadf-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="5eadf-144">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5eadf-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="5eadf-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eadf-145">See Also</span></span>  
 [<span data-ttu-id="5eadf-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="5eadf-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)  
 [<span data-ttu-id="5eadf-147">Riferimenti per il linguaggio</span><span class="sxs-lookup"><span data-stu-id="5eadf-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
