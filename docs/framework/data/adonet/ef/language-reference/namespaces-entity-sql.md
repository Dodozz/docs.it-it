---
title: Spazi dei nomi (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7bcd7a72df8afbd598a15ccd9a259ed11b5b9ef7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583816"
---
# <a name="namespaces-entity-sql"></a>Spazi dei nomi (Entity SQL)
In [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono introdotti gli spazi dei nomi per evitare conflitti di nome per gli identificatori globali, ad esempio nomi di tipi, set di entità, funzioni e così via. Il supporto dello spazio dei nomi in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] è simile al supporto dello spazio dei nomi in .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] fornisce due tipi di clausola USING: spazi dei nomi qualificati (dove viene fornito un alias più breve per lo spazio dei nomi) e spazi dei nomi non qualificati, come illustrato nell'esempio seguente:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Regole per la risoluzione dei nomi  
 Se un identificatore non può essere risolto negli ambiti locali, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta di individuare il nome negli ambiti globali (gli spazi dei nomi). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta innanzitutto di confrontare l'identificatore (prefisso) con uno degli spazi dei nomi qualificati. Se non esiste una corrispondenza, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenterà di risolvere il resto dell'identificatore nello spazio dei nomi specificato. Se non viene trovata alcuna corrispondenza, viene generata un'eccezione .  
  
 Successivamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tenta tutte non qualificati gli spazi dei nomi (specificati nel prologo) per l'identificatore di ricerca. Se l'identificatore può essere individuato esattamente in uno spazio dei nomi, viene restituito tale percorso. Se la corrispondenza per l'identificatore è presente in più di uno spazio dei nomi, viene generata un'eccezione. Se nessuno spazio dei nomi può essere identificato per l'identificatore [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passa il nome all'ambito esterno successivo (la <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection> oggetto), come illustrato nell'esempio seguente:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Differenze rispetto a .NET Framework  
 In .NET Framework, è possibile usare gli spazi dei nomi parzialmente qualificati. Ciò non è consentito in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
## <a name="adonet-usage"></a>Uso di ADO.NET  
 Le query sono espresse attraverso oggetti <xref:System.Data.Common.DbCommand> ADO.NET. Gli oggetti <xref:System.Data.Common.DbCommand> possono essere creati in base a oggetti <xref:System.Data.Common.DbConnection>. Anche gli spazi dei nomi possono essere specificati come parte degli oggetti <xref:System.Data.Common.DbCommand> e <xref:System.Data.Common.DbConnection>. Se [!INCLUDE[esql](../../../../../../includes/esql-md.md)] non è possibile risolvere un identificatore all'interno della query stessa, gli spazi dei nomi esterni viene eseguito il probe (basato su regole simili).  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
