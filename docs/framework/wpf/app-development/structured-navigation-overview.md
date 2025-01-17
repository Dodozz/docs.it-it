---
title: Cenni preliminari sulla navigazione strutturata
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: a0da874c74562822d521d4a44782d9372cd62f90
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588647"
---
# <a name="structured-navigation-overview"></a>Cenni preliminari sulla navigazione strutturata
Contenuto che può essere ospitato da un' [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], una <xref:System.Windows.Controls.Frame>, o una <xref:System.Windows.Navigation.NavigationWindow> è composto da pagine che possono essere identificate da pack [!INCLUDE[TLA#tla_uri#plural](../../../../includes/tlasharptla-urisharpplural-md.md)] e la navigazione da collegamenti ipertestuali. La struttura della pagine e i modi in cui è possibile spostarsi tra di esse, definiti dai collegamenti ipertestuali, costituiscono una topologia di navigazione. Tale topologia è adatta a vari tipi di applicazioni, in particolare a quelli che consentono di spostarsi tra documenti. Per tali applicazioni, l'utente può spostarsi da una pagina all'altra senza che una pagina disponga di informazioni sull'altra.  
  
 Tuttavia, altri tipi di applicazioni presentano pagine che necessitano di informazioni su quando avviene la navigazione tra di esse. Ad esempio, si consideri un'applicazione di risorse umane che include una pagina in cui vengono elencati tutti i dipendenti di un'azienda - la pagina "Elenco dipendenti". Questa pagina può inoltre consentire agli utenti di aggiungere un nuovo dipendente facendo clic su un collegamento ipertestuale. Quando si fa clic su tale collegamento, si passa alla pagina "Aggiungi dipendente" in cui vengono raccolti i dettagli sul nuovo dipendente e quindi si torna alla pagina "Elenco dipendenti" in cui viene creato il nuovo dipendente e aggiornato l'elenco. Questo stile di navigazione è simile alla chiamata di un metodo per l'esecuzione di una determinata elaborazione e la restituzione di un valore, denominata programmazione strutturata. Analogamente, questo stile di navigazione è denominato *navigazione strutturata*.  
  
 Il <xref:System.Windows.Controls.Page> classe non implementa il supporto per la navigazione strutturata. Al contrario, il <xref:System.Windows.Navigation.PageFunction%601> deriva dalla classe <xref:System.Windows.Controls.Page> e lo estende con i costrutti di base necessari per la navigazione strutturata. In questo argomento viene illustrato come definire la navigazione strutturata con <xref:System.Windows.Navigation.PageFunction%601>.  

<a name="Structured_Navigation"></a>   
## <a name="structured-navigation"></a>Navigazione strutturata  
 Quando una pagina chiama un'altra pagina in una navigazione strutturata, sono richiesti alcuni o tutti i comportamenti seguenti:  
  
- La pagina chiamante si sposta sulla pagina chiamata, facoltativamente passando i parametri richiesti dalla pagina chiamata.  
  
- La pagina chiamata, quando l'utente completa l'uso della pagina chiamante, ritorna specificamente alla pagina chiamante e facoltativamente:  
  
    - Restituisce informazioni sullo stato che descrivono come è stata completata la pagina chiamante (ad esempio, se l'utente ha premuto il pulsante OK o Annulla).  
  
    - Restituisce i dati raccolti dall'utente (ad esempio, i dettagli sul nuovo dipendente).  
  
- Quando la pagina chiamate ritorna alla pagina chiamata, la pagina chiamata viene rimossa dalla cronologia di navigazione per isolare le istanze della pagina chiamata l'una dall'altra.  
  
 Questi comportamenti sono illustrati nella figura seguente:  
  
 ![Schermata mostra il flusso tra pagina chiamante e pagina chiamata.](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)  
  
 È possibile implementare questi comportamenti utilizzando un <xref:System.Windows.Navigation.PageFunction%601> come pagina chiamata.  
  
<a name="Structured_Navigation_with_PageFunction"></a>   
## <a name="structured-navigation-with-pagefunction"></a>Navigazione strutturata con PageFunction  
 In questo argomento viene illustrato come implementare il meccanismo di navigazione strutturata includendo una singola base <xref:System.Windows.Navigation.PageFunction%601>. In questo esempio, un <xref:System.Windows.Controls.Page> chiama un <xref:System.Windows.Navigation.PageFunction%601> per ottenere un <xref:System.String> valore da parte dell'utente e come restituirlo.  
  
### <a name="creating-a-calling-page"></a>Creazione di una pagina chiamante  
 La pagina che chiama un' <xref:System.Windows.Navigation.PageFunction%601> può essere un <xref:System.Windows.Controls.Page> o un <xref:System.Windows.Navigation.PageFunction%601>. In questo esempio, è un <xref:System.Windows.Controls.Page>, come illustrato nel codice seguente.  
  
 [!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]  
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]  
  
 [!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
 [!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]  
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]  
  
### <a name="creating-a-page-function-to-call"></a>Creazione di una funzione pagina per la chiamata  
 Poiché la pagina chiama può utilizzare la pagina chiamata per raccogliere e restituire dati da parte dell'utente, <xref:System.Windows.Navigation.PageFunction%601> viene implementato come una classe generica il cui argomento tipo specifica il tipo di valore dalla pagina chiamata restituirà. Il codice seguente illustra l'implementazione iniziale del file, denominata pagina utilizzando un <xref:System.Windows.Navigation.PageFunction%601>, che restituisce un <xref:System.String>.  
  
 [!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]  
  
 [!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
 [!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]  
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]  
  
 La dichiarazione di una <xref:System.Windows.Navigation.PageFunction%601> è simile alla dichiarazione di un <xref:System.Windows.Controls.Page> con l'aggiunta degli argomenti di tipo. Come si può notare nell'esempio di codice, gli argomenti tipo sono specificati sia nel markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usando l'attributo `x:TypeArguments`, che in code-behind, usando la sintassi degli argomenti di tipo generico standard.  
  
 Non è necessario utilizzare solo le classi di .NET Framework come argomenti tipo. Oggetto <xref:System.Windows.Navigation.PageFunction%601> potrebbe essere chiamato per raccogliere dati specifici del dominio astratti come un tipo personalizzato. Il codice seguente viene illustrato come utilizzare un tipo personalizzato come argomento di tipo per un <xref:System.Windows.Navigation.PageFunction%601>.  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]  
  
 [!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]  
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]  
  
 [!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
 [!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]  
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]  
  
 Gli argomenti tipo per il <xref:System.Windows.Navigation.PageFunction%601> forniscono le basi per la comunicazione tra una pagina chiamante e pagina chiamata, descritti nelle sezioni seguenti.  
  
 Come si vedrà, il tipo che viene identificato con la dichiarazione di una <xref:System.Windows.Navigation.PageFunction%601> svolge un ruolo importante nel restituire dati da un <xref:System.Windows.Navigation.PageFunction%601> alla pagina chiamante.  
  
### <a name="calling-a-pagefunction-and-passing-parameters"></a>Chiamata di PageFunction e passaggio di parametri  
 Per chiamare una pagina, la pagina chiamante deve creare un'istanza della pagina chiamata e passare a essa usando il <xref:System.Windows.Navigation.NavigationService.Navigate%2A> (metodo). Ciò consente alla pagina chiamante di passare i dati iniziali alla pagina chiamata, ad esempio i valori predefiniti per i dati raccolti dalla pagina chiamata.  
  
 Il codice seguente illustra la pagina chiamata con un costruttore non predefinito che accetta parametri dalla pagina chiamante.  
  
 [!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
 [!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]  
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]  
  
 Il codice seguente illustra la gestione di pagina chiamante di <xref:System.Windows.Documents.Hyperlink.Click> eventi del <xref:System.Windows.Documents.Hyperlink> per creare un'istanza della pagina chiamata e passare un valore di stringa iniziale.  
  
 [!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]  
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]  
  
 Non è necessario passare parametri alla pagina chiamata. In alternativa, è possibile eseguire quanto segue:  
  
- Dalla pagina chiamante:  
  
    1. Creare un'istanza chiamata <xref:System.Windows.Navigation.PageFunction%601> usando il costruttore predefinito.  
  
    2. I parametri in Store <xref:System.Windows.Application.Properties%2A>.  
  
    3. Passare alla chiamata <xref:System.Windows.Navigation.PageFunction%601>.  
  
- Dall'oggetto chiamato <xref:System.Windows.Navigation.PageFunction%601>:  
  
    - Recuperare e utilizzare i parametri archiviati in <xref:System.Windows.Application.Properties%2A>.  
  
 Tuttavia, come si vedrà successivamente, è comunque necessario usare il codice per creare un'istanza della pagina chiamata e spostarsi su di essa per raccogliere i dati restituiti dalla pagina chiamata. Per questo motivo, il <xref:System.Windows.Navigation.PageFunction%601> deve essere tenuta aperta; in caso contrario, la volta successiva che si passa al <xref:System.Windows.Navigation.PageFunction%601>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] crea un'istanza di <xref:System.Windows.Navigation.PageFunction%601> usando il costruttore predefinito.  
  
 Prima che sia possibile la restituzione della pagina chiamata, questa deve restituire i dati che possono essere recuperati dalla pagina chiamante.  
  
### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Restituzione del risultato dell'attività e dei dati dell'attività da un'attività a una pagina chiamante  
 Al termine dell'uso della pagina chiamata da parte dell'utente, indicato in questo esempio dalla pressione dei pulsanti OK o Annulla, è necessaria la restituzione della pagina chiamata. Dal momento che la pagina chiamante ha usato la pagina chiamata per raccogliere dati dall'utente, la pagina chiamante richiede due tipi di informazioni:  
  
1. Se l'utente ha annullato la pagina chiamante (premendo il pulsante OK o il pulsante Annulla in questo esempio). Ciò consente alla pagina chiamante di determinare se elaborare i dati che la pagina chiamante ha raccolto dall'utente.  
  
2. I dati immessi dall'utente.  
  
 Per informazioni, tornare <xref:System.Windows.Navigation.PageFunction%601> implementa il <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> (metodo). Il codice seguente illustra come chiamarlo.  
  
 [!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
 [!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]  
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]  
  
 In questo esempio se un utente preme il pulsante Annulla, viene restituito alla pagina chiamante un valore di `null`. Se invece viene premuto il pulsante OK, viene restituito il valore di stringa immesso dall'utente. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> è un `protected virtual` che viene chiamato per restituire dati alla pagina chiamante. I dati devono essere assemblati in un'istanza del tipo generico <xref:System.Windows.Navigation.ReturnEventArgs%601> tipo, il cui argomento tipo specifica il tipo di valore che <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> restituisce. In questo modo, quando si dichiara un <xref:System.Windows.Navigation.PageFunction%601> con un particolare argomento tipo, implicitamente che una <xref:System.Windows.Navigation.PageFunction%601> restituirà un'istanza del tipo specificato dall'argomento tipo. In questo esempio, l'argomento di tipo e, di conseguenza, il valore restituito è di tipo <xref:System.String>.  
  
 Quando <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> viene chiamato, la pagina chiamante richiede un modo per ricevere il valore restituito del <xref:System.Windows.Navigation.PageFunction%601>. Per questo motivo <xref:System.Windows.Navigation.PageFunction%601> implementa il <xref:System.Windows.Navigation.PageFunction%601.Return> eventi per la chiamata a pagine da gestire. Quando <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> viene chiamato <xref:System.Windows.Navigation.PageFunction%601.Return> viene generato, in modo che la pagina chiamante può registrarsi con <xref:System.Windows.Navigation.PageFunction%601.Return> che ricevono la notifica.  
  
 [!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
 [!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]  
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]  
  
### <a name="removing-task-pages-when-a-task-completes"></a>Rimozione delle pagine di attività al completamento di un'attività  
 Al momento della restituzione di una pagina chiamata, se l'utente non la annulla, la pagina chiamante elabora i dati immessi dall'utente e restituiti dalla pagina chiamata. Questo tipo di acquisizione dati è in genere un'attività isolata. Al momento della restituzione della pagina chiamata, la pagina chiamante deve creare una nuova pagina chiamante e spostarsi su di essa per acquisire altri dati.  
  
 Tuttavia, a meno che la pagina chiamata non venga rimossa dal journal, l'utente potrà spostarsi nuovamente su un'istanza precedente della pagina chiamante. Se un <xref:System.Windows.Navigation.PageFunction%601> vengono conservate nel journal è determinato dal <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> proprietà. Per impostazione predefinita, una funzione di pagina viene automaticamente rimossa quando <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> viene chiamato quanto <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> è impostata su `true`. Per mantenere una funzione di pagina nella cronologia di navigazione dopo <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> viene chiamato, impostare <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> a `false`.  
  
<a name="Other_Types_of_Structured_Navigation"></a>   
## <a name="other-types-of-structured-navigation"></a>Altri tipi di navigazione strutturata  
 In questo argomento viene illustrato l'utilizzo più elementare di un <xref:System.Windows.Navigation.PageFunction%601> per supportare chiamata/restituzione navigazione strutturata. Partendo da questo fondamento è possibile creare tipi più complessi di navigazione strutturata.  
  
 Ad esempio, talvolta una pagina chiamante richiede più pagine per raccogliere dati sufficienti da un utente o per eseguire un'attività. L'uso di più pagine è indicato come "procedura guidata".  
  
 In altri casi, le applicazioni possono presentare topologie di navigazione complesse il cui corretto funzionamento dipende dalla navigazione strutturata. Per altre informazioni vedere [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Cenni preliminari sulle topologie di navigazione](navigation-topologies-overview.md)
