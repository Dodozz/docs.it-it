---
title: Esplorazione di oggetti DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 91db42acb0e09b8fc99b0ee710a60800d40938ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607271"
---
# <a name="navigating-datatables"></a>Esplorazione di oggetti DataTable
Il tipo <xref:System.Data.DataTableReader> presenta il contenuto di uno o più oggetti <xref:System.Data.DataTable> sotto forma di uno o più set di risultati forward-only di sola lettura.  
  
 Un tipo <xref:System.Data.DataTableReader> può contenere più set di risultati se viene creato tramite il metodo <xref:System.Data.DataSet.CreateDataReader%2A>. Quando è presente più di un set di risultati, il metodo <xref:System.Data.DataTableReader.NextResult%2A> sposta il cursore al set di risultati successivo. Questa proprietà è forward-only. Non è possibile tornare a un set di risultati precedente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il `TestConstructor` metodo vengono creati due <xref:System.Data.DataTable> istanze. Per illustrare questo costruttore per la <xref:System.Data.DataTableReader> (classe), il codice di esempio crea un nuovo **DataTableReader** basato su una matrice che contiene i due **DataTable**ed esegue un'operazione semplice, stampa il contenuto delle prime colonne alla finestra della console.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
