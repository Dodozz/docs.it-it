---
title: Stili e modelli di ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 9c0edfd7ab4772eb9a1f5ecdd3db611fa36bf8d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971028"
---
# <a name="scrollviewer-styles-and-templates"></a>Stili e modelli di ScrollViewer
In questo argomento descrive gli stili e modelli per la <xref:System.Windows.Controls.ScrollViewer> controllo. È possibile modificare il valore predefinito <xref:System.Windows.Controls.ControlTemplate> per fornire al controllo un aspetto univoco. Per altre informazioni, vedere [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="scrollviewer-parts"></a>Parti del controllo ScrollViewer  
 La tabella seguente elenca le parti denominate di <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
|Parte|Tipo|Descrizione|  
|-|-|-|  
|PART_ScrollContentPresenter|<xref:System.Windows.Controls.ScrollContentPresenter>|Il segnaposto per il contenuto di <xref:System.Windows.Controls.ScrollViewer>.|  
|PART_HorizontalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere il contenuto in senso orizzontale.|  
|PART_VerticalScrollBar|<xref:System.Windows.Controls.Primitives.ScrollBar>|Il <xref:System.Windows.Controls.Primitives.ScrollBar> consente di scorrere verticalmente il contenuto.|  
  
## <a name="scrollviewer-states"></a>Stati del controllo ScrollViewer  
 La tabella seguente elenca gli stati visivi il <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
|Nome VisualState|Nome VisualStateGroup|Descrizione|  
|-|-|-|  
|Valido|ValidationStates|Il controllo Usa il <xref:System.Windows.Controls.Validation> classi e le <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `false`.|  
|InvalidFocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo ha lo stato attivo.|  
|InvalidUnfocused|ValidationStates|Il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata è `true` ha il controllo non è attivo.|  
  
## <a name="scrollviewer-controltemplate-example"></a>Esempio di ControlTemplate ScrollViewer  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.ControlTemplate> per il <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 L'esempio precedente usa una o più delle seguenti risorse.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Per l'esempio completo, vedere [Esempio di applicazione di stili con ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Stili e modelli di Control](control-styles-and-templates.md)
- [Personalizzazione dei controlli](control-customization.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Personalizzazione dell'aspetto di un controllo esistente mediante la creazione di un oggetto ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
