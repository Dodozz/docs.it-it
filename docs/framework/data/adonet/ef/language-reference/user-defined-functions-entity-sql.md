---
title: Funzioni definite dall'utente (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: 4922e7fada676a6c26042236ccdb6315d6d455ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879749"
---
# <a name="user-defined-functions-entity-sql"></a>Funzioni definite dall'utente (Entity SQL)
Nelle query Entity SQL sono supportate le chiamate a funzioni definite dall'utente. È possibile definire queste funzioni inline con la query (vedere [come: Chiamare una funzione definita dall'utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))) o come parte del modello concettuale (vedere [come: Definire funzioni personalizzate nel modello concettuale](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))). Funzioni del modello concettuale sono definite come un comando Entity SQL nel [DefiningExpression](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#definingexpression-element-csdl) elemento di un [funzione](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#function-element-csdl) elemento nel modello concettuale.  
  
 Entity SQL consente di definire delle funzioni nel comando di query stesso. Il [funzione](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operatore definisce funzioni inline. È possibile definire più funzioni in un singolo comando e queste funzioni possono avere lo stesso nome purché le rispettive firme siano univoche. Per altre informazioni, vedere [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
