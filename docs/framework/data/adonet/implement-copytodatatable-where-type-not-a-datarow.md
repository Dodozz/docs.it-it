---
title: 'Procedura: Implementare CopyToDataTable<T> in cui il tipo generico T non è un oggetto DataRow'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b27b52cf-6172-485f-a75c-70ff9c5a2bd4
ms.openlocfilehash: 120b4bf22e310bee73ba006cfe5a060d0ecd9d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667015"
---
# <a name="how-to-implement-copytodatatablet-where-the-generic-type-t-is-not-a-datarow"></a>Procedura: Implementare CopyToDataTable\<T > in cui il tipo generico T non è un DataRow
L'oggetto <xref:System.Data.DataTable> viene spesso usato per l'associazione dati. Il metodo <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> copia i dati dei risultati di una query in un oggetto <xref:System.Data.DataTable> che può essere quindi usato per il data binding. I metodi <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>, tuttavia, funzionano solo su un'origine <xref:System.Collections.Generic.IEnumerable%601> in cui il parametro generico `T` è di tipo <xref:System.Data.DataRow>. Sebbene sia utile, questa funzionalità non consente di creare tabelle da una sequenza di tipi scalari, da query che proiettano tipo anonimi o da query che eseguono join di tabelle.  
  
 In questo argomento viene descritto come implementare due metodi di estensione `CopyToDataTable<T>` personalizzati che accettano un parametro generico `T` di un tipo diverso da <xref:System.Data.DataRow>. La logica per creare un oggetto <xref:System.Data.DataTable> da un'origine <xref:System.Collections.Generic.IEnumerable%601> è contenuto nella classe `ObjectShredder<T>`, di cui viene eseguito il wrapping in due metodi di estensione `CopyToDataTable<T>` di overload. Il metodo `Shred` della classe `ObjectShredder<T>` restituisce l'oggetto <xref:System.Data.DataTable> compilato e accetta tre parametri di input: un'origine <xref:System.Collections.Generic.IEnumerable%601>, un oggetto <xref:System.Data.DataTable> e un'enumerazione <xref:System.Data.LoadOption>. Lo schema iniziale dell'oggetto <xref:System.Data.DataTable> restituito è basato sullo schema del tipo `T`. Se viene fornita una tabella esistente come input, lo schema deve essere coerente con lo schema del tipo `T`. Tutte le proprietà e i campi pubblici del tipo `T` vengono convertiti in <xref:System.Data.DataColumn> nella tabella restituita. Se la sequenza di origine contiene un tipo derivato da `T`, lo schema della tabella restituita viene espanso per includere eventuali proprietà o campi pubblici aggiuntivi.  
  
 Per esempi di uso dei metodi `CopyToDataTable<T>` personalizzati, vedere [Creazione di un oggetto DataTable da una query](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md).  
  
### <a name="to-implement-the-custom-copytodatatablet-methods-in-your-application"></a>Per implementare i metodi CopyToDataTable\<T> personalizzati nell'applicazione  
  
1. Implementare la classe `ObjectShredder<T>` per creare un oggetto <xref:System.Data.DataTable> da un'origine <xref:System.Collections.Generic.IEnumerable%601>:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#objectshredderclass)]
     [!code-vb[DP Custom CopyToDataTable Examples#ObjectShredderClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#objectshredderclass)]  

    L'esempio precedente presuppone che le proprietà di `DataColumn` non abbiano tipi nullable. Per gestire le proprietà con tipi nullable, usare il codice seguente:

    ```csharp
    DataColumn dc = table.Columns.Contains(p.Name) ? table.Columns[p.Name] : table.Columns.Add(p.Name, Nullable.GetUnderlyingType(p.PropertyType) ?? p.PropertyType);
    ```

2. Implementare i metodi di estensione `CopyToDataTable<T>` personalizzati in una classe:  
  
     [!code-csharp[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#customcopytodatatablemethods)]
     [!code-vb[DP Custom CopyToDataTable Examples#CustomCopyToDataTableMethods](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#customcopytodatatablemethods)]  
  
3. Aggiungere la classe `ObjectShredder<T>` e i metodi di estensione `CopyToDataTable<T>` all'applicazione.  
  
```vb  
Module Module1  
    Sub Main()  
        ' Your application code using CopyToDataTable<T>.  
    End Sub  
End Module  
  
Public Module CustomLINQtoDataSetMethods  
…  
End Module  
  
Public Class ObjectShredder(Of T)  
…  
End Class
```
  
```csharp
class Program  
{  
    static void Main(string[] args)  
    {  
        // Your application code using CopyToDataTable<T>.  
    }  
}  
public static class CustomLINQtoDataSetMethods  
{  
…  
}  
public class ObjectShredder<T>  
{  
…  
}  
```
  
## <a name="see-also"></a>Vedere anche

- [Creazione di un oggetto DataTable da una query](../../../../docs/framework/data/adonet/creating-a-datatable-from-a-query-linq-to-dataset.md)
- [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
