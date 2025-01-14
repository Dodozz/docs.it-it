---
title: Dizionari risorse uniti
ms.date: 03/30/2017
helpviewer_keywords:
- merged resource dictionaries [WPF]
- dictionaries [WPF], merged resources
ms.assetid: d159531f-05d4-49fd-b951-c332de51e5bc
ms.openlocfilehash: 17dd8e0c02d71fc7e72800fc578866188d03060e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053249"
---
# <a name="merged-resource-dictionaries"></a>Dizionari risorse uniti
Le risorse di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] supportano una funzionalità di dizionari risorse uniti. Questa funzionalità consente di definire la parte delle risorse di un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al di fuori dell'applicazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compilata. Le risorse possono quindi essere condivise nelle applicazioni, oltre che isolate più facilmente per la localizzazione.  
  
## <a name="introducing-a-merged-resource-dictionary"></a>Introduzione di un dizionario risorse unito  
 Nel markup si usa la sintassi seguente per introdurre un dizionario risorse unito in una pagina:  
  
 [!code-xaml[ResourceMergeDictionary#MergedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceMergeDictionary/CS/default.xaml#mergedxaml)]  
  
 Si noti che il <xref:System.Windows.ResourceDictionary> elemento non dispone di un [direttiva X:Key](../../xaml-services/x-key-directive.md), che è in genere necessario per tutti gli elementi in una raccolta di risorse. Ma un'altra <xref:System.Windows.ResourceDictionary> riferimenti interni all'interno di <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> raccolta è un caso speciale, riservato per questo scenario di dizionari risorse uniti. Il <xref:System.Windows.ResourceDictionary> che presenta un oggetto unito dizionario risorse non può contenere un [direttiva X:Key](../../xaml-services/x-key-directive.md). In genere, ognuna <xref:System.Windows.ResourceDictionary> all'interno di <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> raccolta specifica un <xref:System.Windows.ResourceDictionary.Source%2A> attributo. Il valore di <xref:System.Windows.ResourceDictionary.Source%2A> deve essere un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] che risolve il percorso del file di risorse da unire. La destinazione di tale [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] deve essere un altro [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file, con <xref:System.Windows.ResourceDictionary> come elemento radice.  
  
> [!NOTE]
>  È consentito definire le risorse all'interno di un <xref:System.Windows.ResourceDictionary> che viene specificato come un dizionario unito, come alternativa alla specifica <xref:System.Windows.ResourceDictionary.Source%2A>, o aggiunta a qualsiasi risorsa inclusa dall'origine specificata. ma questo non è uno scenario comune. Lo scenario principale per i dizionari uniti prevede l'unione delle risorse da percorsi di file esterni. Se si desidera specificare le risorse all'interno del markup per una pagina, è consigliabile definire in genere questi principale <xref:System.Windows.ResourceDictionary> e non nei dizionari uniti.  
  
## <a name="merged-dictionary-behavior"></a>Comportamento dei dizionari uniti  
 Le risorse in un dizionario unito fanno parte dell'ambito della ricerca di risorse, che segue immediatamente l'ambito del dizionario risorse principale in cui vengono unite. Anche se una chiave di risorsa deve essere univoca in ogni singolo dizionario, una chiave può esistere più volte in un set di dizionari uniti. In questo caso, la risorsa restituita proviene dall'ultimo dizionario trovato in sequenza nel <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> raccolta. Se il <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> raccolta è stata definita in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], quindi l'ordine dei dizionari uniti nella raccolta è l'ordine degli elementi specificati nel markup. Se una chiave viene definita nel dizionario primario e anche in un dizionario unito, la risorsa restituita proviene dal dizionario primario. Queste regole di ambito si applicano ugualmente sia ai riferimenti a risorse statiche che ai riferimenti a risorse dinamiche.  
  
### <a name="merged-dictionaries-and-code"></a>Dizionari uniti e codice  
 I dizionari uniti possono essere aggiunti a un dizionario `Resources` tramite il codice. Il valore predefinito, inizialmente vuoto <xref:System.Windows.ResourceDictionary> che esiste per qualsiasi `Resources` proprietà ha anche un valore predefinito, inizialmente vuoto <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> proprietà della raccolta. Per aggiungere un dizionario unito tramite codice, si ottiene un riferimento all'elemento primario desiderato <xref:System.Windows.ResourceDictionary>, ottenere relativi <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A> il valore di proprietà e chiamare `Add` per il tipo generico `Collection` contenuta in <xref:System.Windows.ResourceDictionary.MergedDictionaries%2A>. L'oggetto aggiunto deve essere un nuovo <xref:System.Windows.ResourceDictionary>. Nel codice, non viene impostato il <xref:System.Windows.ResourceDictionary.Source%2A> proprietà. In alternativa, è necessario ottenere un <xref:System.Windows.ResourceDictionary> oggetto creando uno o caricandone uno. Un modo per caricare un oggetto esistente <xref:System.Windows.ResourceDictionary> chiamare <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> su un oggetto esistente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] flusso di file con un <xref:System.Windows.ResourceDictionary> radice, quindi eseguire il cast di <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType> un valore restituito per <xref:System.Windows.ResourceDictionary>.  
  
### <a name="merged-resource-dictionary-uris"></a>URI di dizionari risorse uniti  
 Per includere un dizionario risorse unito, sono disponibili diverse tecniche, indicate dal formato [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] che si userà. In generale, queste tecniche si possono suddividere in due categorie: risorse compilate come parte del progetto e risorse non compilate come parte del progetto.  
  
 Per le risorse compilate come parte del progetto, è possibile usare un percorso relativo che fa riferimento alla posizione della risorsa. Il percorso relativo viene valutato durante la compilazione. La risorsa deve essere definita nell'ambito del progetto come azione di compilazione Risorsa. Se si include un file di risorse XAML nel progetto come risorsa, non è necessario copiare il file di risorse nella directory di output, perché la risorsa è già inclusa nell'applicazione compilata. È anche possibile usare un'azione di compilazione Contenuto, ma è necessario copiare i file nella directory di output e distribuire i file di risorse nella stessa relazione percorso con l'eseguibile.  
  
> [!NOTE]
>  Non usare l'azione di compilazione Risorsa incorporata. L'azione di compilazione stesso è supportata per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni, ma la risoluzione dello <xref:System.Windows.ResourceDictionary.Source%2A> non incorpora <xref:System.Resources.ResourceManager>e pertanto non è possibile separare la singola risorsa dal flusso. È tuttavia possibile usare risorsa incorporata per altri scopi purché è stato anche usato <xref:System.Resources.ResourceManager> per accedere alle risorse.  
  
 Una tecnica correlata consiste nell'usare un URI di tipo pack di un file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e nel farvi riferimento come origine. Un URI di tipo pack abilita i riferimenti ai componenti degli assembly a cui si fa riferimento e altre tecniche. Per altre informazioni sugli URI di tipo pack, vedere [File di dati e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md).  
  
 Per le risorse non compilate come parte del progetto, l'URI viene valutato in fase di esecuzione. È possibile usare un trasporto URI comune, ad esempio file: o http:, per fare riferimento al file di risorse. Lo svantaggio nell'uso dell'approccio delle risorse non compilate è che l'accesso file: richiede altri passaggi per la distribuzione e l'accesso http: implica la zona di sicurezza Internet.  
  
### <a name="reusing-merged-dictionaries"></a>Riutilizzo dei dizionari uniti  
 È possibile usare di nuovo o condividere i dizionari risorse uniti tra le applicazioni perché è possibile fare riferimento al dizionario risorse da unire con qualsiasi [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] valido. La scelta del modo per procedere dipenderà dalla strategia di distribuzione dell'applicazione e dal modello di applicazione seguito. La suddetta strategia basata sugli URI di tipo pack consente di originare a livello comune una risorsa unita in più progetti durante lo sviluppo condividendo un riferimento ad assembly. In questo scenario le risorse vengono ancora distribuite dal client e almeno una delle applicazioni deve distribuire l'assembly di riferimento. È anche possibile fare riferimento alle risorse unite tramite un URI distribuito che usa il protocollo http.  
  
 La scrittura di dizionari uniti come file dell'applicazione locali o nello spazio di archiviazione condiviso locale è un altro possibile scenario di distribuzione dell'applicazione/dizionari uniti.  
  
### <a name="localization"></a>Localizzazione  
 Se le risorse che è necessario localizzare vengono isolate nei dizionari uniti nei dizionari primari e conservate come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] libero, questi file possono essere localizzati separatamente. Questa tecnica è un'alternativa leggera alla localizzazione degli assembly di risorse satellite. Per informazioni dettagliate, vedere [Panoramica della globalizzazione e localizzazione WPF](wpf-globalization-and-localization-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse XAML](xaml-resources.md)
- [Risorse e codice](resources-and-code.md)
- [File di dati e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md)
