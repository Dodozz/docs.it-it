---
title: 'Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: fcb2014cc92a8a3e4afe7c3ed0365fd5947c70f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628266"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Procedura: Specificare la modalità di modifica per il controllo DataGridView di Windows Form
Per impostazione predefinita, gli utenti possono modificare il contenuto dell'oggetto corrente <xref:System.Windows.Forms.DataGridView> cella casella di testo digitando in esso o premere F2. In questo modo la cella in modalità di modifica se vengono soddisfatte tutte le condizioni seguenti:  
  
-   L'origine dati sottostante supporta la modifica.  
  
-   Il <xref:System.Windows.Forms.DataGridView> controllo è abilitato.  
  
-   Il <xref:System.Windows.Forms.DataGridView.EditMode%2A> valore della proprietà non è <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
-   Il `ReadOnly` delle proprietà della cella, riga, colonna e controllo sono tutti impostati su `false`.  
  
 In modalità di modifica, l'utente può modificare il valore di cella e premere INVIO per eseguire il commit della modifica oppure ESC per ripristinare la cella il valore originale.  
  
 È possibile configurare un <xref:System.Windows.Forms.DataGridView> controllare in modo che una cella passa alla modalità di modifica, non appena diventa la cella corrente. In questo caso il comportamento dei tasti ESC e invio è invariato, ma la cella rimane in modalità di modifica dopo che il valore è stato eseguito il commit o ripristinato. È anche possibile configurare il controllo in modo che le celle modalità di modifica solo quando gli utenti digitano nella cella o solo quando gli utenti premono F2. Infine, è possibile impedire le celle di entrare in modalità di modifica, ad eccezione di quando si chiama il <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> (metodo).  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Per modificare la modalità di modifica di un controllo DataGridView  
  
-   Impostare il <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> proprietà appropriata <xref:System.Windows.Forms.DataGridViewEditMode> enumerazione.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System> e <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
