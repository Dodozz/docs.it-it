---
title: Pubblicare le app .NET Core con l'interfaccia della riga di comando
description: Informazioni su come pubblicare un'app .NET Core con gli strumenti dell'interfaccia della riga di comando di .NET Core SDK.
author: thraka
ms.author: adegeo
ms.date: 01/16/2019
dev_langs:
- csharp
- vb
ms.custom: seodec18
ms.openlocfilehash: a72e5e557cd3aa098b674bffd277e3cc6da99d33
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306066"
---
# <a name="publish-net-core-apps-with-the-cli"></a>Pubblicare le app .NET Core con l'interfaccia della riga di comando

Questo articolo illustra come pubblicare l'applicazione .NET Core dalla riga di comando. .NET Core offre tre modi per pubblicare le applicazioni. La distribuzione dipendente dal framework genera un file con estensione dll multipiattaforma che usa il runtime di .NET Core installato in locale. L'eseguibile dipendente dal framework genera un file eseguibile specifico della piattaforma che usa il runtime di .NET Core installato in locale. L'eseguibile autonomo genera un file eseguibile specifico della piattaforma e include una copia locale del runtime di .NET Core.

Per una panoramica di queste modalità di pubblicazione, vedere [Distribuzione di applicazioni .NET Core](index.md).

Per un aiuto rapido sull'uso dell'interfaccia della riga di comando, la tabella seguente illustra alcuni esempi di pubblicazione di un'app. È possibile specificare il framework di destinazione con il parametro `-f <TFM>` o modificando il file di progetto. Per altre informazioni, vedere [Nozioni di base sulla pubblicazione](#publishing-basics).

| Modalità di pubblicazione | Versione SDK | Comando |
| ------------ | ----------- | ------- |
| Distribuzione dipendente dal framework | 2.x | `dotnet publish -c Release` |
| File eseguibile dipendente dal framework | 2.2 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0* | `dotnet publish -c Release` |
| Distribuzione autonoma      | 2.1 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 2.2 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained true` |

\* Quando si usa l'SDK versione 3.0, il file eseguibile dipendente dal framework è la modalità di pubblicazione predefinita durante l'esecuzione del comando `dotnet publish` di base. Questo vale solo quando il progetto è destinato a **.NET Core 2.1** o **.NET Core 3.0**.

## <a name="publishing-basics"></a>Nozioni di base sulla pubblicazione

L'impostazione `<TargetFramework>` del file di progetto specifica il framework di destinazione predefinito quando si pubblica l'app. È possibile modificare il framework di destinazione impostando qualsiasi [moniker framework di destinazione (TFM)](../../standard/frameworks.md). Ad esempio, se il progetto usa `<TargetFramework>netcoreapp2.2</TargetFramework>`, viene creato un file binario che ha come destinazione .NET Core 2.2. Il moniker framework di destinazione specificato in questa impostazione è la destinazione predefinita usata dal comando [`dotnet publish`](../tools/dotnet-publish.md).

Se si vuole impostare più framework di destinazione, è possibile impostare `<TargetFrameworks>` su più valori di moniker framework di destinazione separati da punto e virgola. È possibile pubblicare uno dei framework con il comando `dotnet publish -f <TFM>`. Ad esempio, se è stato specificato `<TargetFrameworks>netcoreapp2.1;netcoreapp2.2</TargetFrameworks>` e si esegue `dotnet publish -f netcoreapp2.1`, viene creato un file binario che ha come destinazione .NET Core 2.1.

Se non è stata impostata diversamente, la directory di output del comando [`dotnet publish`](../tools/dotnet-publish.md) è `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`. La modalità **BUILD-CONFIGURATION** predefinita è **Debug** a meno che non venga modificata con il parametro `-c`. Ad esempio, `dotnet publish -c Release -f netcoreapp2.1` pubblica in `myfolder/bin/Release/netcoreapp2.1/publish/`.

Se si usa .NET Core SDK 3.0, la modalità di pubblicazione predefinita per le app che hanno come destinazione .NET Core versione 2.1, 2.2 o 3.0 è un file eseguibile dipendente dal framework.

Se si usa .NET Core SDK 2.1, la modalità di pubblicazione predefinita per le app che hanno come destinazione .NET Core versione 2.1 o 2.2 è una distribuzione dipendente dal framework.

### <a name="native-dependencies"></a>Dipendenze native

Se l'app ha dipendenze native, è possibile che non venga eseguita in un sistema operativo diverso. Ad esempio, se l'app usa l'API Windows nativa, non verrà eseguita in macOS o Linux. Sarà necessario specificare un codice specifico della piattaforma e compilare un file eseguibile per ogni piattaforma.

Tenere presente anche che se una libreria a cui viene fatto riferimento include una dipendenza nativa, è possibile che l'app non venga eseguita in ogni piattaforma. Tuttavia, è possibile che un pacchetto NuGet cui viene fatto riferimento includa versioni specifiche della piattaforma per gestire automaticamente le dipendenze native necessarie.

Quando si distribuisce un'app con dipendenze native, potrebbe essere necessario usare l'opzione `dotnet publish -r <RID>` per specificare la piattaforma di destinazione per cui eseguire la pubblicazione. Per un elenco degli identificatori di runtime, vedere [Catalogo RID di .NET Core](../rid-catalog.md).

Altre informazioni sui file binari specifici della piattaforma sono disponibili nelle sezioni [File eseguibili dipendenti dal framework](#framework-dependent-executable) e [Distribuzioni autonome](#self-contained-deployment).

## <a name="sample-app"></a>App di esempio

È possibile usare entrambe le app seguenti per visualizzare i comandi di pubblicazione. L'app viene creata eseguendo i comandi seguenti nel terminale:

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

Il file `Program.cs` o `Program.vb` generato dal modello di console deve essere modificato come segue:

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

Quando si esegue l'app ([`dotnet run`](../tools/dotnet-run.md)), viene visualizzato l'output seguente:

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a>Distribuzione dipendente dal framework

Per l'interfaccia della riga di comando di .NET Core SDK 2.x, la distribuzione dipendente dal framework è la modalità predefinita per il comando `dotnet publish` di base.

Quando si pubblica l'app come distribuzione dipendente dal framework, viene creato un file `<PROJECT-NAME>.dll` nella cartella `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`. Per eseguire l'app, passare alla cartella di output e usare il comando `dotnet <PROJECT-NAME>.dll`.

L'app viene configurata con una versione specifica di .NET Core come destinazione. Il runtime .NET Core di destinazione deve trovarsi nel computer in cui si vuole eseguire l'app. Ad esempio, se l'app ha come destinazione .NET Core 2.2, ogni computer in cui viene eseguita l'app deve avere il runtime .NET Core 2.2 installato. Come descritto nella sezione [Nozioni di base sulla pubblicazione](#publishing-basics), è possibile modificare il file di progetto per cambiare il framework di destinazione predefinito o per impostare come destinazione più framework.

La pubblicazione di una distribuzione dipendente dal framework crea un'app che esegue automaticamente il roll forward all'ultima patch di protezione .NET Core disponibile nel sistema che esegue l'app. Per altre informazioni sul binding di versione in fase di compilazione, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md#framework-dependent-apps-roll-forward).

## <a name="framework-dependent-executable"></a>File eseguibile dipendente dal framework

Per l'interfaccia della riga di comando di .NET Core SDK 3.x, il file eseguibile dipendente dal framework è la modalità predefinita per il comando `dotnet publish` di base. Se la destinazione è il sistema operativo corrente, non è necessario specificare altri parametri.

In questa modalità viene creato un host eseguibile specifico della piattaforma per ospitare l'app multipiattaforma. Questa modalità è simile alla distribuzione dipendente dal framework che richiede un host sotto forma di comando `dotnet`. Il nome del file eseguibile host varia a seconda della piattaforma ed è simile a `<PROJECT-FILE>.exe`. È possibile eseguire questo eseguibile direttamente anziché chiamare `dotnet <PROJECT-FILE>.dll` per eseguire l'app.

L'app viene configurata con una versione specifica di .NET Core come destinazione. Il runtime .NET Core di destinazione deve trovarsi nel computer in cui si vuole eseguire l'app. Ad esempio, se l'app ha come destinazione .NET Core 2.2, ogni computer in cui viene eseguita l'app deve avere il runtime .NET Core 2.2 installato. Come descritto nella sezione [Nozioni di base sulla pubblicazione](#publishing-basics), è possibile modificare il file di progetto per cambiare il framework di destinazione predefinito o per impostare come destinazione più framework.

La pubblicazione di un eseguibile dipendente dal framework crea un'app che esegue automaticamente il roll forward all'ultima patch di protezione .NET Core disponibile nel sistema che esegue l'app. Per altre informazioni sul binding di versione in fase di compilazione, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md#framework-dependent-apps-roll-forward).

Per pubblicare un eseguibile dipendente dal framework è necessario usare le opzioni seguenti con il comando `dotnet publish` (ad eccezione di .NET Core 3.x con la piattaforma corrente come destinazione):

- `-r <RID>`
  Questa opzione usa un identificatore relativo (RID) per specificare la piattaforma di destinazione. Per un elenco degli identificatori di runtime, vedere [Catalogo RID di .NET Core](../rid-catalog.md).

- `--self-contained false` Questa opzione indica a .NET Core SDK di creare un eseguibile come eseguibile dipendente dal framework.

Ogni volta che viene usata l'opzione `-r`, il percorso della cartella di output viene modificato in: `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`

Se si usa l'[app di esempio](#sample-app), eseguire `dotnet publish -f netcoreapp2.2 -r win10-x64 --self-contained false`. Questo comando crea l'eseguibile seguente: `./bin/Debug/netcoreapp2.2/win10-x64/publish/apptest1.exe`

> [!NOTE]
> È possibile ridurre le dimensioni totali della distribuzione abilitando la **modalità invariante della globalizzazione**. La modalità invariante della globalizzazione è utile per le applicazioni che non sono compatibili a livello globale e possono usare le convenzioni di formattazione, le convenzioni sulla combinazione di maiuscole e minuscole, il confronto tra stringhe e l'ordinamento delle [impostazioni cultura invarianti](xref:System.Globalization.CultureInfo.InvariantCulture). Per altre informazioni sulla **modalità invariante della globalizzazione** e su come abilitarla, vedere [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) (Modalità invariante della globalizzazione di .NET Core)

## <a name="self-contained-deployment"></a>Distribuzione autonoma

Quando si pubblica una distribuzione autonoma, .NET Core SDK crea un eseguibile specifico della piattaforma. La pubblicazione di una distribuzione autonoma include tutti i file .NET Core necessari per eseguire l'app ma non include le [dipendenze native di .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md). Queste dipendenze devono essere presenti nel sistema prima dell'esecuzione dell'app.

La pubblicazione di una distribuzione autonoma crea un'app che non esegue il roll forward alla versione più recente disponibile della patch di protezione di .NET Core. Per altre informazioni sul binding di versione in fase di compilazione, vedere [Selezionare la versione di .NET Core da usare](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).

È necessario usare le opzioni seguenti con il comando `dotnet publish` per pubblicare una distribuzione autonoma:

- `-r <RID>`
  Questa opzione usa un identificatore relativo (RID) per specificare la piattaforma di destinazione. Per un elenco degli identificatori di runtime, vedere [Catalogo RID di .NET Core](../rid-catalog.md).

- `--self-contained true` Questa opzione indica a .NET Core SDK di creare un eseguibile come distribuzione autonoma.

> [!NOTE]
> È possibile ridurre le dimensioni totali della distribuzione abilitando la **modalità invariante della globalizzazione**. La modalità invariante della globalizzazione è utile per le applicazioni che non sono compatibili a livello globale e possono usare le convenzioni di formattazione, le convenzioni sulla combinazione di maiuscole e minuscole, il confronto tra stringhe e l'ordinamento delle [impostazioni cultura invarianti](xref:System.Globalization.CultureInfo.InvariantCulture). Per altre informazioni sulla **modalità invariante della globalizzazione** e su come abilitarla, vedere [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) (Modalità invariante della globalizzazione di .NET Core)

## <a name="see-also"></a>Vedere anche

- [Distribuzione di applicazioni .NET Core](index.md)
- [Catalogo dei RID (Runtime IDentifier) di .NET Core](../rid-catalog.md)
