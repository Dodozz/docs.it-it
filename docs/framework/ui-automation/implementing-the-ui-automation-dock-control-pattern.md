---
title: Implementazione del pattern di controllo Dock di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: bc426634f981356c4e183da421c9ced99469b87c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647168"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a>Implementazione del pattern di controllo Dock di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IDockProvider>, incluse le informazioni relative alle proprietà. Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.DockPattern> viene usato per esporre le proprietà di ancoraggio di un controllo all'interno di un contenitore di ancoraggio. Un contenitore di ancoraggio è un controllo che consente di disporre gli elementi figlio orizzontalmente e verticalmente, uno rispetto all'altro. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
 ![Contenitore di ancoraggio con due elementi figlio ancorati. ](../../../docs/framework/ui-automation/media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")  
Esempio di ancoraggio da Visual Studio dove la finestra "Visualizzazione classi" è impostata su DockPosition.Right e la finestra "Elenco errori" è impostata su DockPosition.Bottom  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo Dock, tenere presenti le linee guida e le convenzioni seguenti:  
  
- <xref:System.Windows.Automation.Provider.IDockProvider> non espone le proprietà del contenitore di ancoraggio o le proprietà dei controlli ancorati vicino al controllo corrente all'interno del contenitore di ancoraggio.  
  
- I controlli vengono ancorati reciprocamente in base al relativo ordine z corrente, ovvero più elevata è la posizione nell'ordine z, più lontano verrà inserito il controllo rispetto al bordo specificato del contenitore di ancoraggio.  
  
- Se il contenitore di ancoraggio viene ridimensionato, i controlli ancorati all'interno del contenitore verranno riposizionati e allineati allo stesso bordo a cui sono stati originariamente ancorati. I controlli ancorati verranno inoltre ridimensionati per riempire lo spazio all'interno del contenitore in base al comportamento di ancoraggio della relativa proprietà <xref:System.Windows.Automation.DockPosition>. Ad esempio, se viene specificata la proprietà <xref:System.Windows.Automation.DockPosition.Top> , i lati destro e sinistro del controllo verranno espansi in modo da riempire lo spazio disponibile. Se viene specificata la proprietà <xref:System.Windows.Automation.DockPosition.Fill> , tutti e quattro i lati del controllo verranno espansi in modo da riempire lo spazio disponibile.  
  
- In un sistema con più monitor i controlli devono essere ancorati al lato sinistro o destro del monitor corrente. Se ciò non è possibile, devono essere ancorati al lato sinistro del monitor all'estrema sinistra o al lato destro del monitor all'estrema destra.  
  
<a name="Required_Members_for_IDockProvider"></a>   
## <a name="required-members-for-idockprovider"></a>Membri obbligatori per IDockProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione dell'interfaccia IDockProvider.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|Metodo|nessuno|  
  
 Questo pattern di controllo non è associato a eventi.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> -Quando un controllo non è in grado di eseguire lo stile di ancoraggio richiesto.|  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica dei pattern di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Panoramica dell'albero di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Usare la memorizzazione nella cache in automazione interfaccia utente](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
