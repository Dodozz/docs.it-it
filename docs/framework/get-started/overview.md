---
title: Panoramica di .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- application development [.NET Framework]
- common language runtime
- common language runtime, about
- common language runtime, overview
ms.assetid: 29848c96-fc36-462d-8072-ba223a40b697
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f50a469327a06eabdb6a80821203f2222dcd2921
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878045"
---
# <a name="overview-of-the-net-framework"></a>Panoramica di .NET Framework

.NET Framework è una tecnologia che supporta la compilazione e l'esecuzione di app di ultima generazione e servizi Web XML. .NET Framework è progettata per ottenere gli obiettivi indicati di seguito:

- Fornire un ambiente di programmazione orientato agli oggetti coerente, sia che il codice degli oggetti sia memorizzato ed eseguito localmente, eseguito localmente ma distribuito su Internet oppure eseguito in modalità remota.

- Fornire un ambiente di esecuzione del codice che minimizzi la distribuzione del software e i conflitti di versioni.

- Fornire un ambiente di esecuzione del codice che permetta un'esecuzione sicura anche dei codici creati da produttori sconosciuti o semi-trusted.

- Fornire un ambiente di esecuzione del codice che elimini i problemi di prestazioni degli ambienti basati su script o interpretati.

- Rendere coerente l'esperienza dello sviluppatore su app di tipi diversi, dalle app basate su Windows a quelle basate sul Web.

- Compilare tutte le comunicazioni in base agli standard di settore, per garantire l'integrazione del codice basato su .NET Framework con qualsiasi altro codice.

> [!NOTE]
> Per un'introduzione generale a .NET Framework per utenti e sviluppatori, vedere [Introduzione](../../../docs/framework/get-started/index.md).

.NET Framework è costituito da Common Language Runtime (CLR) e dalla libreria di classi .NET Framework. Common Language Runtime rappresenta la base di .NET Framework e può essere considerato come un agente che gestisce il codice in fase di esecuzione, fornendo servizi di base quali gestione della memoria, gestione di thread e servizi remoti e attivando nel contempo una rigida indipendenza dai tipi e altre forme di accuratezza del codice che garantiscono sicurezza ed efficienza. Il concetto di gestione del codice è infatti un principio fondamentale di runtime. Il codice destinato al runtime è definito codice gestito, mentre quello non destinato al runtime è definito codice non gestito. La libreria di classi è una raccolta completa e orientata agli oggetti di tipi riusabili, da usare per lo sviluppo di app, da quelle tradizionali della riga di comando o con interfaccia utente grafica (GUI, Graphical User Interface) a quelle basate sulle più recenti innovazioni offerte da ASP.NET, quali Web Form e servizi Web XML.

.NET Framework può essere ospitato da componenti non gestiti che caricano Common Language Runtime nei processi e avviano l'esecuzione del codice gestito, creando un ambiente software in grado di sfruttare funzionalità sia gestite che non gestite. Oltre a includere vari host di runtime, .NET Framework supporta lo sviluppo di host di runtime di altri produttori.

In ASP.NET è ad esempio disponibile il runtime per fornire un ambiente lato server scalabile per il codice gestito. È possibile usare ASP.NET direttamente con il runtime per attivare app ASP.NET e servizi Web XLM, entrambi trattati più avanti in questo argomento.

Internet Explorer è un esempio di app non gestita che contiene il runtime in forma di estensione di tipo MIME. L'hosting del runtime tramite Internet Explorer consente di incorporare componenti gestiti o controlli Windows Form nei documenti HTML. Questo tipo di hosting consente l'uso del codice mobile gestito, ma con miglioramenti significativi che solo il codice gestito può offrire, come l'esecuzione parzialmente attendibile e l'archiviazione di file isolati.

L'illustrazione seguente visualizza la relazione di Common Language Runtime e della libreria di classi con le app e con l'intero sistema. Viene inoltre mostrato come opera il codice gestito all'interno di un'architettura più ampia.

![Screenshot che visualizza il funzionamento del codice gestito all'interno di un'architettura più ampia.](./media/overview/language-runtime-class-library-relationship.gif)

Nelle sezioni seguenti vengono descritte più dettagliatamente le principali funzionalità di .NET Framework.

## <a name="features-of-the-common-language-runtime"></a>Funzionalità di Common Language Runtime

Common Language Runtime gestisce la memoria, l'esecuzione di thread, l'esecuzione del codice, la verifica della sicurezza del codice, la compilazione e altri servizi di sistema. Queste funzionalità sono intrinseche al codice gestito che viene eseguito sul Common Language Runtime.

Per quanto riguarda la sicurezza, ai componenti gestiti vengono assegnati vari gradi di attendibilità in base a diversi fattori fra cui l'origine, ad esempio Internet, una rete aziendale o un computer locale. Un componente gestito quindi può essere o non essere in grado di eseguire operazioni di accesso a file, accesso al registro di sistema o altre funzioni riservate, anche se usato nella stessa app attiva.

L'efficienza del codice è inoltre attivata dal runtime mediante l'implementazione di una rigida infrastruttura di verifica di tipi e codice denominata sistema di tipi comuni (CTS, Common Type System). CTS assicura che tutto il codice gestito sia auto descrittivo. I vari compilatori di linguaggio Microsoft e di terze parti generano codice gestito conforme a CTS. Questo significa che il codice gestito può utilizzare altre istanze e altri tipi gestiti, imponendo nel contempo, in modo rigoroso la fedeltà dei tipi e l'indipendenza dai tipi.

Inoltre l'ambiente gestito di runtime elimina molti problemi comuni di software. Nel runtime vengono ad esempio automaticamente gestiti il layout di oggetti e i riferimenti a oggetti, i quali vengono rilasciati quando non sono più utilizzati. Questa gestione automatica della memoria risolve i due errori più comuni delle app, ovvero le perdite di memoria e i riferimenti alla memoria non validi.

Grazie al runtime inoltre la produttività dello sviluppatore viene accelerata. I programmatori possono ad esempio scrivere app nel linguaggio di sviluppo scelto e sfruttare tutti i vantaggi del runtime, della libreria di classi e dei componenti scritti in altri linguaggi da altri sviluppatori. Questo risultato può essere raggiunto da qualsiasi fornitore di compilatori che sceglie di utilizzare il runtime. I compilatori di linguaggio destinati a .NET Framework rendono disponibili le funzionalità di .NET Framework al codice esistente scritto in tale linguaggio, facilitando notevolmente il processo di migrazione delle app esistenti.

Benché il runtime sia progettato per i programmi software futuri, supporta anche quelli attualmente disponibili e meno recenti. L'interoperabilità tra codice gestito e non gestito consente agli sviluppatori di continuare a utilizzare i componenti COM e le DLL che risultano necessari.

Il runtime è progettato per migliorare le prestazioni. Sebbene Common Language Runtime fornisca molti servizi runtime standard, il codice gestito non viene mai interpretato. Una funzionalità denominata compilazione JIT (Just In Time) consente l'esecuzione di tutto il codice gestito nel linguaggio macchina nativo del sistema su cui è in esecuzione. Contemporaneamente, il gestore di memoria impedisce la frammentazione della memoria e aumenta la rintracciabilità dei riferimenti della memoria per migliorare ulteriormente le prestazioni.

L'hosting del runtime può essere infine eseguito da app lato server a elevate prestazioni, quali Microsoft SQL Server e Internet Information Services (IIS). Questa infrastruttura consente di utilizzare il codice gestito per scrivere logica aziendale personalizzata, continuando a sfruttare le prestazioni superiori dei migliori server aziendali del settore che supportano l'hosting del runtime.

## <a name="net-framework-class-library"></a>Libreria di classi .NET Framework

La libreria di classi .NET Framework è una raccolta di tipi riutilizzabili che si integrano strettamente con Common Language Runtime. La libreria di classi è orientata agli oggetti e offre tipi dai quali il codice gestito deriva le funzionalità. In questo modo non solo viene semplificato l'uso dei tipi .NET Framework, ma si riduce anche il tempo necessario all'apprendimento delle nuove funzionalità di .NET Framework. È anche possibile integrare in modo uniforme i componenti di altri produttori nelle classi di .NET Framework.

Ad esempio le classi di raccolte .NET Framework implementano un set di interfacce per lo sviluppo di classi di raccolte personalizzate. Le classi di raccolte personalizzate si integrano perfettamente con le classi in .NET Framework.

Come ci si aspetta da una libreria di classi orientata agli oggetti, i tipi .NET Framework consentono di effettuare una gamma di attività comuni di programmazione, incluse operazioni quali la gestione di stringhe, la raccolta di dati, la connettività al database e l'accesso a file. Oltre a queste attività comuni, la libreria di classi include tipi che supportano vari scenari di sviluppo specializzati. Usare .NET Framework per sviluppare i seguenti tipi di app e servizi:

- App console. Vedere [Compilazione di applicazioni console](../../../docs/standard/building-console-apps.md).

- App GUI Windows (Windows Forms). Vedere [Windows Form](../../../docs/framework/winforms/index.md).

- App Windows Presentation Foundation (WPF). Vedere [Windows Presentation Foundation](../../../docs/framework/wpf/index.md).

- App ASP.NET. Vedere [Applicazioni Web con ASP.NET](../../../docs/framework/develop-web-apps-with-aspnet.md).

- Servizi Windows. Vedere [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md).

- App orientate ai servizi che usano Windows Communication Foundation (WCF). Vedere [Applicazioni orientate ai servizi con WCF](../../../docs/framework/wcf/index.md).

- App basate sul flusso di lavoro che usano Windows Workflow Foundation (WF). Vedere [Windows Workflow Foundation](../windows-workflow-foundation/index.md).

Le classi Windows Form sono un insieme completo di tipi riusabili che semplifica notevolmente lo sviluppo di GUI Windows. Se si scrive un'app Web Form ASP.NET è possibile usare le classi Web Form.

## <a name="see-also"></a>Vedere anche

- [Requisiti di sistema](../../../docs/framework/get-started/system-requirements.md)
- [Guida all'installazione](../../../docs/framework/install/index.md)
- [Guida di sviluppo](../../../docs/framework/development-guide.md)
- [Strumenti](../../../docs/framework/tools/index.md)
- [Esempi ed esercitazioni per .NET](../../samples-and-tutorials/index.md)
- [Libreria di classi .NET Framework](https://go.microsoft.com/fwlink/?LinkID=227195)
