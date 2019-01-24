---
title: 'Procedura: Ancorare i controlli in Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: f4a9d3bcf7f9db1634da2b2f06177c05061af28e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733545"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedura: Ancorare i controlli in Windows Form
È possibile ancorare i controlli ai bordi dei form o chiedere di riempire il contenitore del controllo (un form o un controllo contenitore). Ad esempio, Windows Explorer ancora relativi <xref:System.Windows.Forms.TreeView> controllo sul lato sinistro della finestra e la relativa <xref:System.Windows.Forms.ListView> controllo sul lato destro della finestra. Usare il <xref:System.Windows.Forms.Control.Dock%2A> proprietà per tutti i controlli Windows Form visibili definire la modalità di ancoraggio.  
  
> [!NOTE]
>  I controlli ancorati in ordine inverso.  
  
 Il <xref:System.Windows.Forms.Control.Dock%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Per ancorare un controllo  
  
1.  Selezionare il controllo che si desidera ancorare.  
  
2.  Nella finestra Proprietà, fare clic sulla freccia a destra del <xref:System.Windows.Forms.Control.Dock%2A> proprietà.  
  
     Viene visualizzato un editor che mostra una serie di finestre che rappresenta i bordi e il centro del form.  
  
3.  Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo. Per riempire il contenuto form del controllo o controllo contenitore, fare clic su casella al centro. Fare clic su **(nessuno)** per disabilitare l'ancoraggio.  
  
     Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.  
  
    > [!NOTE]
    >  I controlli ereditati devono essere `Protected` per poter essere ancorata. Per modificare il livello di accesso di un controllo, impostare il relativo **modificatore** proprietà nella finestra Proprietà.  
  
## <a name="see-also"></a>Vedere anche
- [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)
- [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Panoramica sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Procedura: Ancoraggio dei controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
