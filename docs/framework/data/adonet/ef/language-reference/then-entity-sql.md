---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: 8d2d7f9a3a1d6ff9f25db3f19bf8f39781469f9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797644"
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
Risultato di una clausola WHEN quando restituisce `true`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>Argomenti  
 `when_expression`  
 Qualsiasi espressione booleana valida.  
  
 `then_expression`  
 Qualsiasi espressione di query valida che restituisce una raccolta.  
  
## <a name="remarks"></a>Note  
 Se `when_expression` restituisce il valore `true`, il risultato è l'oggetto `then-expression`corrispondente. Se nessuna delle condizioni WHEN è soddisfatta, viene restituito `else-expression` . Se, tuttavia, non sono presenti `else-expression`, il risultato è null.  
  
 Per un esempio, vedere [caso](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usata l'espressione CASE per valutare un set di espressioni `Boolean` . La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1. Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>Vedere anche

- [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)
- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
