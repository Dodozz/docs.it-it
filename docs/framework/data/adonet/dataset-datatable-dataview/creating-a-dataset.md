---
title: Creazione di un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879879"
---
# <a name="creating-a-dataset"></a>Creazione di un dataset
È possibile creare un'istanza di un tipo<xref:System.Data.DataSet> chiamando il costruttore <xref:System.Data.DataSet>. Facoltativamente, specificare un nome di argomento. Se non si specifica alcun nome per il tipo <xref:System.Data.DataSet>, verrà usato il nome "NewDataSet".  
  
 È inoltre possibile creare un nuovo tipo <xref:System.Data.DataSet> basato su un tipo <xref:System.Data.DataSet> esistente. Il nuovo tipo <xref:System.Data.DataSet> può essere una copia esatta del <xref:System.Data.DataSet> esistente; un duplicato del tipo <xref:System.Data.DataSet> in cui viene copiata la struttura relazionale o lo schema ma in cui non è presente alcun dato proveniente dal <xref:System.Data.DataSet> esistente; oppure un subset del tipo <xref:System.Data.DataSet>, contenente solo le righe modificate del <xref:System.Data.DataSet> esistente usando il metodo <xref:System.Data.DataSet.GetChanges%2A>. Per altre informazioni, vedere [copia di contenuti di DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).  
  
 Nell'esempio di codice seguente viene illustrata la creazione di un'istanza di un tipo <xref:System.Data.DataSet>.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>Vedere anche

- [Popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
