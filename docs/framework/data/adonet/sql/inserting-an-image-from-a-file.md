---
title: Inserimento di un'immagine da un file
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: f2bc67b4130633fba3a6e42e2b6925fc09f835c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116230"
---
# <a name="inserting-an-image-from-a-file"></a>Inserimento di un'immagine da un file
È possibile scrivere un oggetto binario di grandi dimensioni (BLOB, Binary Large Object) in un database come dati binari o come dati di tipo carattere, a seconda del tipo di campo dell'origine dati. BLOB è un termine generico che si riferisce ai tipi di dati `text`, `ntext` e `image`, che in genere contengono documenti e immagini.  
  
 Per scrivere un valore BLOB al database, eseguire l'istruzione INSERT o UPDATE appropriata e passare il valore BLOB come un parametro di input (vedere [configurazione dei parametri e tipi di dati di parametro](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)). Se il BLOB è archiviato come testo, come nel caso di un campo `text` di SQL Server, sarà possibile passarlo come parametro di stringa. Se il BLOB è archiviato in formato binario, come nel caso di un campo `image` di SQL Server, sarà possibile passare una matrice di tipo `byte` come parametro binario.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente vengono aggiunte informazioni relative ai dipendenti nella tabella Employees del database Northwind. Una foto del dipendente viene letta da un file e aggiunta a un campo di tipo immagine della tabella, denominato Photo.  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di comandi per modificare i dati](../../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [Recupero di dati binari](../../../../../docs/framework/data/adonet/retrieving-binary-data.md)
- [Dati binari e con valori elevati SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [Mapping dei tipi di dati SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
