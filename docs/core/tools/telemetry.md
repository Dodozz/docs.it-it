---
title: Telemetria di .NET Core SDK
description: Informazioni sulle funzionalità di telemetria degli strumenti di .NET Core SDK che raccolgono informazioni sull'utilizzo per l'analisi, i dati raccolti e il modo in cui disabilitarli.
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 8b0b546d70eab837c2e075f839990870ae9ea6b1
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168845"
---
# <a name="net-core-sdk-telemetry"></a>Telemetria di .NET Core SDK

[.NET Core SDK](index.md) include una [funzionalità di telemetria](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) che raccoglie le informazioni sull'utilizzo. È importante che il team di .NET comprenda come vengono usati gli strumenti per consentire a Microsoft di migliorarne le funzionalità. Per ulteriori informazioni, vedere [Nozioni apprese da .NET Core SDK, telemetria](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).

I dati raccolti sono anonimi e sono pubblicati in forma aggregata per l'uso da parte di Microsoft e della community in base alla [licenza Creative Commons Attribution](https://creativecommons.org/licenses/by/4.0/).

## <a name="scope"></a>Ambito

Il comando `dotnet` viene usato per avviare sia le applicazioni sia l’interfaccia della riga di comando di .NET Core. La raccolta dei dati di telemetria non viene eseguita dal comando `dotnet` stesso. I comandi dell’interfaccia della riga di comando .NET Core eseguiti dal comando `dotnet` raccolgono la telemetria.

La telemetria *non è abilitata* quando si utilizza il comando `dotnet` stesso, con nessun comando collegato:

- `dotnet`
- `dotnet [path-to-app]`

La telemetria *è abilitata* quando si utilizzano i comandi dell’interfaccia della riga di comando . NET Core[, ](index.md)ad esempio:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a>Come rifiutare esplicitamente

La funzionalità di telemetria di .NET Core SDK è abilitata per impostazione predefinita. Rifiutare esplicitamente la funzionalità di telemetria impostando la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`.

## <a name="data-points"></a>Punti dati

La funzionalità raccoglie i dati seguenti:

- Il timestamp della chiamata&#8224;
- Comando richiamato (ad esempio, "build")&#8224;
- Indirizzo IP di tre ottetti usato per determinare la posizione geografica&#8224;
- `ExitCode` del comando
- Test Runner usato (per i progetti di test)
- Sistema operativo e relativa versione&#8224;
- L'eventuale presenza di ID di runtime nel nodo runtimes
- .NET core SDK versione&#8224;

&#8224;Questa metrica è pubblicata.

A partire da .NET Core 2.0 SDK, sono raccolti nuovi punti dati:

- `dotnet`argomenti e opzioni di comando: sono raccolti solo gli argomenti e le opzioni noti (non stringhe arbitrarie).
- Se il SDK è in esecuzione in un contenitore.
- Framework di destinazione.
- Indirizzo MAC con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per uncomputer. Questa metrica non è pubblicata.
- Directory di lavoro corrente con hash.

La funzionalità non raccoglie i dati personali, ad esempio i nomi utente o gli indirizzi e-mail. Non esegue l'analisi del codice e non estrae i dati sensibili a livello di progetto, ad esempio nome, repository o autore. I dati vengono inviati in modo sicuro ai server Microsoft tramite la tecnologia [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), conservati con accesso limitato e pubblicati sotto rigidi controlli di sicurezza dai sistemi protetti [di archiviazione di Azure](https://azure.microsoft.com/services/storage/).

Il team .NET è interessato a conoscere come vengono usati gli strumenti e se funzionano bene e non i progetti realizzati con gli strumenti. Se si ritiene che la telemetria raccolga dati riservati o che i dati siano gestiti in modo non corretto o non protetto, segnalare un problema nel repository [dotnet/cli](https://github.com/dotnet/cli/issues) per un'analisi più approfondita.

## <a name="published-data"></a>Dati pubblicati

I dati pubblicati sono disponibili su base trimestrale e sono elencati in [dati di utilizzo di .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md). Le colonne di un file di dati sono:

- Timestamp
- Occorrenze&#8224;
- Comando
- Geografia&#8225;
- OSFamily
- IDruntime
- OSVersion
- VersioneSDK

&#8224; Nella colonna *Occorrenze* è riportato il conteggio in aggregato dell'utilizzo da parte del comando di metriche di tale riga nel giorno in questione.

&#8225; In genere, nella colonna*Geografia* è riportato il nome di un Paese. In alcuni casi, continente Antartide viene visualizzato in questa colonna, a causa di ricercatori che utilizzano .NET Core in Antartide o dati della posizione non corretti.

### <a name="example"></a>Esempio

| Timestamp      | Occorrenze | Comando | Geografia | OSFamily | IDruntime     | OSVersion | VersioneSDK |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| 4/16/2017 0:00 | 8           | run     | Uganda    | Darwin   | osx.10.12-x64 | 10.12     | 1.0.1      |

### <a name="datasets"></a>Dataset

[2016 - 3° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[2016 - 4° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[2017 - 1° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[2017 - 2° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)  
[2017 - 3° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)  
[2017 - 4° trim.](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)  

Set di dati aggiuntivi vengono pubblicati con un formato URL standard. Sostituire `<YEAR>` con l'anno e sostituire `<QUARTER>` con il trimestre dell'anno (utilizzare `1`, `2`, `3`, o `4`). I file sono in formato con valori delimitati da tabulazioni (*TSV*).

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a>Licenza

La distribuzione Microsoft di .NET Core è concessa in base alle [condizioni di licenza di MICROSOFT .NET LIBRARY](https://aka.ms/dotnet-core-eula). Nelle condizioni è inclusa la sezione "DATA", per l'abilitazione della telemetria (riportata di seguito).

Questa licenza viene usata anche dai [pacchetti NuGet .NET](https://www.nuget.org/profiles/dotnetframework) per i quali, tuttavia, la funzionalità di telemetria non è abilitata (vedere la sezione [Ambito](#scope)).

> 2. DATI. Il software può raccogliere informazioni sull'utente e sull'uso del software e inviarle a Microsoft. Microsoft può usare queste informazioni per migliorare i prodotti e i servizi. Per altre informazioni sulla raccolta dati, sull'uso nella documentazione della Guida e sull'informativa sulla privacy, vedere <http://go.microsoft.com/fwlink/?LinkId=528096>. L'uso del software viene considerato come autorizzazione all'applicazione di queste pratiche.

## <a name="disclosure"></a>Divulgazione

La prima volta che si esegue uno dei [comandi dell'interfaccia della riga di comando di .NET Core](index.md), ad esempio `dotnet restore`, .NET Core SDK visualizza il testo seguente. Testo può variare leggermente a seconda della versione del SDK è in esecuzione. Questa prima esperienza riguarda la modalità di notifica della raccolta dei dati da parte di Microsoft.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a>Vedere anche

- [Nozioni apprese da.NET Core SDK telemetria](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)
- [Origine riferimento di telemetria (repository dotnet/cli)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [Dati di utilizzo di .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
