---
title: Esecuzione di query sulla raccolta DataRowView in un oggetto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
ms.openlocfilehash: 16091f90d700dd62df0870eaf74ad46c716785d3
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504626"
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a>Esecuzione di query sulla raccolta DataRowView in un oggetto DataView
L'oggetto <xref:System.Data.DataView> espone una raccolta enumerabile di oggetti <xref:System.Data.DataRowView>. <xref:System.Data.DataRowView> rappresenta una visualizzazione personalizzata di <xref:System.Data.DataRow> e visualizza una versione specifica di tale oggetto <xref:System.Data.DataRow> in un controllo. È possibile visualizzare un'unica versione di un oggetto <xref:System.Data.DataRow> tramite un controllo, ad esempio <xref:System.Windows.Forms.DataGridView>. È possibile accedere all'oggetto <xref:System.Data.DataRow> esposto da <xref:System.Data.DataRowView> tramite la proprietà <xref:System.Data.DataRowView.Row%2A> di <xref:System.Data.DataRowView>. Quando si visualizzano i valori tramite un oggetto <xref:System.Data.DataRowView>, la proprietà <xref:System.Data.DataView.RowStateFilter%2A> determina quale versione di riga dell'oggetto <xref:System.Data.DataRow> sottostante viene esposta. Per informazioni sull'accesso a diverse versioni di riga utilizzando un <xref:System.Data.DataRow>, vedere [stati e le versioni delle righe](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md). Poiché la raccolta di <xref:System.Data.DataRowView> gli oggetti esposti dal <xref:System.Data.DataView> è enumerabile, è possibile usare LINQ to DataSet per eseguire query su di esso.  
  
 Nell'esempio seguente viene eseguita una query sulla tabella `Product` per individuare i prodotti di colore rosso. Da tale query viene creata una tabella da cui viene creato un oggetto <xref:System.Data.DataView> e viene impostata la proprietà <xref:System.Data.DataView.RowStateFilter%2A> per filtrare le righe eliminate e modificate. Viene quindi usato l'oggetto <xref:System.Data.DataView> come origine in una query LINQ e gli oggetti <xref:System.Data.DataRowView> che sono stati modificati ed eliminati vengono associati a un controllo <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 Nell'esempio seguente viene creata una tabella di prodotti da una visualizzazione associata a un controllo <xref:System.Windows.Forms.DataGridView>. Viene eseguita una query sull'oggetto <xref:System.Data.DataView> per individuare i prodotti di colore rosso, quindi i risultati ordinati vengono associati a un controllo <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
