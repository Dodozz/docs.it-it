---
title: Scrittura del contenuto di dataset come dati XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: dae044a9d7802e858f1f24dd4aa0f1de8f6cba7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158951"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Scrittura del contenuto di dataset come dati XML
In ADO.NET è possibile scrivere una rappresentazione XML di un <xref:System.Data.DataSet>, con o senza schema. Se le informazioni relative allo schema sono incluse inline con il flusso o documento XML, tali informazioni verranno scritte usando il linguaggio XSD (XML Schema Definition Language). Nello schema sono contenute le definizioni delle tabelle del <xref:System.Data.DataSet>, oltre alle definizioni delle relazioni e dei vincoli.  
  
 Quando un <xref:System.Data.DataSet> viene scritto sotto forma di dati XML, le righe del <xref:System.Data.DataSet> vengono scritte usando le versioni correnti. È tuttavia possibile scrivere un <xref:System.Data.DataSet> in formato DiffGram, in modo da consentire l'inclusione sia dei valori correnti che dei valori originali delle righe.  
  
 La rappresentazione XML del <xref:System.Data.DataSet> possono essere scritti in un file, un flusso, un **XmlWriter**, o una stringa. Queste opzioni forniscono una notevole flessibilità per la modalità di trasporto della rappresentazione XML del <xref:System.Data.DataSet>. Per ottenere la rappresentazione XML del <xref:System.Data.DataSet> sotto forma di stringa, usare il **GetXml** metodo come illustrato nell'esempio seguente.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** restituisce la rappresentazione XML del <xref:System.Data.DataSet> senza informazioni sullo schema. Per scrivere le informazioni sullo schema di <xref:System.Data.DataSet> (come XML Schema) a una stringa, usare **GetXmlSchema**.  
  
 Per scrivere un <xref:System.Data.DataSet> in un file, flusso, o **XmlWriter**, usare i **WriteXml** (metodo). Il primo parametro passato a **WriteXml** costituisce la destinazione dell'output XML. Ad esempio, passare una stringa contenente un nome file, un **TextWriter** oggetto e così via. È possibile passare un secondo parametro facoltativo di un **XmlWriteMode** per specificare come deve essere scritto l'output XML.  
  
 La tabella seguente illustra le opzioni per la **XmlWriteMode**.  
  
|Opzione XmlWriteMode|Descrizione|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Scrive i contenuti correnti del <xref:System.Data.DataSet> sotto forma di dati XML, senza schema XML. Questa è l'impostazione predefinita.|  
|**WriteSchema**|Scrive il contenuto corrente dell'oggetto <xref:System.Data.DataSet> come dati XML con la struttura relazionale come XML Schema inline.|  
|**DiffGram**|Scrive l'intero oggetto <xref:System.Data.DataSet> come DiffGram, inclusi i valori originali e quelli correnti. Per altre informazioni, vedere [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 Quando si scrive una rappresentazione XML di un <xref:System.Data.DataSet> che contiene **DataRelation** oggetti, è probabile che si desideri il codice XML risultante siano presenti le righe figlio di ogni relazione annidata all'interno dei relativi elementi padre. A tale scopo, impostare il **Nested** proprietà delle **DataRelation** a **true** quando si aggiunge il **DataRelation** al <xref:System.Data.DataSet>. Per altre informazioni, vedere [annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 Di seguito sono riportati due esempi di scrittura della rappresentazione XML di un <xref:System.Data.DataSet> in un file. Nel primo esempio passa il nome del file per il codice XML risultante come una stringa a **WriteXml**. Nel secondo esempio passa un' **StreamWriter** oggetto.  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Mapping di colonne a elementi, attributi e testo XML  
 È possibile specificare come una colonna di una tabella è rappresentata in formato XML utilizzando il **ColumnMapping** proprietà delle **DataColumn** oggetto. La tabella seguente illustra i diversi **MappingType** i valori per il **ColumnMapping** proprietà di una colonna di tabella e il codice XML risultante.  
  
|Valore MappingType|Descrizione|  
|-----------------------|-----------------|  
|**Elemento**|Questa è l'impostazione predefinita. La colonna viene scritta sotto forma di elemento XML. ColumnName rappresenta il nome dell'elemento e i contenuti della colonna vengono scritti come testo dell'elemento. Ad esempio:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Attributo**|La colonna viene scritta sotto forma di attributo XML dell'elemento XML per la riga corrente. ColumnName rappresenta il nome dell'attributo e i contenuti della colonna vengono scritti sotto forma di valore dell'attributo. Ad esempio:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|I contenuti della colonna vengono scritti sotto forma di testo nell'elemento XML per la riga corrente. Ad esempio:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Si noti che **SimpleContent** non può essere impostata per una colonna di una tabella contenente **elemento** colonne o relazioni annidate.|  
|**Hidden**|La colonna non viene scritta nell'output XML.|  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [Annidamento di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [Scrittura di informazioni dello schema DataSet come XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
