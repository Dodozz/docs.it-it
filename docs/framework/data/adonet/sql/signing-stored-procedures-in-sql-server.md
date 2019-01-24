---
title: Firma di stored procedure in SQL Server
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: da7b21d725d301006288245c940e4367c3ce8568
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606822"
---
# <a name="signing-stored-procedures-in-sql-server"></a>Firma di stored procedure in SQL Server
 Un firma digitale è un digest di dati crittografato con la chiave privata del firmatario. La chiave privata garantisce che la firma digitale è univoca per il titolare o il proprietario. È possibile firmare gli assembly, funzioni (ad eccezione delle funzioni inline con valori di tabella), trigger e stored procedure.  
  
 È possibile firmare una stored procedure con un certificato o una chiave asimmetrica. Le firme sono progettate per scenari in cui le autorizzazioni non possono essere ereditate tramite il concatenamento della proprietà oppure in cui la catena di proprietà è interrotta, come nel caso delle istruzioni SQL dinamiche. È quindi possibile creare un utente con mappato al certificato, concedere autorizzazioni utente per gli oggetti che stored procedure deve accedere il certificato.  

 È anche possibile creare un account di accesso mappato per lo stesso certificato, quindi concedere le autorizzazioni a livello di server necessarie per tale account di accesso oppure aggiungere l'account di accesso a uno o più dei ruoli predefiniti del server. Questa è progettata per evitare di abilitare il `TRUSTWORTHY` impostazione per gli scenari in cui sono necessarie autorizzazioni di livello superiore di database.  
  
 Quando viene eseguita la stored procedure, SQL Server combina le autorizzazioni dell'utente di certificato e/o account di accesso con quelle del chiamante. A differenza di `EXECUTE AS` clausola, non viene modificato il contesto di esecuzione della procedura. Le funzioni predefinite che restituiscono i nomi di accesso e i nomi utente restituiscono il nome del chiamante e non il nome dell'utente del certificato.  
  
## <a name="creating-certificates"></a>Creazione di certificati  
 Quando si firma una stored procedure con un certificato o chiave asimmetrica, un digest di dati costituito dall'hash crittografato del codice della stored procedure, insieme a execute-come utente, viene creato usando la chiave privata. In fase di esecuzione il digest di dati viene decrittografato usando la chiave pubblica e confrontato con il valore hash della stored procedure. Modifica execute-come il valore hash operazione annullata dall'utente in modo che la firma digitale non corrisponde più. Modifica della stored procedure rimuove la firma interamente, che impedisce a un utente che non hanno accesso alla chiave privata di modificare il codice della stored procedure. In entrambi i casi, è necessario firmare nuovamente la procedura ogni volta che si modifica il codice o execute-come utente.  
  
 Sono disponibili due passaggi necessari per la firma di un modulo:  
  
1.  Creazione di un certificato tramite l'istruzione `CREATE CERTIFICATE [certificateName]` Transact-SQL. Questa istruzione prevede diverse opzioni per l'impostazione di una data di inizio e una data di fine, nonché di una password. La data di scadenza predefinito è un anno.  
  
1.  Firma della stored procedure con il certificato tramite l'istruzione `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` Transact-SQL.  

Una volta il modulo è stato firmato, una o più entità deve essere creato per contenere le autorizzazioni aggiuntive che devono essere associate con il certificato.  

Se il modulo deve disporre di autorizzazioni a livello di database aggiuntive:  
  
1.  Creazione di un utente del database associato al certificato tramite l'istruzione `CREATE USER [userName] FROM CERTIFICATE [certificateName]` Transact-SQL. Questo utente esiste solo nel database e non è associato a un account di accesso, a meno che un account di accesso sia stato creato anche dallo stesso certificato.  
  
1.  Concedere le autorizzazioni a livello di database necessari utente del certificato.  
  
Se il modulo deve disporre di autorizzazioni a livello di server aggiuntivi:  
  
1.  Copiare il certificato per il `master` database.  
 
1.  Creare un account di accesso associato al certificato usando l'istruzione Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` istruzione.  
  
1.  Concedere le autorizzazioni necessarie a livello di server l'account di accesso certificato.  
  
> [!NOTE]  
>  Un certificato non può concedere autorizzazioni a un utente al quale sono state revocate autorizzazioni usando l'istruzione DENY. DENY ha sempre la precedenza su GRANT e impedisce al chiamante di ereditare autorizzazioni concesse all'utente del certificato.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Firma del modulo](https://go.microsoft.com/fwlink/?LinkId=98590) nella documentazione Online di SQL Server|Viene descritta la procedura di firma dei moduli e vengono forniti uno scenario di esempio e collegamenti agli argomenti Transact-SQL attinenti.|  
|[Stored procedure con un certificato di firma](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate) nella documentazione Online di SQL Server|Viene fornita un'esercitazione per firmare una stored procedure con un certificato.|  
  
## <a name="see-also"></a>Vedere anche
- [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Cenni preliminari sulla sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Gestione delle autorizzazioni con stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Scrittura dinamica sicura in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [Personalizzazione delle autorizzazioni con rappresentazione in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [Modifica di dati con stored procedure](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
