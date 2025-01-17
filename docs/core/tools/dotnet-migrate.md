---
title: Comando dotnet migrate
description: Il comando dotnet migrate consente di eseguire la migrazione di un progetto e di tutte le relative dipendenze.
ms.date: 05/25/2018
ms.openlocfilehash: 861cd2cb982c6f41baf00a2cbd7e04b26816af76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631956"
---
# <a name="dotnet-migrate"></a>dotnet migrate

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet migrate`: esegue la migrazione di un progetto .NET Core Preview 2 a un progetto .NET Core SDK 1.0.

## <a name="synopsis"></a>Riepilogo

```
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a>Description

Il comando `dotnet migrate` esegue la migrazione di un progetto basato su *project.json* Preview 2 valido a un progetto *csproj* .NET Core SDK 1.0 valido.

Per impostazione predefinita, il comando esegue la migrazione del progetto radice e dei riferimenti del progetto presenti nel progetto radice. Questo comportamento viene disabilitato usando l'opzione `--skip-project-references` in fase di esecuzione.

È possibile eseguire la migrazione in uno degli asset seguenti:

* Un singolo progetto, specificando il file *project.json* di cui eseguire la migrazione.
* Tutte le directory specificate nel file *global.json*, passando un percorso del file *global.json*.
* Un file *solution.sln*, dove vengono migrati i progetti a cui viene fatto riferimento nella soluzione.
* Tutte le sottodirectory della directory specificata, in modo ricorsivo.

Il comando `dotnet migrate` mantiene il file *project.json* di cui è stata eseguita la migrazione all'interno di una directory `backup`, che verrà creata se non esiste già. Questo comportamento viene sottoposto a override tramite l'opzione `--skip-backup`.

Per impostazione predefinita, l'operazione di migrazione restituisce lo stato del processo di migrazione all'output standard (STDOUT). Se si usa l'opzione `--report-file <REPORT_FILE>`, l'output viene salvato nel file specificato.

Il comando `dotnet migrate` supporta solo progetti basati su *project.json* Preview 2 validi. Questo significa che non è possibile usare questo comando per eseguire la migrazione di progetti basati su DNX o *project.json* Preview 1 direttamente a progetti MSBuild/csproj. È prima necessario eseguire manualmente la migrazione del progetto a un progetto basato su *project.json* Preview 2 e quindi usare il comando `dotnet migrate` per eseguire la migrazione del progetto.

## <a name="arguments"></a>Argomenti

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

Percorso a uno degli elementi seguenti:

* File *project.json* di cui eseguire la migrazione.
* File *global.json*: viene eseguita la migrazione delle cartelle specificate in *global.json*.
* File *solution.sln*: viene eseguita la migrazione dei progetti a cui viene fatto riferimento nella soluzione.
* Directory di cui eseguire la migrazione: vengono cercati in modo ricorsivo i file *project.json* di cui eseguire la migrazione all'interno della directory specificata.

Se non è specificata alcuna opzione, verrà impostata automaticamente la directory corrente.

## <a name="options"></a>Opzioni

`--format-report-file-json <REPORT_FILE>`

File di report di migrazione dell'output come JSON anziché messaggi utente.

`-h|--help`

Stampa una breve guida per il comando.

`-r|--report-file <REPORT_FILE>`

Report di migrazione dell'output a un file oltre che alla console.

`-s|--skip-project-references [Debug|Release]`

Ignora la migrazione dei riferimenti del progetto. Per impostazione predefinita, i riferimenti al progetto vengono migrati in modo ricorsivo.

`--skip-backup`

Dopo l'esito positivo della migrazione, ignorare lo spostamento di *project.json*, *global.json* e *\*.xproj* in una directory `backup`.

`-t|--template-file <TEMPLATE_FILE>`

File csproj modello da usare per la migrazione. Per impostazione predefinita, viene usato lo stesso modello di quello eliminato da `dotnet new console`.

`-v|--sdk-package-version <VERSION>`

Versione del pacchetto SDK a cui viene fatto riferimento nell'app di cui è stata eseguita la migrazione. Il valore predefinito è la versione dell'SDK in `dotnet new`.

`-x|--xproj-file <FILE>`

Percorso del file xproj da usare. Obbligatorio quando è presente più di un progetto xproj nella directory di un progetto.

## <a name="examples"></a>Esempi

Eseguire la migrazione di un progetto nella directory corrente e in tutte le relative dipendenze da progetto a progetto:

`dotnet migrate`

Eseguire la migrazione di tutti i progetti inclusi nel file *global.json*:

`dotnet migrate path/to/global.json`

Eseguire solo la migrazione del progetto corrente e non delle dipendenze da progetto a progetto. Usare una versione specifica dell'SDK:

`dotnet migrate -s -v 1.0.0-preview4`
