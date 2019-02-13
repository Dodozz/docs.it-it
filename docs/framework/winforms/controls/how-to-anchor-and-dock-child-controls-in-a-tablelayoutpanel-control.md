---
title: 'Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: cfa0d374bf08ab1ea1753ed46e3e87ca177343b6
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219854"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a>Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel
Il controllo <xref:System.Windows.Forms.TableLayoutPanel> supporta le proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> nei controlli figlio.  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a>Per allineare un controllo figlio in una cella TableLayoutPanel  
  
1.  Creare un controllo <xref:System.Windows.Forms.TableLayoutPanel> nel form.  
  
2.  Impostare il valore della <xref:System.Windows.Forms.TableLayoutPanel> del controllo <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> e <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> delle proprietà per **1**.  
  
3.  Creare un controllo <xref:System.Windows.Forms.Button> nel controllo <xref:System.Windows.Forms.TableLayoutPanel>. 
  <xref:System.Windows.Forms.Button> occupa l'angolo superiore sinistro della cella.  
  
4.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Left`. Il controllo <xref:System.Windows.Forms.Button> viene spostato per allinearlo al bordo sinistro della cella.  
  
    > [!NOTE]
    >  Questo comportamento è diverso dal comportamento di altri controlli contenitore. In altri controlli contenitore, il controllo figlio non viene spostato quando viene impostata la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e la distanza tra il controllo ancorato e i limiti del contenitore padre viene stabilita al momento dell’impostazione della proprietà <xref:System.Windows.Forms.Control.Anchor%2A>.  
  
5.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Left`. Il controllo <xref:System.Windows.Forms.Button> viene spostato in modo che occupi l'angolo superiore sinistro della cella.  
  
6.  Ripetere il passaggio 5 con un valore di `Top, Right` spostare il <xref:System.Windows.Forms.Button> controllo nell'angolo superiore destro della cella. Ripetere l'operazione con i valori di `Bottom, Left` e `Bottom, Right`.  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a>Per estendere un controllo figlio in una cella TableLayoutPanel  
  
1.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Left, Right`. Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato in modo da estendersi per tutta la cella.  
  
    > [!NOTE]
    >  Questo comportamento è diverso dal comportamento di altri controlli contenitore. In altri controlli contenitore, il controllo figlio non viene ridimensionato quando la <xref:System.Windows.Forms.Control.Anchor%2A> è impostata su `Left, Right` o `Top, Bottom`.  
  
2.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Bottom`. Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato in modo da estendersi dalla parte superiore a quella inferiore della cella.  
  
3.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `Top, Bottom, Left, Right`. Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per riempire la cella.  
  
4.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.Control.Anchor%2A> , su `None`. Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato e centrato nella cella.  
  
5.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Control.Dock%2A>, su <xref:System.Windows.Forms.DockStyle.Left>. Il controllo <xref:System.Windows.Forms.Button> viene spostato per allinearlo al bordo sinistro della cella. Il controllo <xref:System.Windows.Forms.Button> conserva la larghezza, ma l'altezza viene ridimensionata per riempire la cella in verticale.  
  
    > [!NOTE]
    >  È lo stesso comportamento che si verifica in altri controlli contenitore.  
  
6.  Modificare il valore della proprietà del controllo <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.Control.Dock%2A>, su <xref:System.Windows.Forms.DockStyle.Fill>. Il controllo <xref:System.Windows.Forms.Button> viene ridimensionato per riempire la cella.  
  
## <a name="example"></a>Esempio  
 La figura seguente mostra cinque pulsanti ancorati in cinque celle <xref:System.Windows.Forms.TableLayoutPanel> separate.  
  
 ![Ancoraggio TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")  
  
 La figura seguente mostra quattro pulsanti ancorati agli angoli di quattro celle <xref:System.Windows.Forms.TableLayoutPanel> separate.  
  
 ![Ancoraggio TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")  
  
 La figura seguente mostra tre pulsanti estesi mediante ancoraggio in tre celle <xref:System.Windows.Forms.TableLayoutPanel> separate.  
  
 ![Ancoraggio TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")  
  
 L'esempio di codice seguente mostra tutte le combinazioni dei valori della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> per un controllo <xref:System.Windows.Forms.Button> in un controllo <xref:System.Windows.Forms.TableLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
