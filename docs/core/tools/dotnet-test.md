---
title: Comando dotnet test
description: Il comando dotnet test viene usato per eseguire unit test in un determinato progetto.
ms.date: 05/29/2018
ms.openlocfilehash: 6b67273f549edd7712237756a5aba13d5cb59a61
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410363"
---
# <a name="dotnet-test"></a>dotnet test

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet test`: driver di test .NET usato per eseguire gli unit test.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a>DESCRIZIONE

Il comando `dotnet test` viene usato per eseguire unit test in un determinato progetto. Il comando `dotnet test` avvia l'applicazione console di esecuzione dei test specificati per un progetto. L'applicazione di esecuzione dei test esegue i test definiti per un framework di unit test (ad esempio MSTest, NUnit o xUnit) e segnala l'esito positivo o negativo di ogni test. Se tutti i test hanno esito positivo, il test runner restituisce 0 come codice di uscita. Se invece i test hanno esito negativo, restituisce 1. L'applicazione di esecuzione dei test e la libreria di unit test sono disponibili come pacchetti NuGet e vengono ripristinati come dipendenze ordinarie per il progetto.

I progetti di test specificano l'applicazione di esecuzione dei test usando un normale elemento `<PackageReference>`, come illustrato nel file di progetto di esempio seguente:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>Argomenti

`PROJECT`

Percorso del progetto di test. Se non specificato, per impostazione predefinita viene usata la directory corrente.

## <a name="options"></a>Opzioni

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.

`--blame`

Esegue i test in modalità di segnalazione degli errori. Questa opzione è utile per isolare i test problematici che causano un arresto anomalo dell'host dei test. Crea un file di output nella directory corrente denominato *Sequence.xml* che acquisisce l'ordine di esecuzione dei test prima dell'arresto anomalo.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Abilita l'agente di raccolta dati per l'esecuzione dei test. Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.

`-f|--framework <FRAMEWORK>`

Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.

`--filter <EXPRESSION>`

Filtra i test nel progetto corrente usando l'espressione specificata. Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details). Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

`-h|--help`

Stampa una breve guida per il comando.

`-l|--logger <LoggerUri/FriendlyName>`

Specifica un logger per i risultati di test.

`--no-build`

Non compila il progetto di test prima dell'esecuzione. Imposta anche in modo implicito il flag `--no-restore`.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directory in cui trovare i file binari da eseguire.

`-r|--results-directory <PATH>`

Directory in cui verranno inseriti i risultati del test. Se la directory specificata non esiste, viene creata.

`-s|--settings <SETTINGS_FILE>`

Il file `.runsettings` da usare per l'esecuzione dei test. [Configurare unit test usando un file `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

Elenca tutti i test individuati nel progetto corrente.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`RunSettings arguments`

Argomenti passati come configurazioni RunSettings per il test. Gli argomenti vengono specificati come coppie `[name]=[value]` dopo "-- ". Si noti lo spazio dopo --. Per separare più coppie `[name]=[value]`, viene usato uno spazio.

Esempio: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

Per altre informazioni su RunSettings, vedere [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md) (vstest.console.exe: passare argomenti RunSettings).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

Abilita l'agente di raccolta dati per l'esecuzione dei test. Per altre informazioni, vedere [Monitoraggio e analisi di esecuzioni dei test](https://aka.ms/vstest-collect).

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.

`-f|--framework <FRAMEWORK>`

Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.

`--filter <EXPRESSION>`

Filtra i test nel progetto corrente usando l'espressione specificata. Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details). Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

`-h|--help`

Stampa una breve guida per il comando.

`-l|--logger <LoggerUri/FriendlyName>`

Specifica un logger per i risultati di test.

`--no-build`

Non compila il progetto di test prima dell'esecuzione. Imposta anche in modo implicito il flag `--no-restore`.

`--no-restore`

Non esegue un ripristino implicito quando si esegue il comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directory in cui trovare i file binari da eseguire.

`-r|--results-directory <PATH>`

Directory in cui verranno inseriti i risultati del test. Se la directory specificata non esiste, viene creata.

`-s|--settings <SETTINGS_FILE>`

Il file `.runsettings` da usare per l'esecuzione dei test. [Configurare unit test usando un file `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

Elenca tutti i test individuati nel progetto corrente.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Usa gli adattatori di test personalizzati dal percorso specificato nell'esecuzione del test.

`-c|--configuration {Debug|Release}`

Definisce la configurazione di compilazione. Il valore predefinito è `Debug`, ma la configurazione del progetto può eseguire l'override di questa impostazione predefinita dell'SDK.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Abilita la modalità di diagnostica per la piattaforma di test e scrive messaggi di diagnostica nel file specificato.

`-f|--framework <FRAMEWORK>`

Cerca i file binari di test per un [framework](../../standard/frameworks.md) specifico.

`--filter <EXPRESSION>`

Filtra i test nel progetto corrente usando l'espressione specificata. Per altre informazioni, vedere la sezione [Dettagli dell'opzione filter](#filter-option-details). Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

`-h|--help`

Stampa una breve guida per il comando.

`-l|--logger <LoggerUri/FriendlyName>`

Specifica un logger per i risultati di test.

`--no-build`

Non compila il progetto di test prima dell'esecuzione.

`-o|--output <OUTPUT_DIRECTORY>`

Directory in cui trovare i file binari da eseguire.

`-s|--settings <SETTINGS_FILE>`

Il file `.runsettings` da usare per l'esecuzione dei test. [Configurare unit test usando un file `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

Elenca tutti i test individuati nel progetto corrente.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

---

## <a name="examples"></a>Esempi

Eseguire i test nel progetto nella directory corrente:

`dotnet test`

Eseguire i test nel progetto `test1`:

`dotnet test ~/projects/test1/test1.csproj`

Eseguire i test nel progetto nella directory corrente e generare un file dei risultati di test in formato trx:

`dotnet test --logger:trx`

## <a name="filter-option-details"></a>Dettagli dell'opzione filter

`--filter <EXPRESSION>`

`<Expression>` ha il formato `<property><operator><value>[|&<Expression>]`.

`<property>` è un attributo di `Test Case`. La tabella seguente elenca le proprietà supportate da framework diffusi per unit test:

| Framework di test | Proprietà supportate                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>nome</li><li>ClassName</li><li>Priorità</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Tratti</li></ul>                                   |

`<operator>` descrive la relazione tra la proprietà e il valore:

| Operatore | Funzione        |
| :------: | --------------- |
| `=`      | Corrispondenza esatta     |
| `!=`     | Corrispondenza non esatta |
| `~`      | Contiene        |

`<value>` è una stringa. Per tutte le ricerche non viene fatta distinzione tra maiuscole e minuscole.

Un'espressione senza `<operator>` viene considerata automaticamente come un'operazione `contains` sulla proprietà `FullyQualifiedName`. Ad esempio, `dotnet test --filter xyz` è uguale a `dotnet test --filter FullyQualifiedName~xyz`.

Le espressioni possono essere unite con operatori condizionali:

| Operatore            | Funzione |
| ------------------- | -------- |
| <code>&#124;</code> | OR       |
| `&`                 | AND      |

È possibile racchiudere le espressioni tra parentesi quando si usano gli operatori condizionali (ad esempio, `(Name~TestMethod1) | (Name~TestMethod2)`).

Per altre informazioni ed esempi sull'uso del filtro degli unit test selettivi, vedere [Esecuzione di unit test selettivi](../testing/selective-unit-tests.md).

## <a name="see-also"></a>Vedere anche

- [Frameworks e destinazioni](../../standard/frameworks.md)
- [Catalogo dei RID (Runtime IDentifier) di .NET Core](../rid-catalog.md)
