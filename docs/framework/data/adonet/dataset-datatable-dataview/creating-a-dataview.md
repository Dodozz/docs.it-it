---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096680"
---
# <a name="creating-a-dataview"></a>Creazione di un oggetto DataView
Per creare un <xref:System.Data.DataView>, sono disponibili due modalità. È possibile usare la **DataView** costruttore, oppure è possibile creare un riferimento al <xref:System.Data.DataTable.DefaultView%2A> proprietà del <xref:System.Data.DataTable>. Il **DataView** costruttore può essere vuota oppure può accettare un **DataTable** come argomento singolo, o un **DataTable** insieme ai criteri di filtro, i criteri di ordinamento e una riga filtro relativo allo stato. Per altre informazioni sugli argomenti aggiuntivi disponibili per l'uso con il **DataView**, vedere [ordinamento e filtro dei dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Perché l'indice per una **DataView** viene compilato sia quando la **DataView** viene creato e quando uno del **Sort**, **RowFilter**, o  **RowStateFilter** vengono modificate le proprietà, si otterranno prestazioni ottimali da fornire qualsiasi tipo di ordinamento iniziale o criteri di filtro come argomenti del costruttore quando si crea il **DataView**. Creazione di un **DataView** senza specificare criteri di filtro o ordinamento e impostando successivamente la **Sort**, **RowFilter**, o **RowStateFilter** le proprietà in un secondo momento fa sì che l'indice verrà compilato almeno due volte: una volta quando il **DataView** viene creato e nuovamente quando le proprietà di ordinamento o filtro vengono modificate.  
  
 Si noti che se si crea una **DataView** usando il costruttore che non accetta alcun argomento, non sarà in grado di utilizzare il **DataView** fino a quando non è stato impostato il **tabella** proprietà .  
  
 Esempio di codice seguente viene illustrato come creare un **DataView** usando la **DataView** costruttore. Oggetto **RowFilter**, **Sort** colonna, e **DataViewRowState** vengono forniti con il **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 Esempio di codice seguente viene illustrato come ottenere un riferimento all'impostazione predefinita **DataView** di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [Ordinamento e applicazione di filtri ai dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
