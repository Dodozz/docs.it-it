---
title: Tipi migrati da WPF a System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 37433768c1bca3c013fb1e505d55bd7295f34933
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758020"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Tipi migrati da WPF a System.Xaml
In .NET Framework 3.5 e .NET Framework 3.0, entrambi [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] e Windows Workflow Foundation è inclusa un'implementazione del linguaggio XAML. Molti dei tipi pubblici che fornivano l'estensibilità per l'implementazione XAML di WPF erano inclusi negli assembly WindowsBase, PresentationCore e PresentationFramework. Analogamente, i tipi pubblici che fornivano l'estensibilità per Windows Workflow Foundation XAML erano inclusi nell'assembly ComponentModel. In .NET Framework 4, alcuni dei tipi correlati a XAML viene eseguita la migrazione all'assembly System. Xaml. Un'implementazione di .NET Framework comune dei servizi di linguaggio XAML consente molti scenari di estensibilità XAML che sono stati originariamente definiti dall'implementazione XAML di un framework specifico, ma fanno ora parte di supporto generale per il linguaggio XAML di .NET Framework 4. In questo argomento sono elencati i tipi di cui è stata eseguita la migrazione e vengono illustrati i problemi correlati alla migrazione.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>Assembly e spazi dei nomi  
 In .NET Framework 3.5 e .NET Framework 3.0, i tipi implementati da WPF per il supporto di XAML erano in genere inclusi il <xref:System.Windows.Markup> dello spazio dei nomi. La maggior parte di questi tipi era inclusa nell'assembly WindowsBase.  
  
 In .NET Framework 4, c'è un nuovo <xref:System.Xaml> dello spazio dei nomi e un nuovo assembly System. Xaml. Molti dei tipi implementati in origine per XAML di WPF sono ora forniti come punti di estendibilità o servizi per qualsiasi implementazione di XAML. Nell'ambito della scelta di renderli disponibili per scenari più generali, i tipi sono stati inoltrati dall'assembly WPF originale all'assembly System.Xaml. Questo consente scenari di estensibilità XAML senza che sia necessario includere assembly di altri Framework (ad esempio WPF e Windows Workflow Foundation).  
  
 Per quanto riguarda i tipi migrati, la maggior parte rimane nello spazio dei nomi <xref:System.Windows.Markup> . Questa scelta deriva parzialmente dalla necessità di evitare l'interruzione dei mapping dello spazio dei nomi CLR nelle implementazioni esistenti su base file. Di conseguenza, il <xref:System.Windows.Markup> dello spazio dei nomi in .NET Framework 4 contiene una combinazione di tipi di supporto del linguaggio XAML generali (dall'assembly System. XAML) e i tipi che sono specifici per l'implementazione XAML WPF (provenienti da WindowsBase e altri assembly WPF). Per qualsiasi tipo di cui è stata eseguita la migrazione a System.Xaml e che in precedenza era incluso in un assembly WPF è disponibile il supporto per l'inoltro dei tipi nella versione 4 dell'assembly WPF.  
  
### <a name="workflow-xaml-support-types"></a>Tipi di supporto XAML del flusso di lavoro  
 Windows Workflow Foundation viene fornito anche i tipi di supporto XAML e in molti casi questi tipi avevano nomi brevi identici a un WPF equivalente. Di seguito è riportato un elenco dei tipi di supporto di Windows Workflow Foundation XAML:  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 Questi tipi sono ancora presenti negli assembly di Windows Workflow Foundation per .NET Framework 4 ed sono ancora il supporto da utilizzare per specifiche applicazioni di Windows Workflow Foundation. Tuttavia, è consigliabile non farvi da applicazioni o Framework che non usano Windows Workflow Foundation.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 In .NET Framework 3.5 e .NET Framework 3.0, il <xref:System.Windows.Markup.MarkupExtension> classe per WPF era inclusa nell'assembly WindowsBase. Una classe parallela per Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, era presente nell'assembly ComponentModel. In .NET Framework 4, il <xref:System.Windows.Markup.MarkupExtension> classe viene eseguita la migrazione all'assembly System. Xaml. In .NET Framework 4, <xref:System.Windows.Markup.MarkupExtension> viene usata per qualsiasi scenario di estensibilità XAML che usa servizi XAML di .NET Framework, non solo per quelli basati su Framework specifici. Quando possibile, framework specifici o codice utente nel framework deve essere basati anche sulla classe <xref:System.Windows.Markup.MarkupExtension> per l'estensione XAML.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>MarkupExtension con supporto di classi del servizio  
 .NET framework 3.5 e .NET Framework 3.0 per WPF offerti diversi servizi disponibili in <xref:System.Windows.Markup.MarkupExtension> i responsabili dell'implementazione e <xref:System.ComponentModel.TypeConverter> per supportare l'utilizzo di tipi/proprietà in XAML. Questi servizi sono i seguenti:  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
>  Un altro servizio da .NET Framework 3.5 è correlato alle estensioni di markup è il <xref:System.Windows.Markup.IReceiveMarkupExtension> interfaccia. <xref:System.Windows.Markup.IReceiveMarkupExtension> non è stata eseguita e viene contrassegnata come `[Obsolete]` per .NET Framework 4. Negli scenari in precedenza veniva usato <xref:System.Windows.Markup.IReceiveMarkupExtension> , ora invece è necessario usare callback con attributi <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> . Anche<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> è contrassegnato come `[Obsolete]`.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>Funzionalità del linguaggio XAML  
 Diversi componenti e funzionalità del linguaggio XAML per WPF erano in precedenza inclusi nell'assembly PresentationFramework. Questi venivano implementati come una sottoclasse <xref:System.Windows.Markup.MarkupExtension> per esporre gli utilizzi delle estensioni di markup nel markup XAML. In .NET Framework 4 questi presenti nell'assembly System. XAML in modo che i progetti che non includono assembly WPF possono usare queste funzionalità a livello di linguaggio XAML. WPF Usa queste stesse implementazioni per le applicazioni .NET Framework 4. Come per gli altri casi elencati in questo argomento, i tipi di supporto continuano a esistere nello spazio dei nomi <xref:System.Windows.Markup> per evitare l'interruzione di riferimenti precedenti.  
  
 Nella tabella seguente è riportato un elenco delle classi di supporto delle funzionalità del linguaggio XAML definite in System.Xaml:  
  
|Funzionalità del linguaggio XAML|Utilizzo|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 Sebbene in System.Xaml possano non essere presenti classi di supporto specifiche, la logica generale per l'elaborazione delle funzionalità del linguaggio per XAML si trova ora in System.Xaml e nei relativi reader XAML e writer XAML implementati. Ad esempio, `x:TypeArguments` è un attributo elaborato da reader XAML e writer XAML delle implementazioni di System.Xaml. Può essere indicato nel flusso del nodo XAML, viene gestito nel contesto dello schema XAML predefinito (basato su CLR), dispone di una rappresentazione del sistema di tipi di XAML e così via. Di conseguenza, la documentazione di riferimento per tutte le funzionalità a livello di linguaggio XAML è inclusa come argomento secondario per [XAML Services](index.md) e per l'area generale specifica del set di documentazione .NET Framework, anziché far parte del set di documentazione WPF come argomento secondario di [Avanzate (WPF)](../wpf/advanced/index.md) , come accade ancora nei set di documentazione 3.5.  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer e classi di supporto  
 La classe <xref:System.Windows.Markup.ValueSerializer> supporta la conversione di tipi in una stringa, in particolare per i casi di serializzazione di XAML in cui per la serializzazione possono essere necessarie più modalità o nodi nell'output. In .NET Framework 3.5 e .NET Framework 3.0, il <xref:System.Windows.Markup.ValueSerializer> per WPF era inclusa nell'assembly WindowsBase. In .NET Framework 4, il <xref:System.Windows.Markup.ValueSerializer> classe è in System. XAML e viene usata per qualsiasi scenario di estensibilità XAML, non solo per quelli basati su WPF. Viene inoltre eseguita la migrazione degli oggetti<xref:System.Windows.Markup.IValueSerializerContext> (servizio di supporto) e <xref:System.Windows.Markup.DateTimeValueSerializer> (sottoclasse specifica) a System.Xaml.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>Attributi correlati a XAML  
 In XAML per WPF erano inclusi vari attributi che potevano essere applicati a tipi CLR per fornire indicazioni sul relativo comportamento XAML. Di seguito è riportato un elenco di attributi presenti negli assembly WPF in .NET Framework 3.5 e .NET Framework 3.0. Questi attributi vengono migrati a System. XAML in .NET Framework 4.  
  
- <xref:System.Windows.Markup.AmbientAttribute>  
  
- <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
- <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
- <xref:System.Windows.Markup.DependsOnAttribute>  
  
- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
- <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
- <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
- <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
- <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
- <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a>Classi di vario tipo  
 Il <xref:System.Windows.Markup.IComponentConnector> interfaccia era inclusa in WindowsBase in .NET Framework 3.5 e .NET Framework 3.0, ma è presente in System. XAML in .NET Framework 4. L'interfaccia<xref:System.Windows.Markup.IComponentConnector> è principalmente destinata al supporto per gli strumenti di supporto e compilatori di markup XAML.  
  
 Il <xref:System.Windows.Markup.INameScope> interfaccia era inclusa in WindowsBase in .NET Framework 3.5 e .NET Framework 3.0, ma è presente in System. XAML in .NET Framework 4. <xref:System.Windows.Markup.INameScope> definisce le operazioni di base per un NameScope XAML.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Classi correlate a XAML con nomi condivisi incluse in WPF e System.Xaml  
 Le classi seguenti sono incluse negli assembly WPF sia l'assembly System. XAML in .NET Framework 4:  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 L'implementazione WPF si trova nello spazio dei nomi <xref:System.Windows.Markup> e nell'assembly PresentationFramework. L'implementazione di System.Xaml si trova nello spazio dei nomi <xref:System.Xaml> . Se si usano tipi WPF o si deriva da tipi WPF, è in genere necessario usare le implementazioni WPF di <xref:System.Windows.Markup.XamlReader> e <xref:System.Windows.Markup.XamlWriter> anziché le implementazioni di System.Xaml. Per altre informazioni, vedere la sezione Osservazioni in <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> e <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.  
  
 Se si includono riferimenti agli assembly WPF a System.Xaml e si usano anche istruzioni `include` per gli spazi dei nomi <xref:System.Windows.Markup> e <xref:System.Xaml> , potrebbe essere necessario qualificare completamente le chiamate a queste API per risolvere i tipi senza ambiguità.  
  
## <a name="see-also"></a>Vedere anche

- [Servizi XAML](index.md)
