---
title: Comando dotnet-add reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: 6e0ca40e701b62dcc18147f9de83cafa6aa2f50f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421997"
---
# <a name="dotnet-add-reference"></a>dotnet-add reference

**Questo articolo si applica a: ✓** .NET Core 1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nome

`dotnet add reference`: aggiunge riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>Description

Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto. Dopo l'esecuzione del comando, al file di progetto vengono aggiunti gli elementi [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items).

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argomenti

* **`PROJECT`**

  Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

* **`PROJECT_REFERENCES`**

  Riferimenti da progetto a progetto da aggiungere. Specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.

## <a name="options"></a>Opzioni

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`-f|--framework <FRAMEWORK>`**

  Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

* **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

## <a name="examples"></a>Esempi

* Aggiungere un riferimento al progetto:

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* Aggiungere più riferimenti al progetto nella directory corrente:

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
