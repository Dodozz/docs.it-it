---
title: Creazione di un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 0625d1005e6519b395ffd7ff0fb0c35583117875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623053"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="ab6c7-102">Creazione di un oggetto DataView</span><span class="sxs-lookup"><span data-stu-id="ab6c7-102">Creating a DataView</span></span>
<span data-ttu-id="ab6c7-103">Per creare un <xref:System.Data.DataView>, sono disponibili due modalità.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="ab6c7-104">È possibile usare la **DataView** costruttore, oppure è possibile creare un riferimento al <xref:System.Data.DataTable.DefaultView%2A> proprietà del <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="ab6c7-105">Il **DataView** costruttore può essere vuota oppure può accettare un **DataTable** come argomento singolo, o un **DataTable** insieme ai criteri di filtro, i criteri di ordinamento e una riga filtro relativo allo stato.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="ab6c7-106">Per altre informazioni sugli argomenti aggiuntivi disponibili per l'uso con il **DataView**, vedere [ordinamento e filtro dei dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span><span class="sxs-lookup"><span data-stu-id="ab6c7-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="ab6c7-107">Perché l'indice per una **DataView** viene compilato sia quando la **DataView** viene creato e quando uno del **Sort**, **RowFilter**, o  **RowStateFilter** vengono modificate le proprietà, si otterranno prestazioni ottimali da fornire qualsiasi tipo di ordinamento iniziale o criteri di filtro come argomenti del costruttore quando si crea il **DataView**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="ab6c7-108">Creazione di un **DataView** senza specificare criteri di filtro o ordinamento e impostando successivamente la **Sort**, **RowFilter**, o **RowStateFilter** le proprietà in un secondo momento fa sì che l'indice verrà compilato almeno due volte: una volta quando il **DataView** viene creato e nuovamente quando le proprietà di ordinamento o filtro vengono modificate.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="ab6c7-109">Si noti che se si crea una **DataView** usando il costruttore che non accetta alcun argomento, non sarà in grado di utilizzare il **DataView** fino a quando non è stato impostato il **tabella** proprietà .</span><span class="sxs-lookup"><span data-stu-id="ab6c7-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="ab6c7-110">Esempio di codice seguente viene illustrato come creare un **DataView** usando la **DataView** costruttore.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="ab6c7-111">Oggetto **RowFilter**, **Sort** colonna, e **DataViewRowState** vengono forniti con il **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="ab6c7-112">Esempio di codice seguente viene illustrato come ottenere un riferimento all'impostazione predefinita **DataView** di un **DataTable** utilizzando il **DefaultView** proprietà della tabella.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab6c7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab6c7-113">See also</span></span>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="ab6c7-114">DataView</span><span class="sxs-lookup"><span data-stu-id="ab6c7-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="ab6c7-115">Ordinamento e applicazione di filtri ai dati</span><span class="sxs-lookup"><span data-stu-id="ab6c7-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [<span data-ttu-id="ab6c7-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="ab6c7-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="ab6c7-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ab6c7-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
