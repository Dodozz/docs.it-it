---
title: 'Procedura: Aggiungere descrizioni comandi a singole celle in un controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: baa6f79f2e0d454412992d9c951734a3437a96cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517643"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Procedura: Aggiungere descrizioni comandi a singole celle in un controllo DataGridView di Windows Form
Per impostazione predefinita, le descrizioni comandi consentono di visualizzare i valori di <xref:System.Windows.Forms.DataGridView> celle che sono troppo piccole per Mostra tutto il loro contenuto. È possibile sostituire questo comportamento, tuttavia, per impostare i valori di testo della descrizione comando per le singole celle. Ciò è utile per visualizzare informazioni aggiuntive agli utenti su una cella o per fornire agli utenti una descrizione alternativa del contenuto della cella. Ad esempio, se si dispone di una riga che vengono visualizzate le icone di stato, è possibile fornire spiegazioni di testo tramite le descrizioni comandi.  
  
 È anche possibile disabilitare la visualizzazione di descrizioni comandi a livello di cella impostando il <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> proprietà `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Per aggiungere una descrizione comandi a una cella  
  
-   Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   L'esempio presenta i requisiti seguenti:  
  
-   Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `Rating` per la visualizzazione dei valori di stringa di uno a quattro asterisco ("*") dei simboli. Il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento del controllo deve essere associato con il metodo del gestore eventi illustrato nell'esempio.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Quando si associa il <xref:System.Windows.Forms.DataGridView> il controllo a un'origine dati esterna o fornire la propria origine dati mediante l'implementazione della modalità virtuale, si potrebbero riscontrare problemi di prestazioni. Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, gestire le <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> eventi invece di impostare il <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà di più celle. Quando si gestisce questo evento, il recupero del valore di una cella <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà genera l'evento e restituisce il valore della <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> proprietà come specificato nel gestore eventi.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
