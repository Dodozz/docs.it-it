---
title: 'Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 66fb814bbf0a40ccaa9339eb24dcc49332861deb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647665"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione
Questa procedura dettagliata illustra come usare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli di Windows Presentation Foundation (WPF).

 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:

-   Creare il progetto.

-   Creare il controllo WPF.

-   Ospitare i controlli WPF in un pannello di layout.

-   Allineare i controlli WPF mediante le guide di allineamento.

-   Ancorare e agganciare i controlli WPF.

> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   Visual Studio 2012.  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto Windows Forms Application in Visual Basic o Visual c# denominato `ArrangeElementHost`.  
  
## <a name="creating-the-wpf-control"></a>Creazione del controllo WPF  
 Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.  
  
#### <a name="to-create-wpf-controls"></a>Per creare controlli WPF  
  
1.  Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  In visualizzazione Progettazione verificare che `UserControl1` sia selezionato. Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.  
  
4.  Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.  
  
5.  Compilare il progetto.  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a>Hosting di controlli WPF in un pannello di layout  
 È possibile usare i controlli WPF nei pannelli di layout nello stesso modo in cui si usano gli altri controlli Windows Form.  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a>Per ospitare controlli WPF in un pannello di layout  
  
1.  Aprire `Form1` in Progettazione Windows Form.  
  
2.  Nel **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo nel form.  
  
3.  Nel <xref:System.Windows.Forms.TableLayoutPanel> pannello smart tag del controllo, seleziona **Rimuovi ultima riga**.  
  
4.  Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando una larghezza e un'altezza maggiori.  
  
5.  Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nella prima cella del <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
6.  Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'altra istanza nella seconda cella del <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
7.  Nel **struttura documento** finestra selezionare `tableLayoutPanel1`. Per altre informazioni, vedere [finestra Struttura documento](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Padding%2A> proprietà `10, 10, 10, 10`.  
  
     Entrambi i controlli <xref:System.Windows.Forms.Integration.ElementHost> vengono ridimensionati per essere adattati al nuovo layout.  
  
## <a name="using-snaplines-to-align-wpf-controls"></a>Allineamento dei controlli WPF mediante le guide di allineamento  
 Le guide di allineamento semplificano l'allineamento dei controlli su un form. È possibile usare le guide di allineamento anche per allineare i controlli WPF. Per altre informazioni, vedere [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a>Per usare le guide di allineamento per allineare i controlli WPF  
  
1.  Dal **casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form e posizionarla nello spazio sotto la <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost3`.  
  
2.  Tramite le guide di allineamento allineare il bordo sinistro di `elementHost3` al bordo sinistro del controllo <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Tramite le guide di allineamento ridimensionare `elementHost3` impostando la stessa larghezza del controllo <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Spostare `elementHost3` verso il controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene visualizzata una guida di allineamento centrale tra i due controlli.  
  
5.  Nel **delle proprietà** finestra, impostare il valore della proprietà Margin su `20, 20, 20, 20`.  
  
6.  Spostare `elementHost3` dal controllo <xref:System.Windows.Forms.TableLayoutPanel> finché non viene di nuovo visualizzata la guida di allineamento centrale. La guida di allineamento centrale indica ora un margine di 20.  
  
7.  Spostare `elementHost3` verso destra fino ad allineare il bordo sinistro a quello di `elementHost1`.  
  
8.  Modificare la larghezza di `elementHost3` finché il bordo destro non è allineato a quello destro di `elementHost2`.  
  
## <a name="anchoring-and-docking-wpf-controls"></a>Ancoraggio e aggancio di controlli WPF  
 Un controllo WPF incluso in un form è soggetto alle stesse regole di ancoraggio e aggancio degli altri controlli Windows Form.  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a>Per ancorare e agganciare i controlli WPF  
  
1.  Selezionare `elementHost1`.  
  
2.  Nel **le proprietà** impostare nella finestra di <xref:System.Windows.Forms.Control.Anchor%2A> proprietà **Top, Bottom, Left, Right**.  
  
3.  Ridimensionare il controllo <xref:System.Windows.Forms.TableLayoutPanel> impostando dimensioni superiori.  
  
     Il controllo `elementHost1` verrà ridimensionato fino ad occupare l'intera cella.  
  
4.  Selezionare `elementHost2`.  
  
5.  Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     Il controllo `elementHost2` verrà ridimensionato fino ad occupare l'intera cella.  
  
6.  Selezionare il controllo <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Top>.  
  
8.  Selezionare `elementHost3`.  
  
9. Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     Il controllo `elementHost3` verrà ridimensionato fino a occupare lo spazio rimanente sul form.  
  
10. Ridimensionare il form.  
  
     Tutti e tre i controlli <xref:System.Windows.Forms.Integration.ElementHost> verranno ridimensionati in maniera appropriata.  
  
     Per altre informazioni, vedere [Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
