---
title: -subsystemversion (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: cf1fb74f5d13817448bec2bcdc37510ff82f024d
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377900"
---
# <a name="-subsystemversion-c-compiler-options"></a>-subsystemversion (opzioni del compilatore C#)

Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, determinando le versioni di Windows in cui è possibile eseguire il file eseguibile. In genere, questa opzione assicura che il file eseguibile possa sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.

> [!NOTE]
>  Per specificare il sottosistema stesso, usare l'opzione del compilatore [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).

## <a name="syntax"></a>Sintassi

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a>Parametri

`major.minor`

Versione minima richiesta per il sottosistema, espressa in una notazione del punto per le versioni principali e secondarie. Ad esempio, è possibile specificare che un'applicazione non può essere eseguita su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento. È necessario specificare i valori per `major` e `minor` come numeri interi.

Gli zeri iniziali della versione `minor` non modificano la versione, a differenza degli zeri finali. Ad esempio, 6.1 e 6.01 si fanno riferimento alla stessa versione, ma 6.10 fa riferimento a una versione diversa. È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.

## <a name="remarks"></a>Osservazioni

Nella tabella seguente sono elencate le versioni comuni del sottosistema di Windows.

|Versione di Windows|Versione del sottosistema|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|

## <a name="default-values"></a>Valori predefiniti

Il valore predefinito dell'opzione del compilatore **-subsystemversion** dipende dalle condizioni elencate di seguito:

- Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:

  - [/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)

  - [/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)

  - [-platform:arm](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)

- Il valore predefinito è 6.00 se si usa MSBuild, se la destinazione è .NET Framework 4.5 e se non è stata impostata una delle opzioni del compilatore specificate in precedenza in questo elenco.

- Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.

## <a name="setting-this-option"></a>Impostazione di questa opzione

Per impostare l'opzione del compilatore **-subsystemversion** in Visual Studio, è necessario aprire il file con estensione csproj e specificare un valore per la proprietà `SubsystemVersion` nel codice XML di MSBuild. Non è possibile impostare questa opzione nell'IDE di Visual Studio. Per altre informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [Proprietà di progetto MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
