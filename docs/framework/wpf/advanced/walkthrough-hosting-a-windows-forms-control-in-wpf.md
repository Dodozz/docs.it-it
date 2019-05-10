---
title: 'Procedura dettagliata: Hosting di un controllo Windows Form in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: af5a0d58e789e609a25aa828493a3b0722cc83e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605461"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Procedura dettagliata: Hosting di un controllo Windows Form in WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre numerosi controlli con un insieme di funzionalità completo. Tuttavia, può a volte si desidera utilizzare [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagine. Ad esempio, potrebbe essere un investimento sostanziale nella esistente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli o si può avere un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che fornisce funzionalità univoche.

Questa procedura dettagliata viene illustrato come ospitare un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control per un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina tramite il codice.

Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [Hosting di controlli Windows Form in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="hosting-the-windows-forms-control"></a>Hosting del controllo Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Per ospitare il controllo MaskedTextBox

1. Creare un progetto di applicazione WPF denominato `HostingWfInWpf`.

2. Aggiungere riferimenti agli assembly indicati di seguito.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Aprire MainWindow. XAML nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

4. Nome di <xref:System.Windows.Controls.Grid> elemento `grid1`.

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. Nella visualizzazione progettazione o XAML, selezionare il <xref:System.Windows.Window> elemento.

6. Nella finestra Proprietà scegliere il **eventi** scheda.

7. Fare doppio clic il <xref:System.Windows.FrameworkElement.Loaded> evento.

8. Inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. Nella parte superiore del file, aggiungere quanto segue `Imports` o `using` istruzione.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Premere **F5** per compilare ed eseguire l'applicazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Procedura dettagliata: Hosting di controlli Windows Form in WPF tramite XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controlli Windows Form e controlli WPF equivalenti](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Esempio di hosting di un controllo Windows Forms in WPF](https://go.microsoft.com/fwlink/?LinkID=160057)
