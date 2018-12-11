---
title: Funzioni data e ora
ms.date: 03/30/2017
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
ms.openlocfilehash: 358d124da5fb60d38d5e906a821c0b4bc86baab2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148990"
---
# <a name="date-and-time-functions"></a>Funzioni data e ora
Il provider di dati .NET Framework per SQL Server (SqlClient) fornisce funzioni di data e ora che eseguono operazioni in un valore di input `System.DateTime` e restituiscono un risultato di tipo `string`, `System.DateTime` o numerico. Tali funzioni si trovano nello spazio dei nomi SqlServer, disponibile quando si usa SqlClient. Una proprietà dello spazio dei nomi del provider consente a Entity Framework di individuare il prefisso usato dal provider per costrutti specifici, ad esempio tipi e funzioni. Nella tabella seguente mostra le funzioni di data e ora SqlClient.  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`DATEADD(datepart, number, date)`|Restituisce un nuovo valore `DateTime` basato sull'aggiunta di un intervallo alla data specificata.<br /><br /> **Argomenti**<br /><br /> `datepart`: Oggetto `String` che rappresenta la parte della data in cui si desidera restituire un nuovo valore.<br /><br /> `number`: Valore `Int32`, `Int64`, `Decimal` o `Double` utilizzato per incrementare `datepart`.<br /><br /> `date:` Un'espressione che restituisce un `DateTime`, oppure `DateTimeOffset`, o `Time` con precisione = [0-7] o una stringa di caratteri in un formato di Data.<br /><br /> **Valore restituito**<br /><br /> Un nuovo valore `DateTime` o `DateTimeOffset` o `Time` con precisione = [0-7].<br /><br /> **Esempio**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(datepart,startdate,enddate)`|Restituisce il numero di limiti di data e ora attraversati tra due date specificate.<br /><br /> **Argomenti**<br /><br /> `datepart`: Oggetto `String` che rappresenta la parte della data per calcolare la differenza.<br /><br /> `startdate`: Data di inizio per il calcolo è un'espressione che restituisce un `DateTime`, oppure `DateTimeOffset`, o `Time` valore con precisione = [0-7] o una stringa di caratteri in un formato di Data.<br /><br /> `enddate:` Una data di fine per il calcolo è un'espressione che restituisce un `DateTime`, oppure `DateTimeOffset`, o `Time` valore con precisione = [0-7] o una stringa di caratteri in un formato di Data.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Int32`.<br /><br /> **Esempio**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(datepart, date)`|Restituisce una stringa di caratteri che rappresenta il valore datepart specificato della data indicata.<br /><br /> **Argomenti**<br /><br /> `datepart`: Oggetto `String` che rappresenta la parte della data in cui si desidera restituire un nuovo valore.<br /><br /> `date`: Un'espressione che restituisce un `DateTime,` oppure `DateTimeOffset`, o `Time` valore con precisione = [0-7] o una stringa di caratteri in un formato di Data.<br /><br /> **Valore restituito**<br /><br /> Stringa di caratteri che rappresenta la parte della data specificata nella data specificata.<br /><br /> **Esempio**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(datepart, date)`|Restituisce un integer che rappresenta la parte specificata della data indicata.<br /><br /> **Argomenti**<br /><br /> `datepart`: Oggetto `String` che rappresenta la parte della data in cui si desidera restituire un nuovo valore.<br /><br /> `date`: Un'espressione che restituisce un `DateTime,` oppure `DateTimeOffset,` o `Time` valore con precisione = [0-7] o una stringa di caratteri in un formato di Data.<br /><br /> **Valore restituito**<br /><br /> La parte della data specificata nella data specificata, come un valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(date)`|Restituisce il giorno della data specificata come numero intero.<br /><br /> **Argomenti**<br /><br /> `date`: Un'espressione di tipo `DateTime` o `DateTimeOffset` con precisione = 0-7.<br /><br /> **Valore restituito**<br /><br /> Il giorno della data specificata come un valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Restituisce la data e l'ora correnti nel formato interno di SQL Server per i valori datetime.<br /><br /> **Valore restituito**<br /><br /> Data e ora di sistema correnti come oggetto `DateTime` con una precisione di 3.<br /><br /> **Esempio**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Restituisce il valore datetime nel formato UTC (Coordinated Universal Time o ora di Greenwich).<br /><br /> **Valore restituito**<br /><br /> Valore `DateTime` con una precisione di 3 in formato UTC.<br /><br /> **Esempio**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(date)`|Restituisce, come valore intero, il mese della data specificata.<br /><br /> **Argomenti**<br /><br /> `date`: Un'espressione di tipo `DateTime` o `DateTimeOffset` con precisione = 0-7.<br /><br /> **Valore restituito**<br /><br /> Mese della data specificata come valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(date)`|Restituisce, come valore intero, l'anno della data specificata.<br /><br /> **Argomenti**<br /><br /> `date`: Un'espressione di tipo `DateTime` o `DateTimeOffset` con precisione = 0-7.<br /><br /> **Valore restituito**<br /><br /> Anno della data specificata come valore `Int32`.<br /><br /> **Esempio**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Restituisce un valore `DateTime` con una precisione di 7.<br /><br /> **Valore restituito**<br /><br /> Valore `DateTime` con una precisione di 7.<br /><br /> **Esempio**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Restituisce il valore datetime nel formato UTC (Coordinated Universal Time o ora di Greenwich).<br /><br /> **Valore restituito**<br /><br /> Valore `DateTime` con precisione = 7 in formato UTC.<br /><br /> **Esempio**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Restituisce un valore `DateTimeOffset` con una precisione di 7.<br /><br /> **Valore restituito**<br /><br /> Valore `DateTimeOffset` con una precisione di 7 in formato UTC.<br /><br /> **Esempio**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Per altre informazioni sulle funzioni di data e ora supportate da SqlClient, vedere la documentazione relativa alla versione di SQL Server specificata nel file manifesto del provider SqlClient:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Funzioni di data e ora (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115908)|[Funzioni di data e ora (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115909)|[Funzioni di data e ora (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=98360)|  
  
## <a name="see-also"></a>Vedere anche  
 [SqlClient per funzioni Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
