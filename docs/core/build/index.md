---
title: Compilare .NET Core dal codice sorgente
description: Informazioni su come compilare .NET Core e .NET Core CLI dal codice sorgente.
author: bleroy
ms.date: 06/28/2017
ms.custom: seodec18
ms.openlocfilehash: 523b537ba07afd1b6c56192c5e2589082fe5820f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650882"
---
# <a name="build-net-core-from-source"></a>Compilare .NET Core dal codice sorgente

La possibilità di compilare .NET Core dal relativo codice sorgente è importante per diversi motivi: rende più semplice il trasferimento di .NET Core sulle nuove piattaforme, abilita i contributi e le correzioni per il prodotto e consente la creazione di versioni personalizzate di .NET.
Questo articolo offre materiale sussidiario agli sviluppatori che vogliono compilare e distribuire le proprie versioni di .NET Core.

## <a name="build-the-clr-from-source"></a>Compilare Common Language Runtime (CLR) dal codice sorgente

Il codice sorgente per .NET CoreCLR è reperibile nel repository [dotnet/coreclr](https://github.com/dotnet/coreclr/) su GitHub.

La compilazione attualmente dipende dai prerequisiti seguenti:

* [Git](https://git-scm.com/)
* [CMake](https://cmake.org/)
* [Python](https://www.python.org/)
* un compilatore C++.

Dopo aver installato questi prerequisiti è possibile compilare CLR richiamando lo script di compilazione (`build.cmd` in Windows o `build.sh` in Linux e macOS) alla base del repository [dotnet/coreclr](https://github.com/dotnet/coreclr/).

L'installazione dei componenti varia in base al sistema operativo. Vedere le istruzioni di compilazione per il sistema operativo specifico:

* [Windows](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
* [Linux](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
* [macOS](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
* [FreeBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md)
* [NetBSD](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

Non esiste alcuna compilazione incrociata tra sistemi operativi (solo per ARM, che è basato su X64).  
È necessario essere sulla piattaforma specifica per compilare quella piattaforma.  

La compilazione ha due `buildTypes` principali:

* Debug (impostazione predefinita): compila il runtime con le ottimizzazioni minime e controlli di runtime aggiuntivi (asserzioni). La riduzione del livello di ottimizzazione e i controlli aggiuntivi rallentano l'esecuzione di runtime, ma sono utili per il debug. Questa è l'impostazione consigliata per gli ambienti di sviluppo e test.
* Release: compila il runtime con le ottimizzazioni complete e senza i controlli di runtime aggiuntivi. Si ottengono così prestazioni di runtime molto più veloci, ma la compilazione può richiedere un po' più di tempo e può essere difficile eseguire il debug. Passare `release` allo script di compilazione per selezionare questo tipo di compilazione.

Inoltre, per impostazione predefinita la compilazione non solo crea gli eseguibili di runtime, ma compila anche tutti i test.
I test sono piuttosto numerosi e richiedono una quantità significativa di tempo che non è necessaria se si vuole solo sperimentare le modifiche.
È possibile ignorare le compilazioni dei test aggiungendo l'argomento `skiptests` allo script di compilazione, come nell'esempio seguente (sostituire `.\build` con `./build.sh` nei computer Unix):

```bat
    .\build skiptests
```

L'esempio precedente illustra come compilare la versione `Debug`, in cui sono abilitati i controlli della fase di sviluppo (asserzioni) e sono disabilitate le ottimizzazioni. Per compilare la versione di rilascio (velocità completa), eseguire le operazioni seguenti:

```bat
    .\build release skiptests
```

Sono disponibili altre opzioni di compilazione se si esegue la compilazione con il qualificatore -? o -help.

### <a name="using-your-build"></a>Uso della compilazione

La compilazione colloca tutti i file generati sotto la directory `bin` alla base dell'archivio.
È presente una directory *bin\Log* che contiene i file di log generati durante la compilazione ed è particolarmente utile quando la compilazione ha esito negativo.
L'output effettivo viene inserito in una directory *bin\Product\[piattaforma]. [architettura CPU]. [tipo di compilazione]* , ad esempio *bin\Product\Windows_NT.x64.Release*.

Benché l'output non elaborato della compilazione spesso sia utile, di solito interessano solo i pacchetti NuGet, che vengono inseriti nella sottodirectory `.nuget\pkg` della directory di output precedente.

Esistono due tecniche di base per l'uso del nuovo runtime:

 1. **Usare dotnet.exe e NuGet per creare un'applicazione**.
    Vedere [Uso della compilazione](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) per istruzioni sulla creazione di un programma che usa il nuovo runtime con i pacchetti NuGet appena creati e l'interfaccia della riga di comando "dotnet" (CLI). Questa tecnica è probabilmente il modo in cui gli sviluppatori non di runtime preferiscono usare il nuovo runtime.

 2. **Usare corerun.exe per eseguire un'applicazione con le DLL non in pacchetto**.
    Questo archivio definisce anche un host semplice denominato corerun.exe che NON accetta dipendenze in NuGet.
    Si dovrà indicare all'host dove si ottengono le DLL necessarie in uso e raccogliere le DLL manualmente.
    Questa tecnica viene usata da tutti i test nel repository [dotnet/coreclr](https://github.com/dotnet/coreclr) ed è utile in un ciclo rapido di "modifica-compilazione-debug" locale, ad esempio per gli unit test preliminari.
    Vedere [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) (Esecuzione delle app .NET Core con CoreRun.exe) per informazioni dettagliate sull'uso di questa tecnica.

## <a name="build-the-cli-from-source"></a>Compilare l'interfaccia della riga di comando dal codice sorgente

Il codice sorgente per l'interfaccia della riga di comando di .NET Core è reperibile nel repository [dotnet/cli](https://github.com/dotnet/cli/) su GitHub.

Per compilare l'interfaccia della riga di comando di .NET Core, i seguenti componenti devono essere installati nel computer.

* Windows e Linux:
  * git nel PERCORSO
* macOS:
  * git nel PERCORSO
  * Xcode
  * OpenSSL

Per compilare, eseguire `build.cmd` in Windows o `build.sh` in Linux e macOS dalla radice. Per non eseguire i test, eseguire `build.cmd -t:Compile` o `./build.sh -t:Compile`. Per compilare l'interfaccia della riga di comando in macOS Sierra, è necessario impostare la variabile di ambiente DOTNET_RUNTIME_ID eseguendo `export DOTNET_RUNTIME_ID=osx.10.11-x64`.

### <a name="using-your-build"></a>Uso della compilazione

Usare l'eseguibile `dotnet` da *artifacts/{os}-{arch}/stage2* per provare l'interfaccia della riga di comando appena creata. Per usare l'output della compilazione quando si chiama `dotnet` dalla console corrente, è anche possibile aggiungere *artifacts/{os}-{arch}/stage2* al PERCORSO.

## <a name="see-also"></a>Vedere anche

- [.NET Core Common Language Runtime (CoreCLR)](https://github.com/dotnet/coreclr/blob/master/README.md)
- [Guida per sviluppatori di .NET Core CLI](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
- [Pacchetti di distribuzione di .NET Core](./distribution-packaging.md)
