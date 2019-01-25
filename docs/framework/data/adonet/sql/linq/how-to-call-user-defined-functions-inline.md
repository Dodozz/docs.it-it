---
title: "Procedura: Chiamare funzioni definite dall'utente Inline"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 76a41ded52ac29b4a8b597188171333a888be5cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692769"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="65e9d-102">Procedura: Chiamare funzioni definite dall'utente Inline</span><span class="sxs-lookup"><span data-stu-id="65e9d-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="65e9d-103">Anche se è possibile chiamare le funzioni inline definite dall'utente, le funzioni incluse in una query la cui esecuzione è rinviata non vengono eseguite finche non verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="65e9d-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="65e9d-104">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65e9d-104">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="65e9d-105">Quando si chiama la stessa funzione al di fuori di una query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una semplice query dall'espressione della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="65e9d-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="65e9d-106">Di seguito è riportata la sintassi SQL, in cui il parametro `@p0` è associato alla costante passata:</span><span class="sxs-lookup"><span data-stu-id="65e9d-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 <span data-ttu-id="65e9d-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene creato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="65e9d-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="65e9d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="65e9d-108">Example</span></span>  
 <span data-ttu-id="65e9d-109">Di seguito [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, è possibile visualizzare un chiamata inline al metodo di funzione definita dall'utente generato `ReverseCustName`.</span><span class="sxs-lookup"><span data-stu-id="65e9d-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="65e9d-110">La funzione non viene eseguita immediatamente poiché l'esecuzione della query è rinviata.</span><span class="sxs-lookup"><span data-stu-id="65e9d-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="65e9d-111">Il codice SQL compilato per questa query viene convertito in una chiamata alla funzione definita dall'utente nel database. Vedere il codice SQL che segue la query.</span><span class="sxs-lookup"><span data-stu-id="65e9d-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="65e9d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65e9d-112">See also</span></span>
- [<span data-ttu-id="65e9d-113">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="65e9d-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
