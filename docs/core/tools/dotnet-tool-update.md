---
title: Comando dotnet tool update
description: Il comando dotnet tool update aggiorna lo strumento globale .NET Core specificato nel computer.
ms.date: 05/29/2018
ms.openlocfilehash: bc7edada013c118564d44cbe4542dacb76925692
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516642"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nome

`dotnet tool update` - Aggiorna lo [strumento globale .NET Core](global-tools.md) specificato nel computer.

## <a name="synopsis"></a>Riepilogo

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a>Description

Il comando `dotnet tool update` consente di aggiornare gli strumenti globali .NET Core nel computer all'ultima versione stabile del pacchetto. Il comando disinstalla e reinstalla uno strumento aggiornandolo. Per usare il comando, è necessario specificare che si vuole aggiornare uno strumento da un'installazione a livello utente con l'opzione `--global` oppure specificare un percorso in cui è installato lo strumento con l'opzione `--tool-path`.

## <a name="arguments"></a>Argomenti

`PACKAGE_NAME`

Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare. È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opzioni

`--add-source <SOURCE>`

Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

`--configfile <FILE>`

File di configurazione NuGet (*nuget.config*) da usare.

`--framework <FRAMEWORK>`

Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.

`-g|--global`

Specifica che l'aggiornamento è per uno strumento a livello utente. Non può essere usata con l'opzione `--tool-path`. Se non si specifica questa opzione, è necessario specificare l'opzione `--tool-path`.

`-h|--help`

Stampa una breve guida per il comando.

`--tool-path <PATH>`

Specifica il percorso in cui è installato lo strumento globale. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Se non si specifica questa opzione, è necessario specificare l'opzione `--global`.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="examples"></a>Esempi

Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool update -g dotnetsay`

Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Windows specifica:

`dotnet tool update dotnetsay --tool-path c:\global-tools`

Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Linux/macOS specifica:

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Vedere anche

- [Strumenti globali .NET Core](global-tools.md)
