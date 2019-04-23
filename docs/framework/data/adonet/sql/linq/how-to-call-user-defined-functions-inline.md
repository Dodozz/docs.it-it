---
title: "Procedura: Chiamare funzioni inline definite dall'utente"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: ed8071352902b8f97445cbfa5ff0ebe8fead9bb9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163709"
---
# <a name="how-to-call-user-defined-functions-inline"></a>Procedura: Chiamare funzioni inline definite dall'utente
Anche se è possibile chiamare le funzioni inline definite dall'utente, le funzioni incluse in una query la cui esecuzione è rinviata non vengono eseguite finche non verrà eseguita la query. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 Quando si chiama la stessa funzione al di fuori di una query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una semplice query dall'espressione della chiamata al metodo. Di seguito è riportata la sintassi SQL, in cui il parametro `@p0` è associato alla costante passata:  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene creato quanto segue:  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a>Esempio  
 Di seguito [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, è possibile visualizzare un chiamata inline al metodo di funzione definita dall'utente generato `ReverseCustName`. La funzione non viene eseguita immediatamente poiché l'esecuzione della query è rinviata. Il codice SQL compilato per questa query viene convertito in una chiamata alla funzione definita dall'utente nel database. Vedere il codice SQL che segue la query.  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni definite dall'utente](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
