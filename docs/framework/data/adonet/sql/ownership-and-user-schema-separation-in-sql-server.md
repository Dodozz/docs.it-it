---
title: Proprietà e separazione tra schemi e utenti in SQL Server
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: 2702f56e8b3b339487ffacf7bc1ceb077d4d8b30
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645725"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a>Proprietà e separazione tra schemi e utenti in SQL Server
Uno dei concetti principali in merito alla sicurezza di SQL Server è che i proprietari di oggetti dispongono di autorizzazioni irrevocabili per amministrarli. Non è possibile rimuovere privilegi dal proprietario di un oggetto, né rilasciare utenti da un database che contiene oggetti di cui sono proprietari.  
  
## <a name="user-schema-separation"></a>Distinzione tra utente e schema  
 La distinzione tra utente e schema offre una maggiore flessibilità nella gestione delle autorizzazioni per gli oggetti di database. Oggetto *schema* è un contenitore denominato per gli oggetti di database, che consente di raggruppare gli oggetti in spazi dei nomi separato. Ad esempio, il database di esempio AdventureWorks contiene gli schemi per Production, Sales e HumanResources.  
  
 Usando la sintassi di denominazione in quattro parti per fare riferimento agli oggetti viene specificato il nome dello schema.  
  
```  
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a>Proprietari e autorizzazioni per gli schemi  
 Gli schemi possono essere di proprietà di qualsiasi entità di database e una singola entità può essere proprietaria di più schemi. È possibile applicare regole di sicurezza a un schema, che vengono ereditate da tutti gli oggetti al suo interno. Le autorizzazioni di accesso configurate per uno schema vengono automaticamente applicate quando vengono aggiunti nuovi oggetti. Agli utenti è possibile assegnare uno schema predefinito e più utenti di database possono condividere lo stesso schema.  
  
 Per impostazione predefinita, gli oggetti creati dagli sviluppatori in uno schema appartengono all'entità di sicurezza proprietaria dello schema, non allo sviluppatore. La proprietà degli oggetti può essere trasferita con l'istruzione Transact-SQL ALTER AUTHORIZATION. Uno schema può anche contenere oggetti che appartengono a utenti diversi e con autorizzazioni più granulari di quelle assegnate allo schema, anche se questa soluzione non è consigliata perché aumenta la complessità della gestione delle autorizzazioni. Gli oggetti possono essere spostati tra schemi e la proprietà dello schema può essere trasferita tra entità. Gli utenti del database possono essere rilasciati senza influire sugli schemi.  
  
### <a name="built-in-schemas"></a>Schemi predefiniti  
 In SQL Server sono disponibili dieci schemi predefiniti con gli stessi nomi degli utenti e dei ruoli incorporati del database. Vengono forniti principalmente per la compatibilità con le versioni precedenti. È possibile rilasciare gli schemi con gli stessi nomi dei ruoli predefiniti del database, se non sono necessari. Non è possibile eliminare i seguenti schemi:  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 Se questi schemi vengono eliminati dal database modello, non saranno presenti nei nuovi database.  
  
> [!NOTE]
>  Gli schemi `sys` e `INFORMATION_SCHEMA` sono riservati per gli oggetti di sistema. Non è possibile creare oggetti in questi schemi e non è possibile rilasciarli.  
  
#### <a name="the-dbo-schema"></a>Schema dbo  
 Lo schema `dbo` è quello predefinito per i nuovi database creati. Lo schema `dbo` è di proprietà dell'account utente `dbo`. Per impostazione predefinita, gli utenti creati con l'istruzione Transact-SQL CREATE USER hanno `dbo` come schema predefinito.  
  
 Gli utenti cui viene assegnato lo schema `dbo` non ereditano le autorizzazioni dell'account utente `dbo`. Gli utenti non ereditano autorizzazioni da uno schema. Le autorizzazioni di uno schema vengono ereditate dagli oggetti di database contenuti nello schema.  
  
> [!NOTE]
>  Quando agli oggetti di database viene fatto riferimento con un nome a una parte, in SQL Server viene innanzitutto esaminato lo schema predefinito dell'utente. Se l'oggetto non viene trovato, viene esaminato lo schema `dbo`. Se l'oggetto non si trova nello schema `dbo`, viene restituito un errore.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni sulla proprietà degli oggetti e sugli schemi, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Separazione Schema-utente](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))|Vengono descritte le modifiche introdotte dalla distinzione tra utente e schema, tra cui il nuovo comportamento, l'impatto sulla proprietà, le visualizzazioni del catalogo e le autorizzazioni.|  
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [Autenticazione in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)
- [Ruoli server e database in SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)
- [Autorizzazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
