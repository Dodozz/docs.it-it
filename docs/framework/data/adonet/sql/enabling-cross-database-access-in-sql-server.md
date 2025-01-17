---
title: Abilitazione dell'accesso tra database in SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 50e2a9149074d2d29ff2e17fa2a339bd7820b984
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490088"
---
# <a name="enabling-cross-database-access-in-sql-server"></a>Abilitazione dell'accesso tra database in SQL Server
Il concatenamento della proprietà tra database si verifica quando una procedura di un database dipende dagli oggetti di un altro. Una catena di proprietà tra database funziona allo stesso modo del concatenamento della proprietà con un singolo database, ad eccezione del fatto che una catena di proprietà non interrotta richiede che tutti i proprietari degli oggetti siano mappati allo stesso account di accesso. Se l'oggetto di origine nel database di origine e gli oggetti di destinazione nei database di destinazione appartengono allo stesso account di accesso, le autorizzazioni sugli oggetti di destinazione non verranno controllate in SQL Server.  
  
## <a name="off-by-default"></a>Disattivazione per impostazione predefinita  
 Il concatenamento della proprietà tra database è disattivato per impostazione predefinita. Microsoft consiglia di disabilitare questa funzionalità perché espone la sicurezza ai seguenti rischi:  
  
- I proprietari dei database e i membri dei ruoli di database `db_ddladmin` o `db_owners` possono creare oggetti appartenenti ad altri utenti. Questi oggetti possono avere come destinazione gli oggetti di altri database, il che significa che se si abilita il concatenamento della proprietà tra database, è necessario considerare completamente attendibili questi utenti per i dati di tutti i database.  
  
- Gli utenti con l'autorizzazione CREATE DATABASE possono creare nuovi database e collegare database esistenti. Se il concatenamento della proprietà tra database è abilitato, questi utenti possono accedere ad oggetti di altri database per cui potrebbero non disporre di privilegi dai database appena creati o collegati.  
  
## <a name="enabling-cross-database-ownership-chaining"></a>Abilitazione del concatenamento della proprietà tra database  
 Il concatenamento della proprietà tra database deve essere abilitato solo negli ambienti in cui gli utenti con privilegi elevati possono essere considerati completamente attendibili. Questa funzionalità può essere configurata durante l'installazione per tutti i database o in modo selettivo per specifici database utilizzando i comandi Transact-SQL `sp_configure` e `ALTER DATABASE`.  
  
 Per configurare in modo selettivo questa funzionalità, usare `sp_configure` per disattivarla per il server. Usare quindi il comando ALTER DATABASE con SET DB_CHAINING ON per configurare il concatenamento della proprietà tra database solo per i database per cui è necessario.  
  
 Nell'esempio seguente si attiva il concatenamento della proprietà tra database per tutti i database:  
  
```  
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 Nell'esempio seguente si attiva il concatenamento della proprietà tra database per database specifici:  
  
```  
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a>SQL dinamico  
 Il concatenamento della proprietà tra database non funziona nei casi in cui vengono eseguite istruzioni SQL create in modo dinamico, a meno che nei due database non esistano gli stessi utenti. Per aggirare questo problema, in SQL Server è possibile creare una stored procedure che accede ai dati di un altro database e firmare la procedura con un certificato disponibile in entrambi i database. In questo modo si fornisce agli utenti l'accesso alle risorse del database usate dalla procedura senza concedere loro l'accesso o le autorizzazioni per il database.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le seguenti risorse.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Estensione della rappresentazione del Database tramite EXECUTE AS](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) e [opzione Cross DB Ownership Chaining](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).|Gli articoli descrivono come configurare il concatenamento di un'istanza di SQL Server della proprietà tra database.|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Cenni preliminari sulla sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Gestione delle autorizzazioni con stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [Scrittura dinamica sicura in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [Firma di stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
