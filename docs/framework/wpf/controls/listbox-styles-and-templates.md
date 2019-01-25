---
title: Stili e modelli di ListBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: 552df5df6bdf8d9cdd8241c3e68cae671a24c6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577763"
---
# <a name="listbox-styles-and-templates"></a>Stili e modelli di ListBox
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ListBox> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="listbox-parts"></a>Parti di ListBox  
 Il <xref:System.Windows.Controls.ListBox> controllo non dispone di parti denominate.  
  
 Quando si crea una <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.ListBox>, il modello potrebbe contenere un' <xref:System.Windows.Controls.ItemsPresenter> all'interno di un <xref:System.Windows.Controls.ScrollViewer>. (Il <xref:System.Windows.Controls.ItemsPresenter> Visualizza ogni elemento nel <xref:System.Windows.Controls.ListBox>; i <xref:System.Windows.Controls.ScrollViewer> consente lo scorrimento all'interno del controllo).  Se il <xref:System.Windows.Controls.ItemsPresenter> non è il figlio diretto del <xref:System.Windows.Controls.ScrollViewer>, è necessario dare il <xref:System.Windows.Controls.ItemsPresenter> il nome, `ItemsPresenter`.  
  
## <a name="listbox-states"></a>Stati di ListBox  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ListBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo è valido.|  
|InvalidFocused|ValidationStates|Il controllo non è valido e ha uno stato attivo.|  
|InvalidUnfocused|ValidationStates|Il controllo non è valido e non ha uno stato attivo.|  
  
## <a name="listboxitem-parts"></a>Parti di ListBoxItem  
 Il <xref:System.Windows.Controls.ListBoxItem> controllo non dispone di parti denominate.  
  
## <a name="listboxitem-states"></a>Stati di ListBoxItem  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ListBox> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Disabilitato|CommonStates|L'elemento è disabilitato.|  
|Con stato attivo|FocusStates|L'elemento ha uno stato attivo.|  
|Con stato non attivo|FocusStates|L'elemento non ha uno stato attivo.|  
|Deselezionato|SelectionStates|L'elemento non è selezionato.|  
|Selezionato|SelectionStates|L'elemento è attualmente selezionato.|  
|SelectedUnfocused|SelectionStates|L'elemento è selezionato, ma non ha uno stato attivo.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="listbox-controltemplate-example"></a>Esempio di ControlTemplate ListBox  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.ListBoxItem> controlli.  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [Personalizzazione dei controlli](../../../../docs/framework/wpf/controls/control-customization.md)
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
