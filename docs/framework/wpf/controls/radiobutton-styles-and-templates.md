---
title: Stili e modelli di RadioButton
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: 58da02a3c6927e0457a16e354ac86724a783354b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661329"
---
# <a name="radiobutton-styles-and-templates"></a>Stili e modelli di RadioButton
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.RadioButton> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="radiobutton-parts"></a>Parti del controllo RadioButton  
 Il <xref:System.Windows.Controls.RadioButton> controllo non dispone di parti denominate.  
  
## <a name="radiobutton-states"></a>Stati di RadioButton  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.RadioButton> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|----------------------|---------------------------|-----------------|  
|Normale|CommonStates|Lo stato predefinito.|  
|MouseOver|CommonStates|Il puntatore del mouse è posizionato sul controllo.|  
|Premuto|CommonStates|Il controllo è premuto.|  
|Disabilitato|CommonStates|Il controllo è disabilitato.|  
|Con stato attivo|FocusStates|Il controllo ha lo stato attivo.|  
|Con stato non attivo|FocusStates|Il controllo non ha lo stato attivo.|  
|Selezionato con segno di spunta|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `true`.|  
|unchecked|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `false`.|  
|Indeterminato|CheckStates|<xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> viene `true`, e <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> è `null`.|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="radiobutton-controltemplate-example"></a>Esempio di ControlTemplate RadioButton  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.RadioButton> controllo.  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
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
