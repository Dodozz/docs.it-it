---
title: Eventi di modifica delle proprietà
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
ms.openlocfilehash: b6f625f76e230b7d6bf0488bfa75c227de31a5d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62030303"
---
# <a name="property-change-events"></a>Eventi di modifica delle proprietà
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] definisce diversi eventi generati in risposta a una modifica nel valore di una proprietà. Spesso la proprietà è una proprietà di dipendenza. L'evento stesso è in alcuni casi un evento indirizzato, in altri casi un evento [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] standard. La definizione dell'evento varia in base allo scenario, poiché alcune modifiche delle proprietà sono inviate in modo più appropriato tramite un albero di elementi, mentre altre in genere sono di interesse solo per l'oggetto in cui la proprietà è stata modificata.  
  
## <a name="identifying-a-property-change-event"></a>Identificazione di un evento di modifica delle proprietà  
 Non tutti gli eventi che segnalano una modifica delle proprietà sono identificati in modo esplicito come eventi di modifica delle proprietà, per mezzo di un pattern di firma o di nome. In genere, la descrizione dell'evento nella documentazione [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] indica se l'evento è direttamente collegato alla modifica del valore di una proprietà e fornisce riferimenti incrociati tra la proprietà e l'evento.  
  
### <a name="routedpropertychanged-events"></a>Eventi RoutedPropertyChanged  
 Alcuni eventi usano un tipo di dati di evento e un delegato che vengono usati in modo esplicito per gli eventi di modifica delle proprietà. Il tipo di dati di evento è <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, e il delegato è <xref:System.Windows.RoutedPropertyChangedEventHandler%601>. I dati di evento e il delegato dispongono entrambi di un parametro di tipo generico, usato per specificare il tipo effettivo della proprietà modificata quando si definisce il gestore. I dati dell'evento contengono due proprietà, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> e <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, entrambe passate come argomento di tipo nell'evento dati.  
  
 La parte "Routed" del nome indica che l'evento di modifica proprietà è registrato come evento indirizzato. Il vantaggio che si ottiene nell'indirizzare un evento di modifica proprietà è dato dal fatto che il livello superiore di un controllo può ricevere eventi di modifica proprietà se vengono modificati i valori delle proprietà sugli elementi figlio (parti composite del controllo). Ad esempio, è possibile creare un controllo che incorpora un <xref:System.Windows.Controls.Primitives.RangeBase> controllo, ad esempio un <xref:System.Windows.Controls.Slider>. Se il valore della <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> le modifiche alle proprietà della parte del dispositivo di scorrimento, si potrebbe voler gestire la modifica del controllo padre anziché sulla parte.  
  
 Poiché si hanno un valore vecchio e un valore nuovo, può sembrare opportuno usare questo gestore eventi come validator per il valore della proprietà. Quest'uso, tuttavia, non rientra negli intenti di progettazione della maggior parte degli eventi di modifica proprietà. In genere i valori vengono forniti per consentire di eseguire azioni su di essi in altre aree logiche del codice, ma la modifica dei valori dall'interno del gestore eventi non è consigliabile e può causare ricorsione non intenzionale a seconda della modalità di implementazione del gestore.  
  
 Se la proprietà è una proprietà di dipendenza personalizzate, o se si lavora con una classe derivata in cui è stato definito il codice di creazione dell'istanza, è un meccanismo per tenere traccia delle modifiche alle proprietà che è incorporata in più efficiente il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà: il callback del sistema di proprietà <xref:System.Windows.CoerceValueCallback> e <xref:System.Windows.PropertyChangedCallback>. Per informazioni dettagliate su come usare il sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per la convalida e la coercizione, vedere [Callback e convalida delle proprietà di dipendenza](dependency-property-callbacks-and-validation.md) e [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Eventi DependencyPropertyChanged  
 Un'altra coppia di tipi che fanno parte di uno scenario di proprietà degli eventi modificati <xref:System.Windows.DependencyPropertyChangedEventArgs> e <xref:System.Windows.DependencyPropertyChangedEventHandler>. Gli eventi per queste modifiche delle proprietà non sono eventi indirizzati, bensì eventi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] standard. <xref:System.Windows.DependencyPropertyChangedEventArgs> è un evento insolito segnalazione dei dati tipo poiché non deriva da <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> è una struttura, non una classe.  
  
 Gli eventi che usano <xref:System.Windows.DependencyPropertyChangedEventArgs> e <xref:System.Windows.DependencyPropertyChangedEventHandler> sono leggermente più comuni `RoutedPropertyChanged` gli eventi. Un esempio di un evento che usa questi tipi è <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Ad esempio <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> segnala inoltre un valore vecchio e nuovo della proprietà. Inoltre, a questo evento si applicano le stesse considerazioni relative all'uso dei valori. In genere è sconsigliabile provare a modificare nuovamente i valori sul mittente in risposta all'evento.  
  
## <a name="property-triggers"></a>Trigger di proprietà  
 Un concetto correlato strettamente a un evento di modifica proprietà è quello di trigger di proprietà. Un trigger di proprietà viene creato all'interno di uno stile o di un modello e consente di creare un comportamento condizionale basato sul valore della proprietà a cui il trigger è assegnato.  
  
 La proprietà per un trigger di proprietà deve essere una proprietà di dipendenza. Può trattarsi, come spesso accade, di una proprietà di dipendenza di sola lettura. Un buon indicatore del fatto che una proprietà di dipendenza esposta da un controllo sia progettata almeno parzialmente come trigger di proprietà è la presenza del termine "Is" nel nome della proprietà. Le proprietà con questo nome sono spesso proprietà di dipendenza booleane di sola lettura il cui scenario primario è la segnalazione dello stato di un controllo che può avere conseguenze sull'interfaccia utente in tempo reale, pertanto sono un buon candidato ad essere trigger di proprietà.  
  
 Alcune di queste proprietà hanno anche un evento di modifica proprietà dedicato. Ad esempio, la proprietà <xref:System.Windows.UIElement.IsMouseCaptured%2A> dispone di un evento di modifica proprietà <xref:System.Windows.UIElement.IsMouseCapturedChanged>. La stessa proprietà è di sola lettura, con il valore viene regolato dal sistema di input e genera il sistema di input <xref:System.Windows.UIElement.IsMouseCapturedChanged> a ogni modifica in tempo reale.  
  
 Rispetto a un vero evento di modifica proprietà, l'uso di un trigger per gestire una modifica di proprietà presenta alcune limitazioni.  
  
 I trigger di proprietà funzionano in base a una logica di corrispondenza esatta. Si specificano una proprietà e un valore che indica il particolare valore per cui interviene il trigger. Ad esempio, `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. A causa di questa limitazione, nella maggior parte dei casi i trigger di proprietà vengono usati per proprietà booleane, o proprietà che accettano un valore di enumerazione dedicato, in cui l'intervallo di valori possibili è sufficientemente gestibile da consentire la definizione di un trigger per ogni caso. In alternativa, potrebbero esistere trigger di proprietà solo per valori speciali, ad esempio nel caso che un conteggio di elementi raggiunga lo zero, senza trigger che tengano conto dei casi in cui il valore della proprietà viene di nuovo modificato in un numero diverso da zero (anziché disporre di trigger per tutti i casi, in questo scenario potrebbe essere necessario un gestore eventi di codice o un comportamento predefinito per ripristinare lo stato del trigger quando il valore è diverso da zero).  
  
 La sintassi del trigger di proprietà è analoga a un'istruzione "if" nella programmazione. Se la condizione del trigger è true, viene eseguito il corpo del trigger di proprietà. Il corpo di un trigger di proprietà non è codice, ma markup. Il markup è limitato all'utilizzo di uno o più <xref:System.Windows.Setter> elementi per impostare altre proprietà dell'oggetto di cui si applica lo stile o modello.  
  
 Per compensare la condizione "if" di un trigger di proprietà che ha un'ampia gamma di possibili valori, è consigliabile in genere impostato quello stesso valore di proprietà sul valore predefinito mediante un <xref:System.Windows.Setter>. In questo modo, il <xref:System.Windows.Trigger> setter contenuto avrà la precedenza quando la condizione del trigger è true e il <xref:System.Windows.Setter> che non rientra in un <xref:System.Windows.Trigger> avrà la precedenza ogni volta che la condizione del trigger è false.  
  
 I trigger di proprietà sono generalmente adatti negli scenari in cui una o più proprietà di aspetto devono essere modificate, in base allo stato di un'altra proprietà sullo stesso elemento.  
  
 Per altre informazioni sui trigger di proprietà, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
