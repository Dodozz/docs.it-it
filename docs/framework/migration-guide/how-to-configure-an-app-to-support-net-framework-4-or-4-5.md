---
title: "Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive"
ms.date: 03/30/2017
helpviewer_keywords:
- configuring apps to support .NET Framework
- .NET Framework, configuring apps
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 186297c050d81eca130b751c46303083ff025f22
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636113"
---
# <a name="how-to-configure-an-app-to-support-net-framework-4-or-later-versions"></a>Procedura: Configurare un'app per supportare .NET Framework 4 o versioni successive

Per tutte le app che ospitano Common Language Runtime (CLR) è necessario che venga avviato o *attivato* CLR per eseguire codice gestito. In genere, un'app .NET Framework viene eseguita sulla versione di CLR in cui è stata sviluppata, ma è possibile modificare questo comportamento per le app desktop tramite un file di configurazione (talvolta definito file app.config). Tuttavia, non è possibile modificare il comportamento di attivazione predefinito per le applicazioni Windows Store o Windows Phone tramite un file di configurazione specifico. In questo articolo viene illustrato come consentire l'esecuzione dell'app desktop in un'altra versione di .NET Framework e viene fornito un esempio per l'esecuzione nella versione 4 o versioni successive.

 La versione di .NET Framework in cui viene eseguita un'app è determinata nell'ordine seguente:

- File di configurazione.

     Se il file di configurazione dell'applicazione include voci [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) che specificano una o più versioni di .NET Framework e una di queste si trova nel computer dell'utente, l'app verrà eseguita in tale versione. Il file di configurazione legge le voci [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) nell'ordine in cui sono elencate e usa la prima versione di .NET Framework elencata presente nel computer dell'utente. Usare l'elemento [\<requiredRuntime>](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) per la versione 1.0.

- Versione compilata.

     Se il file di configurazione non è presente, ma la versione di .NET Framework con cui è stata creata l'app si trova nel computer dell'utente, l'app verrà eseguita in tale versione.

- Versione più recente installata.

     Se la versione di .NET Framework con la quale è stata compilata l'app non è presente e in un file di configurazione non è specificata alcuna versione in un elemento [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md), l'app tenterà l'esecuzione nella versione più recente di .NET Framework presente nel computer dell'utente.

     Tuttavia, le app .NET Framework 1.0, 1.1, 2.0, 3.0 e 3.5 non vengono automaticamente eseguite in .NET Framework 4 o versioni successive e, in alcuni casi, l'utente potrebbe visualizzare un errore e ricevere la richiesta di installare .NET Framework 3.5. Il comportamento di attivazione potrebbe inoltre dipendere dal sistema operativo dell'utente, poiché versioni diverse del sistema Windows includono versioni diverse di .NET Framework. Se l'app supporta .NET Framework versione 3.5 e 4 o successive, è consigliabile indicare questa opzione con più voci nel file di configurazione onde evitare errori di inizializzazione di .NET Framework. Per altre informazioni, vedere [Versioni e dipendenze](versions-and-dependencies.md).

 È inoltre possibile configurare le app .NET Framework 3.5 in .NET Framework 4 o versioni successive, anche nei computer in cui è installato .NET Framework 3.5, per sfruttare i miglioramenti nelle prestazioni nelle versioni 4 e versioni successive.

> [!IMPORTANT]
> È consigliabile testare sempre l'app in ogni versione di .NET Framework supportata. Vedere [Compatibilità tra le versioni](version-compatibility.md) per informazioni su come aggiornare l'applicazione per il supporto di versioni successive di .NET Framework.

 Per informazioni sulla modifica delle app .NET Framework 1.0 e 1.1 per il supporto di Windows 7 e Windows 8, vedere [Migrazione da .NET Framework 1.1](migrating-from-the-net-framework-1-1.md).

## <a name="to-configure-your-app-to-run-on-the-net-framework-4-or-later-versions"></a>Per configurare un'app per eseguirla in. NET Framework 4 o versioni successive

1. Aggiungere o individuare il file di configurazione per il progetto .NET Framework. Il file di configurazione per un'app si trova nella stessa directory e ha lo stesso nome dell'app, ma presenta un'estensione config. Per un'app denominata MyExecutable.exe, ad esempio, il file di configurazione deve essere MyExecutable.exe.config.

     Per aggiungere un file di configurazione, nella barra dei menu di Visual Studio scegliere **Progetto**, **Aggiungi nuovo elemento**. Scegliere **Generale** nel riquadro sinistro, quindi **File di configurazione**. Denominare il file di configurazione *appName*.exe.config. Queste opzioni di menu non sono disponibili per progetti di applicazioni Windows Store o Windows Phone, poiché non è possibile modificare i criteri di attivazione in queste piattaforme.

2. Aggiungere l'elemento [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) al file di configurazione dell'applicazione come segue:

    ```xml
    <configuration>
      <startup>
        <supportedRuntime version="<version>"/>
      </startup>
    </configuration>
    ```

     dove *\<version>* indica la versione CLR che si allinea alla versione di .NET Framework supportata dall'app. Utilizzare le stringhe seguenti:

    - .NET Framework 1.0: "v1.0.3705"

    - .NET Framework 1.1: "v1.1.4322"

    - .NET Framework 2.0, 3.0 e 3.5: "v2.0.50727"

    - .NET Framework 4 e versioni successive: "v4.0"

     È possibile aggiungere più elementi [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) elencati in ordine di preferenza, per specificare il supporto per più versioni di .NET Framework.

 Nella tabella seguente viene illustrato il modo in cui le impostazioni del file di configurazione dell'applicazione e le versioni di .NET Framework installate in un computer determinano la versione in cui viene eseguita un'app .NET Framework 3.5. Gli esempi sono specifici di un'applicazione .NET Framework 3.5, ma una logica simile può essere utilizzata anche con applicazioni di destinazione create con versioni di .NET Framework precedenti. Il numero di versione di .NET Framework 2.0 (v2.0.50727) viene utilizzato per specificare .NET Framework 3.5 nel file di configurazione dell'applicazione.

|Impostazione del file app.config|In un computer in cui è installata la versione 3.5.|In computer con le versioni 3.5 e 4 o versioni successive installate|In computer con versione 4 o versioni successive installate|
|-|-|-|-|
|nessuno|In esecuzione nella versione 3.5.|In esecuzione nella versione 3.5.|Viene visualizzato un messaggio di errore che richiede all'utente di installare la versione corretta*|
|`<supportedRuntime version="v2.0.50727"/>`|In esecuzione nella versione 3.5.|In esecuzione nella versione 3.5.|Viene visualizzato un messaggio di errore che richiede all'utente di installare la versione corretta*|
|`<supportedRuntime version="v2.0.50727"/>` <br /> `<supportedRuntime version="v4.0"/>`|In esecuzione nella versione 3.5.|In esecuzione nella versione 3.5.|In esecuzione nella versione 4 o versioni successive|
|`<supportedRuntime version="v4.0"/>` <br /> `<supportedRuntime version="v2.0.50727"/>`|In esecuzione nella versione 3.5.|In esecuzione nella versione 4 o versioni successive|In esecuzione nella versione 4 o versioni successive|
|`<supportedRuntime version="v4.0"/>`|Viene visualizzato un messaggio di errore che richiede all'utente di installare la versione corretta*|In esecuzione nella versione 4 o versioni successive|In esecuzione nella versione 4 o versioni successive|

 \* Per altre informazioni su questo messaggio di errore e su come evitarlo, vedere [Errori di inizializzazione di .NET Framework: gestione dell'esperienza utente](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md).

## <a name="see-also"></a>Vedere anche

- [Migrazione da .NET Framework 1.1](migrating-from-the-net-framework-1-1.md)
- [Guida alla migrazione](index.md)
