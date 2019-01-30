---
title: Novità in Windows Workflow Foundation in .NET 4.5
ms.date: 03/30/2017
ms.assetid: 195c43a8-e0a8-43d9-aead-d65a9e6751ec
ms.openlocfilehash: 6afdca70dacb97cda4f72d7a6b4114c09d46bee1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279136"
---
# <a name="whats-new-in-windows-workflow-foundation-in-net-45"></a>Novità in Windows Workflow Foundation in .NET 4.5
Windows Workflow Foundation (WF) in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] introduce molte nuove funzionalità, come nuove attività, funzionalità di progettazione e modelli di sviluppo del flusso di lavoro. Molte, ma non tutte, le nuove funzionalità del flusso di lavoro introdotte in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sono supportate nella finestra di progettazione del flusso di lavoro ospitata nuovamente. Per altre informazioni sulle nuove funzionalità supportate, vedere [supporto per nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocate](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md). Per altre informazioni sulla migrazione delle applicazioni del flusso di lavoro .NET 3.0 e .NET 3.5 per usare la versione più recente, vedere [materiale sussidiario di migrazione](../../../docs/framework/windows-workflow-foundation/migration-guidance.md). In questo argomento viene fornita una panoramica delle nuove funzionalità del flusso di lavoro introdotte in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
> [!WARNING]
>  Le nuove funzionalità di Windows Workflow Foundation introdotte [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] non sono disponibili per i progetti destinati a versioni precedenti del framework. Se un progetto destinato a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] viene reindirizzato a una versione precedente del framework, si possono verificare diversi problemi.  
>   
>  -   Le espressioni c# verranno sostituite nel finestra di progettazione con il messaggio **valore impostato in XAML**.  
> -   Si verificheranno molti errori di compilazione, incluso il seguente errore.  
>   
>  **Il formato di file non è compatibile con framework di destinazione corrente. Per convertire il formato file, salvare il file in modo esplicito. Questo messaggio di errore scomparirà dopo aver salvato il file e riaprire la finestra di progettazione.**  
  
##  <a name="BKMK_Versioning"></a> Controllo delle versioni del flusso di lavoro  
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] sono state introdotte numerose nuove funzionalità di controllo delle versioni basate sulla nuova classe <xref:System.Activities.WorkflowIdentity>. La classe <xref:System.Activities.WorkflowIdentity> fornisce agli autori dell'applicazione flusso di lavoro un meccanismo per eseguire il mapping di un'istanza del flusso di lavoro persistente con la relativa definizione.  
  
-   Gli sviluppatori che usano l'hosting di <xref:System.Activities.WorkflowApplication> possono usare la classe <xref:System.Activities.WorkflowIdentity> per consentire l'hosting side-by-side di più versioni di un flusso di lavoro. Le istanze del flusso di lavoro persistenti possono essere caricate usando la nuova classe <xref:System.Activities.WorkflowApplicationInstance>. Successivamente, <xref:System.Activities.WorkflowApplicationInstance.DefinitionIdentity%2A> può essere usato dall'host per fornire la versione corretta della definizione del flusso di lavoro durante la creazione di istanze di <xref:System.Activities.WorkflowApplication>. Per altre informazioni, vedere [uso di WorkflowIdentity e controllo delle versioni](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md) e [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).  
  
-   L'oggetto <xref:System.ServiceModel.WorkflowServiceHost> è ora un host multiversione. Quando viene distribuita una nuova versione di un servizio del flusso di lavoro, vengono create nuove istanze usando il nuovo servizio, mentre le istanze esistenti vengono completate con la versione precedente. Per altre informazioni, vedere [Side-by-Side più versioni in WorkflowServiceHost](../../../docs/framework/wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).  
  
-   Viene introdotto l'aggiornamento dinamico che fornisce un meccanismo per aggiornare la definizione di un'istanza del flusso di lavoro persistente. Per altre informazioni, vedere [aggiornamento dinamico](../../../docs/framework/windows-workflow-foundation/dynamic-update.md) e [come: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md).  
  
-   Uno script del database SqlWorkflowInstanceStoreSchemaUpgrade.sql viene fornito per aggiornare i database di persistenza creati mediante gli script del database di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Questo script aggiorna i database di persistenza di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] per supportare nuove funzionalità di controllo delle versioni introdotte in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Le istanze persistenti del flusso di lavoro nel database sono valori predefiniti specificati per il controllo delle versioni e possono partecipare all'esecuzione side-by-side e all'aggiornamento dinamico. Per altre informazioni, vedere [l'aggiornamento di .NET Framework 4 i database di persistenza al controllo delle versioni del flusso di lavoro di supporto](../../../docs/framework/windows-workflow-foundation/using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).  
  
##  <a name="BKMK_NewActivities"></a> Attività  
 La libreria di attività predefinita contiene nuove attività e funzionalità per le attività esistenti.  
  
###  <a name="BKMK_NoPersistScope"></a> Nopersistscope  
 <xref:System.Activities.Statements.NoPersistScope> è una nuova attività contenitore che impedisce a un flusso di lavoro di essere reso persistente durante l'esecuzione delle attività figlio di NoPersistScope. Ciò si rivela utile in scenari in cui non è necessario che il flusso di lavoro sia reso persistente, ad esempio quando il flusso di lavoro usa risorse specifiche del computer come handle di file o durante le transazioni di database. In precedenza, per impedire la persistenza durante l'esecuzione di un'attività, era necessario un oggetto <xref:System.Activities.NativeActivity> personalizzato in cui veniva usato un oggetto <xref:System.Activities.NoPersistHandle>.  
  
###  <a name="BKMK_NewFlowchartCapabilities"></a> Nuove capacità di diagramma di flusso  
 I diagrammi di flusso vengono aggiornati per [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e dispongono delle nuove funzionalità seguenti:  
  
-   La proprietà `DisplayName` di un'attività <xref:System.Activities.Statements.FlowSwitch%601> o <xref:System.Activities.Statements.FlowDecision> è modificabile. In questo modo, nell'ActivityDesigner verranno illustrate ulteriori informazioni sullo scopo dell'attività.  
  
-   I diagrammi di flusso dispongono di una nuova proprietà denominata <xref:System.Activities.Statements.Flowchart.ValidateUnconnectedNodes%2A>; l'impostazione predefinita per questa proprietà è `False`. Se questa proprietà viene impostata su `True`, i nodi dei diagrammi di flusso non connessi genereranno errori di convalida.  
  
## <a name="support-for-partial-trust"></a>Supporto per l'attendibilità parziale  
 I flussi di lavoro in [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] prevedono un dominio applicazione con attendibilità totale. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], i flussi di lavoro possono operare in un ambiente parzialmente attendibile. In un ambiente parzialmente attendibile, i componenti di terze parti possono essere usati senza concedere loro accesso completo alle risorse dell'host. Di seguito vengono riportati alcuni dei problemi che riguardano i flussi di lavoro in esecuzione con attendibilità parziale:  
  
1.  L'utilizzo dei componenti legacy (regole incluse) contenuti nell'attività di <xref:System.Activities.Statements.Interop> non è supportato con l'attendibilità parziale.  
  
2.  I flussi di lavoro in esecuzione con attendibilità parziale in <xref:System.ServiceModel.WorkflowServiceHost> non sono supportati.  
  
3.  Rendere persistenti le eccezioni in uno scenario parzialmente attendibile rappresenta una potenziale minaccia alla sicurezza. Per disabilitare la persistenza delle eccezioni, un'estensione di tipo <xref:System.Activities.ExceptionPersistenceExtension> deve essere aggiunta al progetto per rifiutare la memorizzazione delle eccezioni. Nell'esempio di codice riportato di seguito viene illustrato come implementare questo tipo.  
  
    ```  
    public class ExceptionPersistenceExtension   
    {  
        public ExceptionPersistenceExtension()   
        {   
            this.PersistExceptions = false;   
        }   
        public bool PersistExceptions { get; set; }   
    }  
    ```  
  
     Se le eccezioni non devono essere serializzate, assicurarsi che le eccezioni vengano usate all'interno di <xref:System.Activities.Statements.NoPersistScope>.  
  
4.  Gli autori di attività devono eseguire l'override <xref:System.Activities.Activity.CacheMetadata%2A> per evitare che il runtime del flusso di lavoro esegua automaticamente la reflection per questo tipo. Gli argomenti e le attività figlio devono essere non Null e <xref:System.Activities.ActivityMetadata.Bind%2A> deve essere chiamato in modo esplicito. Per altre informazioni sull'override <xref:System.Activities.Activity.CacheMetadata%2A>, vedere [esposizione dei dati con CacheMetadata](../../../docs/framework/windows-workflow-foundation/exposing-data-with-cachemetadata.md). Inoltre, le istanze di argomenti che sono di un tipo che è `internal` oppure **privati** devono essere esplicitamente create <xref:System.Activities.Activity.CacheMetadata%2A> per evitare di essere create dalla reflection.  
  
5.  I tipi non utilizzeranno <xref:System.Runtime.Serialization.ISerializable> o <xref:System.SerializableAttribute> per la serializzazione; i tipi che devono essere serializzati devono supportare <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
6.  Le espressioni che usano <xref:System.Activities.Expressions.LambdaValue%601> richiedono <xref:System.Security.Permissions.ReflectionPermissionAttribute.RestrictedMemberAccess%2A>e non funzioneranno con attendibilità parziale. I flussi di lavoro che usano <xref:System.Activities.Expressions.LambdaValue%601> sostituiscono le espressioni con le attività che derivano da <xref:System.Activities.CodeActivity%601>. .  
  
7.  Le espressioni non possono essere compilate usando <xref:System.Activities.XamlIntegration.TextExpressionCompiler> o il compilatore ospitato di Visual Basic in attendibilità parziale, ma le espressioni precedentemente compilate possono essere eseguite.  
  
8.  Un singolo assembly che usa [trasparenza di livello 2](https://aka.ms/Level2Transparency) non è consentito nei [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in attendibilità totale, e [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in attendibilità parziale.  
  
##  <a name="BKMK_NewDesignerCapabilites"></a> Nuove funzionalità di progettazione  
  
###  <a name="BKMK_DesignerSearch"></a> Ricerca della finestra di progettazione  
 Per rendere più gestibili i flussi di lavoro di grandi dimensioni, è ora possibile effettuarvi ricerche in base a parole chiave. Questa funzionalità è disponibile solo in Visual Studio. Questa funzionalità non è disponibile in una finestra di progettazione ospitata nuovamente. Sono disponibili due tipi di ricerche:  
  
-   Ricerca veloce, avviata con **Ctrl + F** oppure **Edit**, **Trova e sostituisci**, **ricerca veloce**.  
  
-   Cerca nei file, avviata con **Ctrl + Maiusc + F** oppure **Edit**, **Trova e sostituisci**, **Cerca nei file**.  
  
 Si noti che la sostituzione non è supportata.  
  
####  <a name="BKMK_QuickFind"></a> Ricerca veloce  
 Le parole chiave ricercate nei flussi di lavoro corrisponderanno agli elementi delle finestre di progettazione seguenti:  
  
-   Proprietà degli oggetti <xref:System.Activities.Activity>, <xref:System.Activities.Statements.FlowNode>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>, nonché altri elementi di controllo del flusso personalizzati.  
  
-   Variabili  
  
-   Argomenti  
  
-   Espressioni  
  
 La ricerca veloce viene effettuata nell'albero <xref:System.Activities.Presentation.Model.ModelItem> della finestra di progettazione. Con la ricerca veloce non verranno individuati gli spazi dei nomi importati nella definizione del flusso di lavoro.  
  
####  <a name="BKMK_FindInFiles"></a> Cerca nei file  
 Le parole chiave ricercate nei flussi di lavoro corrisponderanno al contenuto effettivo dei file del flusso di lavoro. I risultati della ricerca verranno mostrati nel riquadro di visualizzazione Risultati ricerca di Visual Studio. Facendo doppio clic sull'elemento del risultato verrà visualizzata l'attività contenente la corrispondenza nella finestra di progettazione del flusso di lavoro.  
  
###  <a name="BKMK_VariableDeleteContextMenu"></a> Eliminare i menu di scelta rapida nella finestra di progettazione variabili e degli argomenti  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] le variabili e gli argomenti potevano essere eliminati solo nella finestra di progettazione mediante la tastiera. A partire da [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] le variabili e gli argomenti possono essere eliminati usando il menu di scelta rapida.  
  
 Nella schermata seguente è illustrato il menu di scelta rapida della finestra di progettazione delle variabili e degli argomenti.  
  
 ![Variabili e menu di scelta rapida della finestra di progettazione argomenti](../../../docs/framework/windows-workflow-foundation/media/designercontextmenu.png "DesignerContextMenu")  
  
###  <a name="BKMK_AutoSurround"></a> Auto-surround con sequenza  
 Poiché un flusso di lavoro o determinate attività contenitore (ad esempio <xref:System.Activities.Statements.NoPersistScope>) potevano contenere solo un'unica attività Body, l'aggiunta di una seconda attività richiedeva allo sviluppatore di eliminare la prima attività, di aggiungere un'attività <xref:System.Activities.Statements.Sequence> e, successivamente, di aggiungere entrambe le attività all'attività Sequence. A partire da [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], quando si aggiunge una seconda attività all'area di progettazione, verrà creata automaticamente un'attività `Sequence` per eseguire il wrapping di entrambe le attività.  
  
 La schermata riportata di seguito mostra un'attività di `WriteLine` in `Body` di `NoPersistScope`.  
  
 ![Automatico&#45;racchiudere il percorso di rilascio](../../../docs/framework/windows-workflow-foundation/media/autosurround1.png "AutoSurround1")  
  
 La schermata riportata di seguito mostra l'attività automaticamente creata di `Sequence` in `Body` quando un secondo `WriteLine` viene rilasciato sotto il primo.  
  
 ![Attività sequence creata automaticamente](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")  
  
###  <a name="BKMK_PanMode"></a> Modalità dettaglio  
 Per spostarsi più facilmente in un flusso di lavoro di grandi dimensioni nella finestra di progettazione è possibile abilitare la modalità dettaglio, consentendo allo sviluppatore di selezionare e trascinare la parte visibile del flusso di lavoro, anziché dover usare le barre di scorrimento. Il pulsante per attivare la modalità dettaglio si trova nell'angolo inferiore destro della finestra di progettazione.  
  
 Nella schermata seguente viene illustrato il pulsante della modalità dettaglio posizionato nell'angolo inferiore destro della finestra di progettazione del flusso di lavoro.  
  
 ![Pulsante mano nella finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/media/panbutton.png "PanButton")  
  
 Per ottenere il dettaglio della finestra di progettazione del flusso di lavoro è anche possibile usare il pulsante centrale del mouse o la barra spaziatrice.  
  
###  <a name="BKMK_MultiSelect"></a> Selezione multipla  
 È possibile selezionare più attività alla volta trascinando un rettangolo attorno a esse (quando la modalità dettaglio non è abilitata) o tenendo premuto CTRL e facendo clic sulle attività desiderate una alla volta.  
  
 Le selezioni di più attività possono anche essere trascinate e rilasciate all'interno della finestra di progettazione, nonché usate con il menu di scelta rapida.  
  
###  <a name="BKMK_DocumentOutline"></a> Visualizzazione della struttura degli elementi del flusso di lavoro  
 Per consentire uno spostamento più semplice nei flussi di lavoro gerarchici, i componenti di un flusso di lavoro vengono visualizzati in una visualizzazione ad albero. Visualizzazione della struttura viene visualizzata nei **struttura documento** visualizzazione. Per aprire questa visualizzazione, nel menu principale, selezionare **View**, **Other Windows**, **struttura documento**, oppure premere Ctrl W, U. Facendo clic su un nodo nella visualizzazione Struttura verrà visualizzata l'attività corrispondente nella finestra di progettazione del flusso di lavoro e la visualizzazione Struttura verrà aggiornata in modo da mostrare le attività selezionate nella finestra di progettazione.  
  
 Lo screenshot seguente del flusso di lavoro completata dal [esercitazione introduttiva su](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) Mostra la visualizzazione struttura con un flusso di lavoro sequenza.  
  
 ![Visualizzazione nella finestra di progettazione del flusso di lavoro struttura](../../../docs/framework/windows-workflow-foundation/media/outlineviewinworkflowdesigner.jpg "OutlineViewinWorkflowDesigner")  
  
###  <a name="BKMK_CSharpExpressions"></a> Espressioni c#  
 In precedenza a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], tutte le espressioni nei flussi di lavoro potevano essere scritte solo in Visual Basic. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] le espressioni di Visual Basic vengono usate solo per i progetti creati tramite questo linguaggio. Nei progetti Visual C# viene ora usato C# per le espressioni. È ora disponibile un editor espressioni C# completamente funzionale con funzionalità quali l'evidenziazione della grammatica e Intellisense. I progetti di flussi di lavoro C# creati in versioni precedenti che utilizzavano espressioni di Visual Basic continueranno a funzionare.  
  
 Le espressioni C# vengono convalidate in fase di progettazione. Gli errori nelle espressioni C# verranno contrassegnati con una sottolineatura ondulata rossa.  
  
 Per altre informazioni sulle espressioni di c#, vedere [espressioni c#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).  
  
###  <a name="BKMK_Visibility"></a> Maggiore controllo della visibilità della barra della shell e intestazione elementi  
 In una finestra di progettazione ospitata nuovamente, alcuni dei controlli dell'interfaccia utente standard possono non essere appropriati per un determinato flusso di lavoro e, pertanto, è possibile disattivarli. In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] questa personalizzazione è supportata solo dalla barra della shell nella parte inferiore della finestra di progettazione. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] la visibilità degli elementi dell'intestazione della shell nella parte superiore della finestra di progettazione può essere regolata impostando la proprietà <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> con il valore <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> appropriato.  
  
###  <a name="BKMK_AutoConnect"></a> Connessione e inserimento automatici nei flussi di lavoro macchina a stati e diagramma di flusso  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] le connessioni tra i nodi di un flusso di lavoro del diagramma di flusso devono essere aggiunte manualmente. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] i nodi del diagramma di flusso e della macchina a stati dispongono di punti di connessione automatica che diventano visibili quando un'attività viene trascinata dalla casella degli strumenti nell'area di progettazione. Rilasciando un'attività in uno di questi punti, viene automaticamente aggiunta insieme alla connessione necessaria.  
  
 Nella schermata seguente vengono illustrati i punti di associazione che diventano visibili quando un'attività viene trascinata dalla casella degli strumenti.  
  
 ![Nodo iniziale del diagramma di flusso che illustra i punti di connessione automatica](../../../docs/framework/windows-workflow-foundation/media/autoconnect1.png "Autoconnect1")  
  
 Le attività possono anche essere trascinate nelle connessioni tra i nodi e gli stati del diagramma di flusso per inserire automaticamente un nodo tra altri due. Nella schermata seguente viene illustrata la linea di connessione evidenziata in cui è possibile trascinare e rilasciare le attività dalla casella degli strumenti.  
  
 ![Automatico&#45;inserire handle per l'eliminazione di attività](../../../docs/framework/windows-workflow-foundation/media/autoinsert.png "Autoinsert")  
  
###  <a name="BKMK_Annotations"></a> Annotazioni della finestra di progettazione  
 Per semplificare lo sviluppo di flussi di lavoro di grandi dimensioni, la finestra di progettazione supporta ora l'aggiunta di annotazioni per consentire di tenere traccia del processo di progettazione. Le annotazioni possono essere aggiunte ad attività, stati, nodi del diagramma di flusso, variabili e argomenti. Nella schermata seguente è illustrato il menu di scelta rapida usato per aggiungere annotazioni alla finestra di progettazione.  
  
 ![Menu di scelta rapida annotazione](../../../docs/framework/windows-workflow-foundation/media/annotationdialog.png "annotationdialog")  
  
### <a name="debugging-states"></a>Stati di debug  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] gli elementi di non attività non potevano supportare punti di interruzione del debug poiché non erano unità di esecuzione. Questa versione fornisce un meccanismo per aggiungere punti di interruzione agli oggetti <xref:System.Activities.Statements.State>. Se un punto di interruzione è impostato su un oggetto <xref:System.Activities.Statements.State>, l'esecuzione verrà interrotta quando viene eseguita la transizione dello stato, prima della pianificazione delle attività o dei trigger di inserimento.  
  
###  <a name="BKMK_ActivityDelegates"></a> Definire e usare gli oggetti ActivityDelegate nella finestra di progettazione  
 Le attività in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] utilizzavano gli oggetti <xref:System.Activities.ActivityDelegate> per esporre i punti di esecuzione dove altre parti del flusso di lavoro potevano interagire con l'esecuzione di un flusso di lavoro, tuttavia l'uso dei punti di esecuzione richiedeva, generalmente, una grande quantità di codice. In questa versione gli sviluppatori possono definire e usare delegati di attività tramite la finestra di progettazione del flusso di lavoro. Per altre informazioni, vedere [Procedura: Definire e usare delegati di attività nella finestra di progettazione del flusso di lavoro](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer).  
  
###  <a name="BKMK_BuildTimeValidation"></a> Convalida in fase di compilazione  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] gli errori di convalida del flusso di lavoro non venivano contati come errori di compilazione durante l'esecuzione di questa operazione per un progetto di flusso di lavoro. In questo modo, la compilazione di un progetto di flusso di lavoro poteva essere completata correttamente anche in presenza di errori di convalida del flusso di lavoro. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] gli errori di convalida del flusso di lavoro comportano il mancato completamento della compilazione.  
  
###  <a name="BKMK_DesignTimeValidation"></a> Convalida in background in fase di progettazione  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] i flussi di lavoro venivano convalidati come processo in primo piano. Questa condizione poteva potenzialmente bloccare l'interfaccia utente durante processi di convalida complessi o lunghi. La convalida del flusso di lavoro viene ora effettuata in un thread in background, pertanto l'interfaccia utente non viene bloccata.  
  
###  <a name="BKMK_ViewState"></a> Stato di visualizzazione che si trova in un percorso separato nei file XAML  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] le informazioni sullo stato di visualizzazione per un flusso di lavoro sono archiviate nel file XAML in molti percorsi diversi. Questa condizione è poco pratica per gli sviluppatori che desiderano leggere direttamente i file XAML o scrivere codice per rimuovere le informazioni sullo stato di visualizzazione. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], le informazioni sullo stato di visualizzazione nel file XAML viene serializzate come elemento separato nel file XAML.  Gli sviluppatori possono facilmente individuare e modificare le informazioni sullo stato di visualizzazione di un'attività oppure rimuovere completamente lo stato di visualizzazione.  
  
###  <a name="BKMK_ExpressionExtensibility"></a> Estendibilità dell'espressione  
 In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] gli sviluppatori possono creare le proprie espressioni, che possono essere inserite nella finestra di progettazione del flusso di lavoro, e acquisire una relativa esperienza di creazione.  
  
###  <a name="BKMK_BackwardCompatRehostedDesigner"></a> Acconsenti esplicitamente di funzionalità del flusso di lavoro 4.5 nella finestra di progettazione ospitata nuovamente  
 Per mantenere la compatibilità con le versioni precedenti, alcune nuove funzionalità incluse in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] non vengono abilitate per impostazione predefinita nella finestra di progettazione ospitata nuovamente. In questo modo si garantisce che le applicazioni esistenti in cui viene usata la finestra di progettazione ospitata nuovamente non vengano interrotte in caso di aggiornamento alla versione più recente. Per abilitare le nuove funzionalità nella finestra di progettazione ospitata nuovamente, impostare la proprietà <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> su ".NET Framework 4.5" oppure impostare singoli membri dell'oggetto <xref:System.Activities.Presentation.DesignerConfigurationService> per abilitare singole funzionalità.  
  
##  <a name="BKMK_NewWFModels"></a> Nuovi modelli di sviluppo del flusso di lavoro  
 Oltre ai modelli di sviluppo dei flussi di lavoro del diagramma di flusso e sequenziale, in questa versione sono inclusi i flussi di lavoro macchina a stati e i servizi dei flussi di lavoro con priorità al contratto ("contract-first").  
  
###  <a name="BKMK_StateMachine"></a> Flussi di lavoro macchina a stati  
 I flussi di lavoro macchina a stati sono stati introdotti come parte di .NET Framework 4, versione 4.0.1 nel [Microsoft .NET Framework 4 Platform Update 1](https://go.microsoft.com/fwlink/?LinkID=215092). In questo aggiornamento sono incluse numerose nuove classi e attività che hanno consentito agli sviluppatori di creare i flussi di lavoro macchina a stati. Queste classi e attività sono state aggiornate per [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Gli aggiornamenti includono:  
  
1.  Possibilità di impostare punti di interruzione negli stati  
  
2.  Possibilità di copiare e incollare transizioni nella finestra di progettazione del flusso di lavoro  
  
3.  Supporto della finestra di progettazione per la creazione di transizioni con trigger condivisi  
  
4.  Attività usate per creare i flussi di lavoro macchina a stati, incluse <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> e <xref:System.Activities.Statements.Transition>  
  
 Lo screenshot seguente illustra il flusso di lavoro alla macchina sullo stato completato il [esercitazione introduttiva](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) passaggio [come: Creare un flusso di lavoro macchina a stati](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md).  
  
 ![Flusso di lavoro macchina a stati completo](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 Per altre informazioni sulla creazione di flussi, vedere [flussi](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).  
  
###  <a name="BKMK_ContractFirst"></a> Sviluppo di flussi di lavoro del contratto  
 Lo strumento di sviluppo di flussi di lavoro contratto consente allo sviluppatore di progettare un contratto in code prima di tutto, quindi, con pochi clic in Visual Studio, generare automaticamente un modello di attività nella casella degli strumenti che rappresenta ogni operazione. Queste attività vengono quindi usate per creare un flusso di lavoro che implementa le operazioni definite dal contratto. La finestra di progettazione del flusso di lavoro convaliderà il servizio di quest'ultimo per garantire che queste operazioni vengano implementate e che la firma del flusso di lavoro corrisponda a quella del contratto. Lo sviluppatore può inoltre associare un servizio del flusso di lavoro a una raccolta di contratti implementati. Per altre informazioni sullo sviluppo di flussi di lavoro contratto di servizio, vedere [come: Creare un servizio del flusso di lavoro che utilizza un contratto di servizio esistente](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).
