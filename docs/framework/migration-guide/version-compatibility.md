---
title: Compatibilità tra le versioni in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8db23f8e670406faff01644e751a948096f5fc7c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592889"
---
# <a name="version-compatibility-in-the-net-framework"></a>Compatibilità tra le versioni in .NET Framework

Per compatibilità con le versioni precedenti si intende che un'app sviluppata per una particolare versione di una piattaforma sarà eseguita su versioni successive di quella piattaforma. .NET Framework tenta di mantenere la massima compatibilità con le versioni precedenti: è possibile compilare codice sorgente scritto per una versione di .NET Framework con versioni successive di .NET Framework e i file binari in esecuzione in una versione di .NET Framework devono comportarsi in modo identico nelle versioni successive di .NET Framework.

## <a name="Apps"></a> Compatibilità tra le versioni per app

Per impostazione predefinita, un'app viene eseguita sulla versione di .NET Framework per cui è stata creata. Se tale versione non è presente e il file di configurazione dell'app non definisce le versioni supportate, potrebbe verificarsi un errore di inizializzazione di .NET Framework. In questo caso, il tentativo di esecuzione dell'app avrà esito negativo.

Per definire le versioni specifiche in cui viene eseguita l'app, aggiungere uno o più elementi [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) al file di configurazione dell'app. Ogni elemento `<supportedRuntime>` elenca una versione supportata del runtime, con il primo che specifica la versione preferita e l'ultimo che specifica l'ultima versione nell'elenco delle preferenze.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v2.0.50727" />
      <supportedRuntime version="v4.0" />
   </startup>
</configuration>
```

Per altre informazioni, vedere [Procedura: Configurare un'app per supportare .NET Framework 4 o 4.x](../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).

## <a name="version-compatibility-for-components"></a>Compatibilità tra le versioni per componenti

Un'app, diversamente da un componente, può controllare la versione di .NET Framework in cui viene eseguita. I componenti e le librerie di classi vengono caricati nel contesto di un'app specifica, ecco perché vengono eseguiti automaticamente nella versione di .NET Framework in cui è in esecuzione l'app.

A causa di questa restrizione, le garanzie di compatibilità sono particolarmente importanti per i componenti. A partire da .NET Framework 4, è possibile specificare il livello di compatibilità di un componente in più versioni applicando l'attributo <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> a tale componente. Gli strumenti possono usare questo attributo per rilevare le possibili violazioni della garanzia di compatibilità in versioni future di un componente.

## <a name="backward-compatibility-and-the-net-framework"></a>Compatibilità con le versioni precedenti e .NET Framework

.NET Framework 4.5 e versioni successive sono compatibili con le versioni precedenti delle app create con le versioni precedenti di .NET Framework. In altre parole, le app e i componenti creati con le versioni precedenti funzioneranno senza applicare alcuna modifica in .NET Framework 4.5 e versioni successive. Tuttavia, per impostazione predefinita, le app vengono eseguite sulla versione di Common Language Runtime per la quale sono state sviluppate, pertanto potrebbe essere necessario fornire un file di configurazione per far sì che l'app venga eseguita in .NET Framework 4.5 o versioni successive. Per altre informazioni, vedere la sezione [Compatibilità tra le versioni per app](#Apps) in questo articolo.

In pratica, questa compatibilità può essere interrotta da modifiche apparentemente irrilevanti in .NET Framework e nelle tecniche di programmazione. Ad esempio, i miglioramenti delle prestazioni in .NET Framework 4.5 possono esporre una race condition che non si era verificata nelle versioni precedenti. Allo stesso modo, l'uso di un percorso hardcoded per gli assembly .NET Framework, l'esecuzione di un confronto delle uguaglianze con una particolare versione di .NET Framework e l'acquisizione del valore di un campo privato tramite reflection non sono pratiche compatibili con le versioni precedenti. Inoltre, ogni versione di .NET Framework include correzioni di bug e modifiche correlate alla sicurezza che possono incidere sulla compatibilità di alcune app e componenti.

Se l'app o il componente non funziona come previsto in .NET Framework 4.5 (e versioni intermedie: .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8), usare gli elenchi di controllo seguenti:

- Se l'app è stata sviluppata per l'esecuzione in qualsiasi versione di .NET Framework a partire da .NET Framework 4.0, vedere [Compatibilità delle applicazioni in .NET Framework](application-compatibility.md) per creare un elenco di modifiche tra la versione di .NET Framework di destinazione e la versione in cui l'app è in esecuzione.

- Se si dispone di un'app .NET Framework 3.5, vedere anche [Problemi di migrazione di .NET Framework 4](../migration-guide/net-framework-4-migration-issues.md).

- Se si dispone di un'app .NET Framework 2.0, vedere anche [Modifiche in .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkId=186989).

- Se si dispone di un'app .NET Framework 1.1, vedere anche [Modifiche in .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkID=125263).

- Se si sta eseguendo la ricompilazione del codice sorgente esistente per l'esecuzione in .NET Framework 4.5 o nelle relative versioni intermedie oppure si sta sviluppando una nuova versione di un'app o di un componente destinato a .NET Framework 4.5 o alle relative versioni intermedie da una codebase sorgente esistente, vedere [Elementi obsoleti nella libreria di classi .NET Framework](../whats-new/whats-obsolete.md) per i tipi e i membri obsoleti e applicare la soluzione alternativa descritta. (Il codice compilato precedentemente continuerà a essere in esecuzione sui tipi e i membri contrassegnati come obsoleti).

- Se si determina che una modifica in .NET Framework 4.5 ha interrotto l'app, vedere [Schema delle impostazioni di runtime](../configure-apps/file-schema/runtime/index.md) e in particolare l'[elemento \<AppContextSwitchOverrides>](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) per stabilire se è possibile usare un'impostazione di runtime nel file di configurazione dell'app per ripristinare il comportamento precedente.

- Se si verifica un problema non documentato, segnalarlo nel [sito della community degli sviluppatori .NET](https://developercommunity.visualstudio.com/spaces/61/index.html) oppure nel [repository GitHub Microsoft/dotnet](https://github.com/microsoft/dotnet/issues).

## <a name="compatibility-and-side-by-side-execution"></a>Compatibilità ed esecuzione affiancata

Se non si riesce a trovare una soluzione alternativa adatta al problema, ricordare che .NET Framework 4.5 (e versioni intermedie) viene eseguito side-by-side con le versioni 1.1, 2.0 e 3.5 ed è un aggiornamento sul posto che sostituisce la versione 4. Per app destinate alle versioni 1.1, 2.0 e 3.5, è possibile installare la versione appropriata di .NET Framework nel computer di destinazione per eseguire l'app nell'ambiente migliore. Per altre informazioni sull'esecuzione side-by-side, vedere [Esecuzione side-by-side](../deployment/side-by-side-execution.md).

## <a name="see-also"></a>Vedere anche

- [Novità](../whats-new/index.md)
- [Elementi obsoleti nella libreria di classi](../whats-new/whats-obsolete.md)
- [Compatibilità delle applicazioni](../migration-guide/application-compatibility.md)
- [Criteri relativi al ciclo di vita del supporto di Microsoft .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=248212)
- [Problemi di migrazione di .NET Framework 4](../migration-guide/net-framework-4-migration-issues.md)
