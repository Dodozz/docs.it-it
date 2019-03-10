---
title: Ambito e visibilità della definizione di attività
ms.date: 03/30/2017
ms.assetid: ccdffa07-9503-4eea-a61b-17f1564368b7
ms.openlocfilehash: 7b09ac6d27dd3be502c98ce3ac0a90f636714fc2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723842"
---
# <a name="activity-definition-scoping-and-visibility"></a>Ambito e visibilità della definizione di attività
In modo analogo all'ambito e alla visibilità di un oggetto, per ambito di definizione e visibilità di attività si intende la capacità di altri oggetti o attività di accedere ai membri dell'attività stessa. La definizione di attività viene eseguita tramite le implementazioni seguenti.  
  
1.  Definizione dei membri (oggetti <xref:System.Activities.Argument>, <xref:System.Activities.Variable> e <xref:System.Activities.ActivityDelegate> e attività figlio) che un'attività espone ai propri utenti.  
  
2.  Implementazione della logica di esecuzione dell'attività.  
  
 L'implementazione può coinvolgere membri non esposti a utenti dell'attività che costituiscono piuttosto dettagli dell'implementazione.  In modo analogo alla definizione di tipo, il modello di attività consente a un autore di qualificare la visibilità di un membro dell'attività in relazione alla specifica dell'attività da definire.  Tale visibilità consente di controllare aspetti dell'utilizzo del membro, ad esempio l'ambito dei dati.  
  
## <a name="scope"></a>Ambito  
 Oltre all'ambito dei dati, la visibilità del modello di attività può limitare l'accesso ad altri aspetti dell'attività, ad esempio la convalida, il debug, il rilevamento o l'analisi. Le proprietà di esecuzione usano visibilità e ambito per vincolare caratteristiche dell'esecuzione a un particolare ambito di definizione, mentre le radici secondarie usano visibilità e ambito per vincolare lo stato acquisito da un oggetto <xref:System.Activities.Statements.CompensableActivity> all'ambito di definizione in cui vengono usate le attività compensabili.  
  
## <a name="definition-and-usage"></a>Definizione e utilizzo  
 Creazione di nuove attività che eredita dalle classi di attività di base e usando le attività eseguite da un flusso di lavoro viene scritta la [libreria attività incorporata](net-framework-4-5-built-in-activity-library.md). Per usare un'attività, l'autore deve configurare la visibilità di ogni componente della relativa definizione.  
  
### <a name="activity-members"></a>Membri dell'attività  
 Il modello di attività definisce gli argomenti, le variabili, i delegati e le attività figlio resi disponibili agli utenti dall'attività stessa. Ciascuno di questi membri può essere dichiarato come `public` o `private`. I membri pubblici vengono configurati dall'utente dell'attività, mentre i membri configurati come `private` usano un'implementazione definita dall'autore dell'attività. Le regole di visibilità per l'ambito dei dati sono le seguenti.  
  
1.  Membri pubblici e membri pubblici di attività figlio pubbliche possono fare riferimento a variabili pubbliche.  
  
2.  Membri privati e membri pubblici di attività figlio pubbliche possono fare riferimento ad argomenti e variabili private.  
  
 Un membro che può essere impostato dall'utente di un'attività non deve mai essere reso privato.  
  
### <a name="authoring-models"></a>Modalità di creazione  
 Le attività personalizzate vengono definite tramite <xref:System.Activities.NativeActivity>, <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity> o <xref:System.Activities.AsyncCodeActivity>. Attività che derivano da tali classi possono esporre tipi di membro diversi con visibilità differenti.  
  
#### <a name="nativeactivity"></a>NativeActivity  
 Le attività che derivano da <xref:System.Activities.NativeActivity> si comportano in base a un codice imperativo e possono essere definite facoltativamente tramite attività esistenti. Se le attività vengono derivate da <xref:System.Activities.NativeActivity>, è possibile accedere a tutte le funzionalità esposte dal runtime. Ad eccezione degli argomenti, che possono essere dichiarati solo come `public`, ogni membro di attività di questo tipo può essere definito tramite visibilità pubblica o privata.  
  
 I membri di classi derivate da <xref:System.Activities.NativeActivity> vengono dichiarati in fase di esecuzione tramite lo struct <xref:System.Activities.NativeActivityMetadata> passato al metodo <xref:System.Activities.NativeActivity.CacheMetadata%2A>.  
  
#### <a name="activity"></a>Attività  
 Le attività create tramite <xref:System.Activities.Activity> dispongono di un comportamento strettamente basato sulla composizione di altre attività. Alla classe <xref:System.Activities.Activity> è associata un'attività figlio di implementazione, ottenuta in fase di esecuzione usando <xref:System.Activities.Activity.Implementation%2A>. Un'attività che deriva da <xref:System.Activities.Activity> può definire variabili e argomenti pubblici nonché attività ed elementi ActivityDelegates importati.  
  
 Attività ed elementi ActivityDelegates importati vengono dichiarati come figli pubblici dell'attività, ma non possono essere pianificati direttamente dall'attività. Queste informazioni vengono usate durante la convalida per evitare di eseguire convalide rispetto agli elementi padre in percorsi in cui l'attività non verrà mai eseguita. In modo analogo ai figli pubblici, i figli importati possono essere pianificati dall'implementazione dell'attività ed è possibile farvi riferimento dall'implementazione stessa. Ciò significa che un'attività che importa un'attività denominata Attività1 può contenere un elemento <xref:System.Activities.Statements.Sequence> nell'implementazione che pianifica Attività1.  
  
#### <a name="codeactivity-asynccodeactivity"></a>CodeActivity/ AsyncCodeActivity  
 Questa classe di base viene usata per la creazione del comportamento in codice imperativo. Le attività che derivano da questa classe possono accedere solo agli argomenti che espongono. Ciò significa che i soli membri che queste attività possono esporre sono argomenti pubblici. A tali attività non si applica alcun altro membro o visibilità.  
  
#### <a name="summary-of-visibilities"></a>Riepilogo delle visibilità  
 Nella tabella seguente vengono riepilogate le informazioni fornite in precedenza in questa sezione.  
  
|Tipo di membro|NativeActivity|Attività|CodeActivity/ AsyncCodeActivity|  
|-----------------|--------------------|--------------|--------------------------------------|  
|Argomenti|Pubblico/ privato|Public|non applicabile|  
|Variabili|Pubblico/ privato|Public|non applicabile|  
|Attività figlio|Pubblico/ privato|Pubblico, un figlio privato fisso definito nell'Implementazione|non applicabile|  
|ActivityDelegates|Pubblico/ privato|Public|non applicabile|  
  
 In generale, un membro che non può essere impostato dall'utente di un'attività non deve essere reso pubblico.  
  
### <a name="execution-properties"></a>Proprietà di esecuzione  
 In alcuni scenari è utile definire l'ambito di una particolare proprietà di esecuzione come i figli pubblici di un'attività. Nella raccolta <xref:System.Activities.ExecutionProperties> questa operazione può essere eseguita tramite il metodo <xref:System.Activities.ExecutionProperties.Add%2A> che dispone di un parametro di tipo Boolean che indica se l'ambito di una proprietà specifica è definito da tutti i figli o solo da quelli pubblici. Se questo parametro viene impostato su `true`, la proprietà sarà visibile solo a membri pubblici e ai membri pubblici dei relativi figli pubblici.  
  
### <a name="secondary-roots"></a>Radici secondarie  
 Una radice secondaria è il meccanismo interno del runtime per la gestione dello stato per attività di compensazione. Quando l'esecuzione di un oggetto <xref:System.Activities.Statements.CompensableActivity> è completata, lo stato non viene immediatamente pulito ma viene gestito dal runtime in una radice secondaria fino a quando la compensazione non è stata completata. Gli ambienti del percorso acquisiti con la radice secondaria corrispondono all'ambito di definizione in cui viene usata l'attività compensabile.
