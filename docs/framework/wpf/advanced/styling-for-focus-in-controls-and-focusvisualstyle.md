---
title: Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 745c2174c54ed072f91a6d5eb3b43d5385e96b90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172055"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] offre due meccanismi paralleli per modificare l'aspetto visivo di un controllo che riceve lo stato attivo della tastiera. Il primo meccanismo consiste nell'usare setter di proprietà per proprietà, ad esempio <xref:System.Windows.UIElement.IsKeyboardFocused%2A> entro lo stile o il modello che viene applicato al controllo. Il secondo consiste nel fornire uno stile separato come valore del <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà; la "dello stile di visualizzazione dello stato attivo" Crea un struttura ad albero visuale separato per uno strumento decorativo che viene disegnato sopra il controllo, anziché modificare la struttura ad albero visuale del controllo o altra interfaccia utente elemento sostituendola. Questo argomento descrive gli scenari appropriati a ogni meccanismo.  

<a name="Purpose"></a>   
## <a name="the-purpose-of-focus-visual-style"></a>Scopo dello stile di visualizzazione dello stato attivo  
 La funzionalità dello stile di visualizzazione dello stato attivo offre un "modello a oggetti" comune per introdurre un feedback utente visivo, basato sul passaggio tramite tastiera a un qualsiasi elemento dell'interfaccia utente. Questo è possibile senza bisogno di applicare un nuovo modello al controllo, né di conoscere la composizione specifica del modello.  
  
 Dal momento però che la funzionalità dello stile di visualizzazione dello stato attivo funziona a prescindere dai modelli di controllo, il feedback visivo che è possibile visualizzare per un controllo usando uno stile di visualizzazione dello stato attivo è necessariamente limitato. La funzionalità sovrappone una struttura ad albero visuale diversa (uno strumento decorativo visuale) sulla struttura ad albero visuale creata dal rendering di un controllo tramite il relativo modello. Si definisce questa struttura ad albero separato con uno stile che compila il <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> proprietà.  
  
<a name="Default"></a>   
## <a name="default-focus-visual-style-behavior"></a>Comportamento predefinito dello stile di visualizzazione dello stato attivo  
 Gli stili di visualizzazione dello stato attivo funzionano solo quando l'azione di impostazione dello stato attivo è stata iniziata dalla tastiera. Qualsiasi azione del mouse o modifica dello stato attivo a livello di codice disabilita la modalità degli stili di visualizzazione dello stato attivo. Per altre informazioni sulle differenze tra le modalità dello stato attivo, vedere [Cenni preliminari sullo stato attivo](focus-overview.md).  
  
 I temi dei controlli includono un comportamento predefinito dello stile di visualizzazione dello stato attivo che diventa lo stile di visualizzazione dello stato attivo per tutti i controlli del tema. Questo stile del tema viene identificato dal valore della chiave statica <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>. Quando si dichiara uno stile di visualizzazione dello stato attivo personalizzato a livello di applicazione, questo sostituisce il comportamento dello stile predefinito dei temi. In alternativa, se si definisce l'intero tema, è necessario usare questa stessa chiave per definire lo stile del comportamento predefinito per tutto il tema.  
  
 Nei temi, lo stile di visualizzazione dello stato attivo predefinito in genere è molto semplice. Di seguito è riportata un'approssimazione generica:  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>   
## <a name="when-to-use-focus-visual-styles"></a>Quando usare gli stili di visualizzazione dello stato attivo  
 Dal punto di vista concettuale, l'aspetto degli stili di visualizzazione dello stato attivo applicati ai controlli deve essere coerente da un controllo all'altro. Un modo per garantire la coerenza consiste nel modificare lo stile di visualizzazione dello stato attivo solo se si sta componendo un tema completo, in cui ogni controllo definito nel tema ottiene lo stesso stile di visualizzazione dello stato attivo o una variazione di uno stile visivamente coerente tra i vari controlli. In alternativa, si può usare lo stesso stile (o stili simili) per assegnare uno stile a ogni elemento della pagina o di un'interfaccia utente in grado di ricevere lo stato attivo tramite tastiera.  
  
 Impostazione <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> su stili del controllo singoli che non fanno parte di un tema è non l'utilizzo previsto dello stato attivo gli stili di visualizzazione. Un comportamento visivo incoerente tra controlli può infatti creare confusione nell'esperienza utente relativamente allo stato attivo. Se si stanno prendendo in considerazione comportamenti specifici del controllo per lo stato attivo della tastiera che non fanno deliberatamente coerenti all'interno di un tema, un approccio migliore consiste usare trigger negli stili per le proprietà dello stato di input singolo, ad esempio <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocused%2A>.  
  
 Gli stili di visualizzazione dello stato attivo funzionano esclusivamente per lo stato attivo da tastiera. Come tali, costituiscono un tipo di funzionalità di accessibilità. Se si vogliono apportare modifiche all'interfaccia utente per qualsiasi tipo di stato attivo, tramite mouse, tastiera o a livello di codice, è preferibile usare non gli stili di visualizzazione dello stato attivo, bensì setter e trigger all'interno degli stili oppure modelli che funzionino in base al valore delle proprietà generali dello stato attivo, ad esempio <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>   
## <a name="how-to-create-a-focus-visual-style"></a>Come creare uno stile di visualizzazione dello stato attivo  
 Lo stile creato per un stile di visualizzazione dello stato attivo deve sempre disporre le <xref:System.Windows.Style.TargetType%2A> di <xref:System.Windows.Controls.Control>. Lo stile deve essere costituito principalmente un <xref:System.Windows.Controls.ControlTemplate>. Non si specifica il tipo di destinazione in cui lo stile di visualizzazione dello stato attivo viene assegnato a per il tipo di <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Poiché il tipo di destinazione è sempre <xref:System.Windows.Controls.Control>, è necessario definire lo stile usando proprietà comuni a tutti i controlli (usando proprietà dell'oggetto di <xref:System.Windows.Controls.Control> classe e le relative classi base). È necessario creare un modello che funzioni correttamente come sovrapposizione a un elemento dell'interfaccia utente e che non nasconda le aree funzionali del controllo. In generale, questo vuol dire che il feedback visivo deve essere visualizzato all'esterno dei margini del controllo o sotto forma di effetti temporanei o non intrusivi, che non blocchino l'hit testing sul controllo a cui viene applicato lo stile di visualizzazione dello stato attivo. Le proprietà che è possibile usare in associazione a modello utili per determinare il ridimensionamento e posizionamento del modello di sovrapposizione includono <xref:System.Windows.FrameworkElement.ActualHeight%2A>, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, e <xref:System.Windows.Controls.Control.Padding%2A>.  
  
<a name="Alternatives"></a>   
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternative all'uso di uno stile di visualizzazione dello stato attivo  
 Per le situazioni in cui non è appropriato usare uno stile di visualizzazione dello stato attivo, perché si sta assegnando uno stile solo a singoli controlli o perché si vuole un controllo maggiore sul modello del controllo, sono disponibili molte altre proprietà e tecniche accessibili che creano un comportamento visivo in risposta alle modifiche apportate allo stato attivo.  
  
 Trigger, setter e setter di eventi sono illustrati in dettaglio in [Applicazione di stili e modelli](../controls/styling-and-templating.md). La gestione degli eventi indirizzati è illustrata in [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Se è interessati in stato attivo della tastiera, il <xref:System.Windows.UIElement.IsKeyboardFocused%2A> proprietà di dipendenza può essere utilizzata per una proprietà <xref:System.Windows.Trigger>. Un trigger di proprietà in uno stile o in un modello rappresenta una tecnica più appropriata per la definizione di un comportamento dello stato attivo della tastiera specifico per un singolo controllo, che potrebbe non corrispondere visivamente al comportamento dello stato attivo della tastiera di altri controlli.  
  
 Un'altra proprietà di dipendenza simile è <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>, che potrebbe essere appropriata se si vuole evidenziare visivamente che lo stato attivo è un punto qualsiasi all'interno di composizione o all'interno dell'area funzionale del controllo. Ad esempio, potrebbe inserire un <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> trigger in modo che un pannello che raggruppa diversi controlli viene visualizzato in modo diverso, anche se lo stato attivo da tastiera potrebbe essere più precisamente trovarsi in un singolo elemento all'interno di tale pannello.  
  
 È anche possibile usare gli eventi <xref:System.Windows.UIElement.GotKeyboardFocus> e <xref:System.Windows.UIElement.LostKeyboardFocus> (nonché i relativi equivalenti di anteprima). È possibile usare questi eventi come base per un <xref:System.Windows.EventSetter>, oppure è possibile scrivere gestori per gli eventi nel code-behind.  
  
### <a name="other-focus-properties"></a>Altre proprietà dello stato attivo  
 Se si desidera che tutte le possibili cause di modifica dello stato attivo per produrre un comportamento visivo, è consigliabile basare un setter o trigger la <xref:System.Windows.UIElement.IsFocused%2A> proprietà di dipendenza, o in alternativa nel <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus> eventi usati per un <xref:System.Windows.EventSetter>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica sullo stato attivo](focus-overview.md)
- [Cenni preliminari sull'input](input-overview.md)
