---
title: Implementazione del pattern di controllo Selection di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: 0b468c7fd88c7b79ca069553af0740e84ae9d05b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649517"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a>Implementazione del pattern di controllo Selection di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.ISelectionProvider>, incluse le informazioni relative a eventi e proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.SelectionPattern> viene usato per supportare i controlli che fungono da contenitori per una raccolta di elementi figlio selezionabili. Gli elementi figlio di questo elemento devono implementare <xref:System.Windows.Automation.Provider.ISelectionItemProvider>. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Selection, tenere presenti le linee guida e le convenzioni seguenti:  
  
- I controlli che implementano <xref:System.Windows.Automation.Provider.ISelectionProvider> consentono la selezione di uno o più elementi figlio. Ad esempio, una casella di riepilogo e le visualizzazioni elenco e struttura ad albero supportano più selezioni, mentre una casella combinata, un dispositivo di scorrimento e un gruppo di pulsanti di opzione supportano solo una selezione.  
  
- I controlli che presentano un intervallo minimo, massimo e continuo, ad esempio il controllo dispositivo di scorrimento **Volume** , deve implementare <xref:System.Windows.Automation.Provider.IRangeValueProvider> anziché <xref:System.Windows.Automation.Provider.ISelectionProvider>.  
  
- I controlli a selezione singola che gestiscono i controlli figlio che implementano <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, ad esempio il dispositivo di scorrimento **Risoluzione schermo** nella finestra di dialogo **Proprietà di visualizzazione** oppure il controllo di selezione **Selezione colori** in [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (illustrato di seguito), devono implementare <xref:System.Windows.Automation.Provider.ISelectionProvider>. I relativi elementi figlio devono implementare <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> e <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
 ![Selezione colori con il giallo evidenziato. ](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Esempio di mapping delle stringhe dei campioni colore  
  
- I menu non supportano <xref:System.Windows.Automation.SelectionPattern>. Se vengono usate voci di menu che includono testo e grafica, ad esempio gli elementi **Riquadro di anteprima** nel menu **Visualizza** in [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)], e se occorre indicare lo stato, è necessario implementare <xref:System.Windows.Automation.Provider.IToggleProvider>.  
  
<a name="Required_Members_for_ISelectionProvider"></a>   
## <a name="required-members-for-iselectionprovider"></a>Membri obbligatori per ISelectionProvider  
 Le proprietà, i metodi e gli eventi seguenti sono obbligatori per l'implementazione dell'interfaccia <xref:System.Windows.Automation.Provider.ISelectionProvider> .  
  
|Membri obbligatori|Tipo|Note|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Proprietà|Deve supportare gli eventi modificati dalla proprietà tramite <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> e <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Proprietà|Deve supportare gli eventi modificati dalla proprietà tramite <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> e <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|event|Generato quando una selezione in un contenitore ha subito modifiche significative e richiede l'invio di un numero di eventi di aggiunta e rimozione maggiore rispetto a quanto definito mediante la costante <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
 Le proprietà <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> e <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> possono essere dinamiche. Ad esempio, lo stato iniziale di un controllo potrebbe prevedere la selezione di nessun elemento per impostazione predefinita, a indicare che <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> è `false`. Tuttavia, dopo aver selezionato un elemento, il controllo deve sempre avere almeno un elemento selezionato. Analogamente, in casi rari, un controllo potrebbe consentire la selezione di più elementi durante l'inizializzazione e successivamente consentire solo selezioni singole.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Il controllo non è abilitato.|  
|<xref:System.InvalidOperationException>|Il controllo è nascosto.|  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei pattern di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Implementazione del pattern di controllo SelectionItem di automazione interfaccia utente](../../../docs/framework/ui-automation/implementing-the-ui-automation-selectionitem-control-pattern.md)
- [Panoramica dell'albero di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
