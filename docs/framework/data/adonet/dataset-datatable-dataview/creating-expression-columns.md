---
title: Creazione di colonne espressioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 6e19e4e7cc0ea92e9d93e45c2a50d009e46b78c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175500"
---
# <a name="creating-expression-columns"></a>Creazione di colonne espressioni
È possibile definire un'espressione per una colonna per consentire che questa contenga un valore calcolato sulla base di altri valori di colonna nella stessa riga o sulla base di valori di colonna di più righe della tabella. Per definire l'espressione da valutare, usare la proprietà <xref:System.Data.DataColumn.Expression%2A> della colonna di destinazione e la proprietà <xref:System.Data.DataColumn.ColumnName%2A> per fare riferimento ad altre colonne nell'espressione. La proprietà <xref:System.Data.DataColumn.DataType%2A> specificata per la colonna di espressioni deve essere adeguata per il valore restituito dall'espressione.  
  
 La tabella seguente indica diversi usi possibili delle colonne di espressioni in una tabella.  
  
|Tipo di espressione|Esempio|  
|---------------------|-------------|  
|Confronto|"Total >= 500"|  
|Calcolo|"UnitPrice * Quantity"|  
|Aggregazione|Sum(Price)|  
  
 È possibile impostare il **espressione** proprietà su un oggetto esistente **DataColumn** oggetto oppure è possibile includere la proprietà come terzo argomento passato al <xref:System.Data.DataColumn> costruttore, come illustrato nell'esempio seguente.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Le espressioni possono fare riferimento ad altre colonne di espressioni. Viene tuttavia generata un'eccezione se è presente un riferimento circolare, ovvero quando due espressioni fanno riferimento l'una all'altra. Per informazioni sulla scrittura di espressioni, vedere la <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
