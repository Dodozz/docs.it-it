---
title: Generazione di dataset fortemente tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 2d3dc99d78ee9ceb3e8e1cac22fc5571cc1545ba
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504101"
---
# <a name="generating-strongly-typed-datasets"></a>Generazione di dataset fortemente tipizzati
Dato un XML Schema che è conforme allo XML Schema definition language (XSD) standard, è possibile generare una classe fortemente tipizzata <xref:System.Data.DataSet> utilizzando lo strumento XSD.exe fornito con Windows Software Development Kit (SDK).  
  
 (Per creare uno schema xsd dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> oppure [utilizzo di dataset in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 Il codice seguente illustra la sintassi per la generazione di un **set di dati** usando questo strumento.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 In questa sintassi, il `/d` direttiva richiede lo strumento per generare un **set di dati**e il `/l:` indica allo strumento del linguaggio da usare (ad esempio, c# o Visual Basic .NET). L'opzione facoltativa `/eld` direttiva specifica che è possibile usare LINQ to DataSet per eseguire query sul generato **set di dati.** Questa opzione viene usata quando si specifica anche l'opzione `/d`. Per altre informazioni, vedere [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). L'opzione facoltativa `/n:` direttiva richiede lo strumento per generare anche uno spazio dei nomi per il **set di dati** chiamato **XSDSchema**. L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere compilato e usato in un'applicazione ADO.NET. È possibile compilare il codice generato come libreria o modulo.  
  
 Nel codice seguente viene mostrata la sintassi per la compilazione del codice generato come libreria usando il compilatore C# (csc.exe).  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 La direttiva `/t:` consente di richiedere allo strumento la compilazione in una libreria e la direttiva `/r:` consente di specificare le librerie dipendenti necessarie per la compilazione. L'output del comando è costituito dal file XSDSchemaFileName.dll, che può essere passato al compilatore quando si compila un'applicazione ADO.NET con la direttiva `/r:`.  
  
 Nel codice seguente viene mostrata la sintassi usata per l'accesso allo spazio dei nomi passato a XSD.exe in un'applicazione ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 Esempio di codice seguente usa un oggetto tipizzato **set di dati** denominata **CustomerDataSet** per caricare un elenco di clienti il **Northwind** database. Una volta caricati i dati usando il **riempire** metodo, l'esempio scorre in ciclo ogni cliente nella **clienti** tabella usando l'oggetto tipizzato **CustomersRow** ( **DataRow**) oggetti. Ciò fornisce accesso diretto al **CustomerID** colonna, anziché tramite il **DataColumnCollection**.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 Di seguito viene riportato l'XML Schema usato per l'esempio.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Set di dati tipizzati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
