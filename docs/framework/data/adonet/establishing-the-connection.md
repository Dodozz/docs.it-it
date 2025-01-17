---
title: Stabilire una connessione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: 50cf5011376576d371dba558a602187201395bd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599596"
---
# <a name="establishing-the-connection"></a>Stabilire una connessione
Per eseguire la connessione a Microsoft SQL Server, usare l'oggetto <xref:System.Data.SqlClient.SqlConnection> del provider di dati .NET Framework per SQL Server. Per eseguire la connessione a un'origine dati OLE DB, usare l'oggetto <xref:System.Data.OleDb.OleDbConnection> del provider di dati .NET Framework per OLE DB. Per eseguire la connessione a un'origine dati ODBC, usare l'oggetto <xref:System.Data.Odbc.OdbcConnection> del provider di dati .NET Framework per ODBC. Per eseguire la connessione a un'origine dati Oracle, usare l'oggetto <xref:System.Data.OracleClient.OracleConnection> del provider di dati .NET Framework per Oracle. Per l'archiviazione sicura e recupero delle stringhe di connessione, vedere [protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## <a name="closing-connections"></a>Disconnessione  
 Al termine dell'utilizzo, chiudere sempre la connessione in modo che possa essere restituita al pool. Il blocco `Using` in Visual Basic o C# elimina automaticamente la connessione quando il codice esce dal blocco, anche in caso di eccezione non gestita. Visualizzare [istruzione using](~/docs/csharp/language-reference/keywords/using-statement.md) e [istruzione Using](~/docs/visual-basic/language-reference/statements/using-statement.md) per altre informazioni.  
  
 È anche possibile usare il metodo `Close` o `Dispose` dell'oggetto connessione del provider in uso. Le connessioni che non vengono chiuse in modo esplicito potrebbero non essere aggiunte o restituite al pool. Ad esempio, una connessione che esce dall'ambito ma non viene chiusa in modo esplicito verrà restituita al pool di connessioni solo se è stata raggiunta la dimensione massima del pool e la connessione è ancora valida. Per altre informazioni, vedere [OLE DB, ODBC e Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).  
  
> [!NOTE]
>  Non chiamare `Close` o `Dispose` in un **connessione**, una **DataReader**, o qualsiasi altro oggetto gestito nel `Finalize` metodo della classe. Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente. Se nella classe non sono presenti risorse non gestite, non includere un metodo `Finalize` nella relativa definizione della classe. Per altre informazioni, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).  
  
> [!NOTE]
>  Nel server non vengono generati eventi di accesso e di disconnessione quando una connessione viene recuperata dal o restituita al pool di connessioni, in quanto la connessione non viene effettivamente chiusa quando viene restituita al pool di connessioni. Per altre informazioni, vedere [Pool di connessioni SQL Server (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## <a name="connecting-to-sql-server"></a>Connessione a SQL Server  
 Il formato della stringa di connessione supportato dal provider di dati .NET Framework per SQL Server è simile al formato della stringa di connessione OLE DB (ADO). Per informazioni sui nomi e sui valori validi del formato della stringa, vedere la proprietà <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>. È anche possibile usare la classe <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per creare stringhe di connessione sintatticamente valide in fase di esecuzione. Per altre informazioni, vedere [Compilatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
 Nel codice di esempio seguente viene descritta la procedura di creazione e di apertura di una connessione a un database SQL Server.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### <a name="integrated-security-and-aspnet"></a>Sicurezza integrata e ASP.NET  
 La sicurezza integrata di SQL Server (connessioni trusted) consente di proteggere la connessione a SQL Server, poiché non espone l'identificatore utente e la password nella stringa di connessione ed è il metodo consigliato per l'autenticazione di una connessione. La sicurezza integrata usa l'identità di sicurezza corrente, o token, del processo in esecuzione. Per le applicazioni desktop, tale identità corrisponde solitamente all'identità dell'utente attualmente connesso.  
  
 L'identità di sicurezza delle applicazioni ASP.NET può essere impostata su diverse opzioni. Per comprendere meglio l'identità di sicurezza che un'applicazione ASP.NET usa quando ci si connette a SQL Server, vedere [rappresentazione ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [autenticazione ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100)), e [come: La sicurezza integrata di accesso SQL Server tramite Windows](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100)).  
  
## <a name="connecting-to-an-ole-db-data-source"></a>Connessione a un'origine dati OLE DB  
 Il Provider di dati .NET Framework per OLE DB fornisce la connettività a origini dati esposte tramite OLE DB (tramite SQLOLEDB, il Provider OLE DB per SQL Server), usando il **OleDbConnection** oggetto.  
  
 Per il provider di dati .NET Framework per OLE DB, il formato della stringa di connessione è identico a quello usato in ADO, con le eccezioni seguenti:  
  
- Il **Provider** parola chiave è obbligatoria.  
  
- Il **URL**, **Provider remoto**, e **Server remoto** parole chiave non sono supportate.  
  
 Per altre informazioni sulle stringhe di connessione OLE DB, vedere l'argomento relativo a <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>. È anche possibile usare <xref:System.Data.OleDb.OleDbConnectionStringBuilder> per creare stringhe di connessione in fase di esecuzione.  
  
> [!NOTE]
>  Il **OleDbConnection** objekt nepodporuje impostazione o recupero di proprietà dinamiche specifiche di un provider OLE DB. Sono supportate esclusivamente le proprietà che possono essere passate nella stringa di connessione per il provider OLE DB.  
  
 Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati OLE DB.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =   
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="do-not-use-universal-data-link-files"></a>Non usare file collegamento dati universali (UDL, Universal Data Link)  
 È possibile fornire informazioni di connessione per un **OleDbConnection** in un file Universal Data Link (UDL); tuttavia è consigliabile evitare questa operazione. I file UDL non sono crittografati, pertanto espongono le informazioni nella stringa di connessione come testo non crittografato. Poiché per l'applicazione si tratta di una risorsa esterna basata su file, un file UDL non può essere protetto tramite .NET Framework.  
  
## <a name="connecting-to-an-odbc-data-source"></a>Connessione a un'origine dati ODBC  
 Il Provider di dati .NET Framework per ODBC offre connettività a origini dati esposte tramite ODBC mediante il **OdbcConnection** oggetto.  
  
 Il formato della stringa di connessione da usare con il provider di dati .NET Framework per ODBC è molto simile a quello della stringa di connessione ODBC. È anche possibile specificare il nome di un'origine dati (DSN, Data Source Name) ODBC. Per altre informazioni sul **OdbcConnection** , vedere il <xref:System.Data.Odbc.OdbcConnection>.  
  
 Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati ODBC.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =   
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="connecting-to-an-oracle-data-source"></a>Connessione a un'origine dati Oracle  
 Il Provider di dati .NET Framework per Oracle fornisce la connettività alle origini dati Oracle tramite il **OracleConnection** oggetto.  
  
 Il formato della stringa di connessione da usare con il provider di dati .NET Framework per Oracle è molto simile a quello della stringa di connessione del provider OLE DB per Oracle (MSDAORA). Per altre informazioni sul **OracleConnection**, vedere il <xref:System.Data.OracleClient.OracleConnection>.  
  
 Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati Oracle.  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =   
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Connessione a un'origine dati](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Stringhe di connessione](../../../../docs/framework/data/adonet/connection-strings.md)
- [Pool di connessioni OLE DB, ODBC e Oracle](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
