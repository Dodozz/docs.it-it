---
title: Cenni preliminari sugli eventi di tempo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: 58861a036d95fcef41da455b25ad71d6e6afaef5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726819"
---
# <a name="timing-events-overview"></a>Cenni preliminari sugli eventi di tempo
In questo argomento viene descritto come utilizzare i cinque eventi di temporizzazione disponibili nel <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock> oggetti.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento è necessario sapere come creare e usare le animazioni. Per iniziare a usare animazioni, vedere la [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Esistono diversi modi per animare le proprietà in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Uso di oggetti storyboard** (markup e codice): È possibile usare <xref:System.Windows.Media.Animation.Storyboard> oggetti per disporre e distribuire le animazioni a uno o più oggetti. Per un esempio, vedere [animare una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Uso di animazioni locali** (solo codice): È possibile applicare <xref:System.Windows.Media.Animation.AnimationTimeline> oggetti direttamente alla proprietà animate. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Uso di orologi** (solo codice): Gestire la creazione di orologi in modo esplicito e distribuire direttamente il clock di animazione definiti.  Per un esempio, vedere [animare una proprietà utilizzando un oggetto AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Poiché è possibile usarli nel markup e codice, usano gli esempi in questa panoramica <xref:System.Windows.Media.Animation.Storyboard> oggetti. I concetti descritti possono tuttavia essere applicati ad altri metodi di animazione delle proprietà.  
  
### <a name="what-is-a-clock"></a>Che cos'è un orologio?  
 Una sequenza temporale, da sola, in realtà non fa altro che descrivere un intervallo di tempo. Si tratta della sequenza temporale <xref:System.Windows.Media.Animation.Clock> oggetto che esegue il lavoro effettivo: mantiene lo stato di runtime correlato al tempo per la sequenza temporale. Nella maggior parte dei casi, ad esempio quando si usano gli storyboard, viene creato automaticamente un orologio per la sequenza temporale. È anche possibile creare un <xref:System.Windows.Media.Animation.Clock> in modo esplicito tramite il <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> (metodo). Per altre informazioni sulle <xref:System.Windows.Media.Animation.Clock> oggetti, vedere la [Cenni preliminari sul sistema di temporizzazione e animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Perché usare gli eventi?  
 Fatta eccezione di una (ricerca allineata all'ultimo tick), tutte le operazioni di tempo interattive sono asincrone. Non è possibile sapere esattamente quando verranno eseguite. Questo può essere un problema quando è presente altro codice dipendente dall'operazione di tempo. Si supponga che si desidera interrompere una sequenza temporale che ha aggiunto un'animazione a un rettangolo. Dopo l'interruzione della sequenza temporale, viene modificato il colore del rettangolo.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 Nell'esempio precedente la seconda riga di codice potrebbe essere eseguita prima dell'interruzione dello storyboard. Ciò avviene perché l'interruzione è un'operazione asincrona. L'indicazione per l'interruzione di una sequenza temporale o di un orologio crea una "richiesta di interruzione" di ordinamenti che non viene elaborata fino al tick successivo del motore di temporizzazione.  
  
 Per eseguire i comandi dopo il completamento di una sequenza temporale, usare gli eventi di tempo. Nell'esempio seguente, un gestore eventi viene usato per modificare il colore di un rettangolo dopo l'interruzione della riproduzione dello storyboard.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Per un esempio più esaustivo, vedere [le modifiche dello stato di ricevere notifica quando un Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Eventi pubblici  
 Il <xref:System.Windows.Media.Animation.Timeline> e <xref:System.Windows.Media.Animation.Clock> classi forniscono entrambe cinque eventi di tempo. Nella tabella seguente sono elencati questi eventi e le condizioni che li attivano.  
  
|event|Operazione interattiva di attivazione|Altri trigger|  
|-----------|--------------------------------------|--------------------|  
|**Completed**|Passaggio al riempimento|L'orologio viene completato.|  
|**CurrentGlobalSpeedInvalidated**|Sospensione, ripresa, ricerca, impostazione di frequenza velocità, passaggio al riempimento, interruzione|L'orologio viene invertito, accelerato, avviato o interrotto.|  
|**CurrentStateInvalidated**|Inizio, passaggio al riempimento, interruzione|L'orologio viene avviato, interrotto, riempito.|  
|**CurrentTimeInvalidated**|Inizio, ricerca, passaggio al riempimento, interruzione|L'orologio avanza.|  
|**RemoveRequested**|Rimuovi||  
  
## <a name="ticking-and-event-consolidation"></a>Tick e consolidamento degli eventi  
 Quando si animano oggetti in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è il motore di temporizzazione che gestisce le animazioni. Il motore di temporizzazione tiene traccia dell'avanzamento del tempo e calcola lo stato di ogni animazione. Esegue numerosi passaggi di valutazione in un secondo. Questi passaggi di valutazione sono noti come "tick".  
  
 Sebbene gli eventi tick siano piuttosto frequenti, è possibile che tra essi avvengano vari eventi. Una sequenza temporale può essere ad esempio interrotta, avviata e interrotta nuovamente, nel qual caso lo stato corrente verrà cambiato tre volte. In teoria l'evento può essere generato più volte in un singolo tick. Il motore di temporizzazione consolida tuttavia gli eventi in modo che ogni evento possa essere generato al massimo una volta per tick.  
  
## <a name="registering-for-events"></a>Registrazione per gli eventi  
 Esistono due modi per registrarsi per gli eventi di tempo: è possibile registrarsi con la sequenza temporale o con l'orologio creato dalla sequenza temporale. La registrazione per un evento direttamente con un orologio è piuttosto semplice, anche se può essere eseguita solo dal codice. È possibile registrarsi per gli eventi con una sequenza temporale dal codice o dal markup. La sezione successiva descrive come registrarsi per gli eventi di orologio con una sequenza temporale.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Registrazione per gli eventi di orologio con una sequenza temporale  
 Anche se una sequenza temporale <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, e <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> sembrano essere associati alla sequenza temporale, la registrazione per questi eventi associa in effetti un gestore eventi con eventi di <xref:System.Windows.Media.Animation.Clock> creato per la sequenza temporale.  
  
 Quando si registra per la <xref:System.Windows.Media.Animation.Timeline.Completed> eventi in una sequenza temporale, ad esempio, si indica al sistema di registrazione per il <xref:System.Windows.Media.Animation.Clock.Completed> evento di ogni orologio creato per la sequenza temporale. Nel codice, è necessario registrarsi per questo evento prima che il <xref:System.Windows.Media.Animation.Clock> viene creato per questa sequenza temporale; in caso contrario, non viene visualizzato la notifica. Ciò si verifica automaticamente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; il parser registra automaticamente per l'evento prima di <xref:System.Windows.Media.Animation.Clock> viene creato.  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sull'animazione e sul sistema di temporizzazione](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Cenni preliminari sui comportamenti temporali](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
