---
title: Automazione interfaccia utente e Microsoft Active Accessibility
ms.date: 03/30/2017
helpviewer_keywords:
- Active Accessibility
- UI Automation, Active Accessibility compared to
- UI Automation, Microsoft Active Accessibility
- Active Accessibility, UI Automation compared to
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
ms.openlocfilehash: 29a6b897115c5f2f3ae8d7e4ec708be59dc0d85b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033215"
---
# <a name="ui-automation-and-microsoft-active-accessibility"></a>Automazione interfaccia utente e Microsoft Active Accessibility
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] è la soluzione usata in precedenza per rendere accessibili le applicazioni. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] è il nuovo modello di accessibilità per [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] , destinato a rispondere ai requisiti di prodotti di assistive technology e strumenti di test automatizzati. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] offre numerosi miglioramenti rispetto a [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
 Questo argomento descrive le principali funzionalità di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e illustra le differenze tra queste funzionalità e quelle di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)].  
  
<a name="Programming_Languages_compare"></a>   
## <a name="programming-languages"></a>Linguaggi di programmazione  
<[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] basa il [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] con il supporto per le interfacce duali ed è pertanto programmabile in C/C++, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)]e linguaggi di scripting. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (inclusa la libreria di provider lato client per i controlli standard) viene scritto in codice gestito e le applicazioni client di automazione interfaccia utente vengono programmate più facilmente utilizzando c# o Visual Basic .NET. I provider di automazione interfaccia utente, che corrispondono a implementazioni di interfaccia, possono essere scritti in codice gestito o in C/C++.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## <a name="support-in-windows-presentation-foundation"></a>Supporto in Windows Presentation Foundation  
 Windows Presentation Foundation (WPF) è il nuovo modello per la creazione di interfacce utente. Gli elementi[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] non contengono supporto nativo per [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]; tuttavia, supportano [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], che include il supporto del bridging per i client [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] . Solo i client scritti specificamente per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] possono trarre il massimo vantaggio dalle funzionalità di accessibilità di [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], ad esempio il supporto completo per il testo.  
  
<a name="Servers_and_Clients_compare"></a>   
## <a name="servers-and-clients"></a>Server e client  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]i server e i client comunicano direttamente, principalmente tramite l'implementazione del server di `IAccessible`.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]tra il server (denominato provider) e il client è disponibile un servizio di base che effettua chiamate alle interfacce implementate dai provider e fornisce servizi aggiuntivi, ad esempio la generazione di identificatori di runtime univoci per gli elementi. Le applicazioni client usano funzioni di libreria per chiamare il servizio di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 I provider di automazione interfaccia utente possono fornire informazioni ai client [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] , mentre i server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] possono fornire informazioni alle applicazioni client di automazione interfaccia utente. Tuttavia, poiché [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] non espone la stessa quantità di informazioni di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], i due modelli non sono completamente compatibili.  
  
<a name="UI_Elements_compare"></a>   
## <a name="ui-elements"></a>Elementi dell'interfaccia utente  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] presenta gli elementi dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] come interfaccia `IAccessible` o come identificatore di elemento figlio. È difficile confrontare due puntatori `IAccessible` per determinare se fanno riferimento allo stesso elemento.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]ogni elemento è rappresentato come oggetto <xref:System.Windows.Automation.AutomationElement> . Il confronto viene eseguito usando l'operatore di uguaglianza o il metodo <xref:System.Windows.Automation.AutomationElement.Equals%2A> ed entrambi confrontano gli identificatori di runtime univoci degli elementi.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## <a name="tree-views-and-navigation"></a>Visualizzazioni struttura ad albero e spostamenti  
 Gli elementi dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] possono essere visualizzati come una struttura ad albero, con il desktop che funge da radice, le finestre delle applicazioni da elementi figlio diretti e gli elementi all'interno delle applicazioni da ulteriori discendenti.  
  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]molti elementi di automazione irrilevanti per gli utenti finali vengono esposti nella struttura ad albero. Le applicazioni client devono esaminare tutti gli elementi per determinare quali sono significativi.  
  
 Le applicazioni client di automazione interfaccia utente vedono l' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] tramite una visualizzazione filtrata, che contiene solo elementi di interesse, ossia quelli che forniscono informazioni all'utente o consentono l'interazione. Sono disponibili visualizzazioni predefinite di soli elementi controllo e di soli elementi contenuto; inoltre, le applicazioni possono definite visualizzazioni personalizzate. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] semplifica l'attività di descrizione dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] all'utente e l'interazione dell'utente con l'applicazione.  
  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]lo spostamento tra elementi è spaziale (ad esempio lo spostamento all'elemento che si trova a sinistra dello schermo), logico (ad esempio lo spostamento alla voce di menu successiva o all'elemento successivo nell'ordine di tabulazione in una finestra di dialogo) o gerarchico (ad esempio lo spostamento del primo elemento figlio in un contenitore o dall'elemento figlio all'elemento padre). Lo spostamento gerarchico è complicato dal fatto che gli elementi figlio non sono sempre oggetti che implementano `IAccessible`.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]tutti gli elementi dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] sono oggetti <xref:System.Windows.Automation.AutomationElement> che supportano la stessa funzionalità di base. Dal punto di vista del provider, si tratta di oggetti che implementano un'interfaccia ereditata da <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>. Lo spostamento è prevalentemente gerarchico: dagli elementi padre agli elementi figlio e da un elemento di pari livello al successivo. Lo spostamento tra elementi di pari livello include un elemento logico, in quanto può seguire l'ordine di tabulazione. È possibile spostarsi da qualsiasi punto iniziale, usando qualsiasi visualizzazione filtrata della struttura ad albero, tramite la classe <xref:System.Windows.Automation.TreeWalker>. È inoltre possibile spostarsi su determinati elementi figlio o discendenti tramite <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> e <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; ad esempio, è estremamente facile recuperare tutti gli elementi di una finestra di dialogo che supportano un pattern di controllo specificato.  
  
 Lo spostamento in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] è più coerente rispetto a [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Alcuni elementi, ad esempio elenchi a discesa e finestre popup, vengono visualizzati due volte nella struttura ad albero di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] , quindi lo spostamento da questi elementi può generare risultati imprevisti. È di fatto impossibile implementare correttamente [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] per un controllo Rebar. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] consente l'assegnazione di nuovi elementi padre e il riposizionamento, pertanto un elemento può essere posizionato in qualsiasi punto dell'albero nonostante la gerarchia imposta dalla proprietà delle finestre.  
  
<a name="Roles_and_Control_Types"></a>   
## <a name="roles-and-control-types"></a>Ruoli e tipi di controlli  
 In[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] viene usata la proprietà `accRole` (`IAccessible::get_actRole`) per recuperare una descrizione del ruolo dell'elemento nell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], ad esempio ROLE_SYSTEM_SLIDER o ROLE_SYSTEM_MENUITEM. Il ruolo di un elemento rappresenta l'indicazione principale della relativa funzionalità disponibile. L'interazione con un controllo si ottiene usando metodi fissi, ad esempio `IAccessible::accSelect` e `IAccessible::accDoDefaultAction`. L'interazione tra l'applicazione client e l' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] è limitata alle operazioni che è possibile eseguire tramite `IAccessible`.  
  
 Viceversa, in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il tipo di controllo dell'elemento (descritto dalla proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> ) è nettamente separato dalla relativa funzionalità prevista. La funzionalità è determinata dai pattern di controllo che sono supportati dal provider tramite la relativa implementazione di interfacce specializzate. I pattern di controllo possono essere combinati per descrivere l'insieme completo di funzionalità supportate da un determinato elemento dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Alcuni provider devono supportare un determinato pattern di controllo. Ad esempio il provider per una casella di controllo deve supportare il pattern di controllo Toggle. Altri provider devono supportare uno o più insiemi di pattern di controllo. Ad esempio un pulsante deve supportare Toggle o Invoke. Altri provider ancora non supportano affatto i pattern di controllo. Ad esempio, un riquadro che non può essere spostato, ridimensionato o ancorato non include alcun pattern di controllo.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] supporta i controlli personalizzati, che sono identificati dalla proprietà <xref:System.Windows.Automation.ControlType.Custom> e possono essere descritti dalla proprietà <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> .  
  
 Nella tabella seguente è illustrato il mapping tra i ruoli di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] e i tipi di controlli di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|Ruolo di[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Tipo di controllo di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |  
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------|  
|ROLE_SYSTEM_PUSHBUTTON|Button|  
|ROLE_SYSTEM_CLIENT|Calendar|  
|ROLE_SYSTEM_CHECKBUTTON|Casella di controllo|  
|ROLE_SYSTEM_COMBOBOX|Casella combinata|  
|ROLE_SYSTEM_CLIENT|Personalizzato|  
|ROLE_SYSTEM_LIST|Griglia dei dati|  
|ROLE_SYSTEM_LISTITEM|Elemento dei dati|  
|ROLE_SYSTEM_DOCUMENT|Document|  
|ROLE_SYSTEM_TEXT|Edit|  
|ROLE_SYSTEM_GROUPING|Raggruppa|  
|ROLE_SYSTEM_LIST|Intestazione|  
|ROLE_SYSTEM_COLUMNHEADER|Voce di intestazione|  
|ROLE_SYSTEM_LINK|Hyperlink|  
|ROLE_SYSTEM_GRAPHIC|Image|  
|ROLE_SYSTEM_LIST|List|  
|ROLE_SYSTEM_LISTITEM|Elemento dell'elenco|  
|ROLE_SYSTEM_MENUPOPUP|Menu|  
|ROLE_SYSTEM_MENUBAR|Barra dei menu|  
|ROLE_SYSTEM_MENUITEM|Voce di menu|  
|ROLE_SYSTEM_PANE|Riquadro|  
|ROLE_SYSTEM_PROGRESSBAR|Indicatore di stato|  
|ROLE_SYSTEM_RADIOBUTTON|Pulsante di opzione|  
|ROLE_SYSTEM_SCROLLBAR|Barra di scorrimento|  
|ROLE_SYSTEM_SEPARATOR|Separatore|  
|ROLE_SYSTEM_SLIDER|Slider|  
|ROLE_SYSTEM_SPINBUTTON|Spinner|  
|ROLE_SYSTEM_SPLITBUTTON|Pulsante di menu combinato|  
|ROLE_SYSTEM_STATUSBAR|Barra di stato|  
|ROLE_SYSTEM_PAGETABLIST|Scheda|  
|ROLE_SYSTEM_PAGETAB|Voce di scheda|  
|ROLE_SYSTEM_TABLE|Tabella|  
|ROLE_SYSTEM_STATICTEXT|Testo|  
|ROLE_SYSTEM_INDICATOR|Thumb|  
|ROLE_SYSTEM_TITLEBAR|Barra del titolo|  
|ROLE_SYSTEM_TOOLBAR|Barra degli strumenti|  
|ROLE_SYSTEM_TOOLTIP|Descrizione comando|  
|ROLE_SYSTEM_OUTLINE|Struttura ad albero|  
|ROLE_SYSTEM_OUTLINEITEM|Elemento di struttura ad albero|  
|ROLE_SYSTEM_WINDOW|Finestra|  
  
 Per altre informazioni sui diversi tipi di controlli, vedere [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## <a name="states-and-properties"></a>Stati e proprietà  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]gli elementi supportano un insieme comune di proprietà e alcune proprietà (ad esempio `accState`) devono descrivere aspetti molto diversi, a seconda del ruolo dell'elemento. I server devono implementare tutti i metodi di `IAccessible` che restituiscono una proprietà, anche quelli che non sono attinenti all'elemento.  
  
 In[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sono definite molte più proprietà, alcune delle quali corrispondono agli stati di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Alcune sono comuni a tutti gli elementi, mentre altre sono specifiche dei tipi di controlli e dei pattern di controllo. Le proprietà sono differenziate da identificatori univoci e la maggior parte può essere recuperata con un singolo metodo <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>. Molte proprietà sono anche facilmente recuperabili tramite le funzioni di accesso alle proprietà <xref:System.Windows.Automation.AutomationElement.Current%2A> e <xref:System.Windows.Automation.AutomationElement.Cached%2A> .  
  
 Un provider di automazione interfaccia utente non deve implementare proprietà irrilevanti, ma può restituire semplicemente un valore `null` per tutte le proprietà che non supporta. Inoltre, il servizio di base di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] può ottenere alcune proprietà dal provider di finestre predefinito, che vengono combinate con le proprietà implementate in modo esplicito dal provider.  
  
 Oltre a supportare un numero maggiore di proprietà, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] fornisce prestazioni più elevate consentendo il recupero di più proprietà con una singola chiamata tra più processi.  
  
 Nella tabella seguente è illustrata la corrispondenza tra le proprietà nei due modelli.  
  
|Funzione di accesso a proprietà di[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |ID proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Note|  
|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> o <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` ha la precedenza se sono presenti entrambe.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>||  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Vedere la tabella precedente per il mapping tra ruoli e tipi di controlli.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType>|Valide solo per i tipi di controlli che supportano ValuePattern o RangeValuePattern. I valori RangeValue sono normalizzati su 0-100, per coerenza con il comportamento di MSAA. Gli elementi dei valori usano una stringa.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|Proprietà non supportata in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|All'interno di MSAA non è stata fornita una specifica chiara di`accDescription` , quindi i provider hanno inserito informazioni diverse in questa proprietà.|  
|`get_accHelpTopic`|Proprietà non supportata in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]||  
  
 Nella tabella seguente sono illustrate le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che corrispondono alle costanti di stato di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] .  
  
|Stato di[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Proprietà[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Attivazione di una modifica dello stato|  
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------|----------------------------|  
|STATE_SYSTEM_CHECKED|Per la casella di controllo, <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Per il pulsante di opzione, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE_SYSTEM_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Collapsed>|Y|  
|STATE_SYSTEM_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> = <xref:System.Windows.Automation.ExpandCollapseState.Expanded> o <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>|Y|  
|STATE_SYSTEM_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE_SYSTEM_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE_SYSTEM_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> per le voci di menu|N|  
|STATE_SYSTEM_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True e <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> genera <xref:System.Windows.Automation.NoClickablePointException>|N|  
|STATE_SYSTEM_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> =<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE_SYSTEM_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> = <xref:System.Windows.Automation.ToggleState.Indeterminate>|N|  
|STATE_SYSTEM_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE_SYSTEM_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE_SYSTEM_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> = True|N|  
|STATE_SYSTEM_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE_SYSTEM_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=nameWithType>|N|  
|STATE_SYSTEM_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern> è supportato|N|  
|STATE_SYSTEM_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE_SYSTEM_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE_SYSTEM_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 I seguenti stati non sono stati implementati dalla maggior parte dei server di controllo di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] o non hanno equivalenti in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
|Stato di[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] |Note|  
|-----------------------------------------------------------------------|-------------|  
|STATE_SYSTEM_BUSY|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_DEFAULT|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ANIMATED|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_EXTSELECTABLE|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_MARQUEED|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_SELFVOICING|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_TRAVERSED|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_ALERT_HIGH|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_MEDIUM|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_ALERT_LOW|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_FLOATING|Non ampiamente implementato dai server [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]|  
|STATE_SYSTEM_HOTTRACKED|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE_SYSTEM_PRESSED|Non disponibile in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Per un elenco completo di identificatori di proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## <a name="events"></a>Eventi  
 Il meccanismo degli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a differenza di quello di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)], non si basa sull'indirizzamento di eventi (che è strettamente collegato agli handle di finestra) e non richiede l'impostazione di hook da parte dell'applicazione client. La sottoscrizione di eventi può essere ottimizzata non solo per determinati eventi ma anche per determinate parti della struttura ad albero. I provider possono inoltre ottimizzare la generazione di eventi tenendo traccia degli eventi per i quali esistono elementi in ascolto.  
  
 È inoltre più facile per i client recuperare gli elementi che generano eventi, in quanto vengono passati direttamente al callback dell'evento. Le proprietà dell'elemento vengono automaticamente prelette se era attiva una richiesta di cache quando il client ha sottoscritto l'evento.  
  
 Nella tabella seguente è illustrata la corrispondenza tra eventi WinEvent di [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] ed eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|WinEvent|Identificatore di evento di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |  
|--------------|--------------------------------------------------------------------------------------------|  
|EVENT_OBJECT_ACCELERATORCHANGE|Modifica della proprietà<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty> |  
|EVENT_OBJECT_CONTENTSCROLLED|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> sulle barre di scorrimento associate|  
|EVENT_OBJECT_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_DEFACTIONCHANGE|Nessun equivalente|  
|EVENT_OBJECT_DESCRIPTIONCHANGE|Nessun equivalente esatto; forse modifica della proprietà <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> o della proprietà <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|  
|EVENT_OBJECT_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_OBJECT_HELPCHANGE|Modifica di<xref:System.Windows.Automation.AutomationElement.HelpTextProperty> |  
|EVENT_OBJECT_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_LOCATIONCHANGE|Modifica della proprietà<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_OBJECT_NAMECHANGE|Modifica della proprietà<xref:System.Windows.Automation.AutomationElement.NameProperty> |  
|EVENT_OBJECT_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_REORDER|Non usato coerentemente in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Nessun evento direttamente corrispondente definito in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|EVENT_OBJECT_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT_OBJECT_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT_OBJECT_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT_OBJECT_SELECTIONWITHIN|Nessun equivalente|  
|EVENT_OBJECT_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT_OBJECT_STATECHANGE|Vari eventi di modifica di proprietà|  
|EVENT_OBJECT_VALUECHANGE|Modifica di<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=nameWithType> |  
|EVENT_SYSTEM_ALERT|Nessun equivalente|  
|EVENT_SYSTEM_CAPTUREEND|Nessun equivalente|  
|EVENT_SYSTEM_CAPTURESTART|Nessun equivalente|  
|EVENT_SYSTEM_CONTEXTHELPEND|Nessun equivalente|  
|EVENT_SYSTEM_CONTEXTHELPSTART|Nessun equivalente|  
|EVENT_SYSTEM_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT_SYSTEM_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT_SYSTEM_DRAGDROPEND|Nessun equivalente|  
|EVENT_SYSTEM_DRAGDROPSTART|Nessun equivalente|  
|EVENT_SYSTEM_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT_SYSTEM_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT_SYSTEM_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT_SYSTEM_MINIMIZEEND|Modifica della proprietà<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|EVENT_SYSTEM_MINIMIZESTART|Modifica della proprietà<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|EVENT_SYSTEM_MOVESIZEEND|Modifica della proprietà<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_SYSTEM_MOVESIZESTART|Modifica della proprietà<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> |  
|EVENT_SYSTEM_SCROLLINGEND|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>|  
|EVENT_SYSTEM_SCROLLINGSTART|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> o <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> |  
|EVENT_SYSTEM_SOUND|Nessun equivalente|  
|EVENT_SYSTEM_SWITCHEND|Nessun equivalente, ma un evento <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> segnala che una nuova applicazione ha ricevuto lo stato attivo|  
|EVENT_SYSTEM_SWITCHSTART|Nessun equivalente|  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty> |  
|Nessun equivalente|Modifica della proprietà<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> |  
|Nessun equivalente|Evento<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent> |  
|Nessun equivalente|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## <a name="security"></a>Sicurezza  
 Alcuni scenari di personalizzazione di `IAccessible` richiedono il wrapping di un oggetto `IAccessible` di base e la chiamata a tale oggetto. Questa operazione ha implicazioni per la sicurezza, in quanto un componente parzialmente attendibile non deve essere un intermediario in un percorso di codice.  
  
 Il modello di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] rimuove la necessità che i provider effettuino chiamate ad altro codice di provider. Tutta l'aggregazione necessaria viene completata dal servizio di base di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sull'automazione interfaccia utente](../../../docs/framework/ui-automation/index.md)
