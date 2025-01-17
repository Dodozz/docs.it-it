---
title: Convertire un'app Windows Forms in .NET Core 3.0
description: Illustra come convertire un'applicazione Windows Forms .NET Framework in .NET Core 3.0 per Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/01/2019
ms.custom: ''
ms.openlocfilehash: aebfaa85338e014ca47256b85a1bd6529ad803bb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327165"
---
# <a name="how-to-port-a-windows-forms-desktop-app-to-net-core"></a>Procedura: Convertire un'app desktop Windows Forms in .NET Core

Questo articolo descrive come convertire un'app desktop basata su Windows Forms da .NET Framework a .NET Core 3.0. .NET Core SDK 3.0 include il supporto per le applicazioni Windows Forms. Windows Forms è ancora un framework solo per Windows e supporta l'esecuzione solo in Windows. Questo esempio usa l'interfaccia della riga di comando di .NET Core SDK per creare e gestire il progetto.

In questo articolo vengono usati vari nomi per identificare i tipi di file usati per la migrazione. Durante la migrazione del progetto personale i file verranno denominati in modo diverso, pertanto abbinarli mentalmente a quelli elencati di seguito:

| File | Description |
| ---- | ----------- |
| **MyApps.sln** | Nome del file di soluzione. |
| **MyForms.csproj** | Nome del progetto Windows Forms di .NET Framework da convertire. |
| **MyFormsCore.csproj** | Nome del nuovo progetto .NET Core creato. |
| **MyAppCore.exe** | Eseguibile dell'app Windows Forms .NET Core. |

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per tutte le operazioni di progettazione che si vogliono eseguire.

  Installare i carichi di lavoro di Visual Studio seguenti:
  - Sviluppo per desktop .NET
  - Sviluppo multipiattaforma .NET Core

- Un progetto Windows Forms funzionante in una soluzione che viene compilata ed eseguita senza problemi.
- Il progetto deve essere codificato in C#. 
- Installare l'anteprima più recente di [.NET Core 3.0](https://aka.ms/netcore3download).

>[!NOTE]
>**Visual Studio 2017** non supporta progetti .NET Core 3.0. **Visual Studio 2019** supporta i progetti .NET Core 3.0, ma non supporta ancora la finestra di progettazione grafica per i progetti Windows Forms .NET Core 3.0. Per usare la finestra di progettazione visiva, è necessario avere un progetto Windows Forms .NET nella soluzione che condivide i file di modulo con il progetto .NET Core.

### <a name="consider"></a>Consider

Per la conversione di un'applicazione Windows Forms di .NET Framework, esistono alcuni aspetti da considerare.

01. Controllare che l'applicazione sia un buon candidato per la migrazione.

    Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per determinare se sarà possibile eseguire la migrazione del progetto a .NET Core 3.0. Se il progetto presenta problemi con .NET Core 3.0, l'analizzatore consente di identificarli.

01. Si usa una versione diversa di Windows Forms.

    In concomitanza con il rilascio di .NET Core 3.0 Preview 1, Windows Forms è stato reso disponibile come open source su GitHub. Il codice per .NET Core Windows Forms è un fork della base di codice di .NET Framework Windows Forms. È possibile che esistano alcune differenze che non consentono la conversione dell'app.

01. [Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.

    Alcune API che sono disponibili in .NET Framework non sono disponibili in .NET Core 3.0. [Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può essere utile per rendere l'app Windows Forms compatibile con .NET Core.

01. Aggiornare i pacchetti NuGet usati dal progetto.

    È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione. Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente. Verificare che l'applicazione venga compilata correttamente. Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.

01. Visual Studio 2019 non supporta ancora Progettazione Windows Forms per .NET Core 3.0

    Attualmente, è necessario mantenere il file di progetto .NET Framework Windows Forms esistente se si vuole usare la finestra di progettazione dei moduli da Visual Studio.

## <a name="create-a-new-sdk-project"></a>Creare un nuovo progetto SDK

Il nuovo progetto .NET Core 3.0 creato deve essere in una directory diversa dal progetto .NET Framework. Se si trovano entrambi nella stessa directory, è possibile che si verifichino conflitti con i file generati nella directory **obj**. In questo esempio, si creerà una directory denominata **MyFormsAppCore** nella directory **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore      <--- New folder for core project
```

Successivamente, è necessario creare il progetto **MyFormsCore.csproj** nella directory **MyFormsAppCore**. È possibile creare questo file manualmente usando l'editor di testo preferito. Incollare il codice XML seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

Se non si vuole creare manualmente il file di progetto, è possibile usare Visual Studio o .NET Core SDK per generare il progetto. Tuttavia, è necessario eliminare tutti gli altri file generati dal modello di progetto, ad eccezione del file di progetto. Per usare l'SDK, eseguire il comando seguente dalla directory **SolutionFolder**:

```cli
dotnet new winforms -o MyFormsAppCore -n MyFormsCore
```

Dopo aver creato **MyFormsCore.csproj**, la struttura della directory dovrebbe essere simile alla seguente:

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
└───MyFormsAppCore
    └───MyFormsCore.csproj
```

È opportuno aggiungere il progetto **MyFormsCore.csproj** alla soluzione **MyApps.sln** con Visual Studio o l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:

```cli
dotnet sln add .\MyFormsAppCore\MyFormsCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Correggere la generazione delle informazioni sull'assembly

I progetti Windows Forms che sono stati creati con .NET Framework includono un file `AssemblyInfo.cs` che contiene gli attributi dell'assembly, ad esempio la versione dell'assembly da generare. I progetti in stile SDK generano automaticamente queste informazioni in base al file di progetto SDK. La presenza di entrambi i tipi di "informazioni sull'assembly" crea un conflitto. Per risolvere questo problema, disabilitare la generazione automatica, che impone l'uso del file `AssemblyInfo.cs` esistente nel progetto.

Sono disponibili tre impostazioni da aggiungere al nodo `<PropertyGroup>` principale. 

- **GenerateAssemblyInfo**\
Quando si imposta questa proprietà su `false`, non verranno generati gli attributi dell'assembly. Ciò consente di evitare il conflitto con il file `AssemblyInfo.cs` esistente dal progetto .NET Framework.

- **AssemblyName**\
Il valore di questa proprietà è il file binario di output creato durante la compilazione. Non è necessario aggiungere un'estensione al nome. Ad esempio, `MyCoreApp` produce `MyCoreApp.exe`.

- **RootNamespace**\
Spazio dei nomi predefinito usato dal progetto. Deve corrispondere allo spazio dei nomi predefinito del progetto .NET Framework.

Aggiungere questi tre elementi al nodo `<PropertyGroup>` nel file `MyFormsCore.csproj`:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>WindowsFormsApp1</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Aggiungere codice sorgente

Il progetto **MyFormsCore.csproj** per il momento non compila alcun codice. Per impostazione predefinita, i progetti .NET Core includono automaticamente tutto il codice sorgente nella directory corrente e in eventuali directory figlio. È necessario configurare il progetto per includere il codice dal progetto .NET Framework usando un percorso relativo. Se il progetto .NET Framework usava file **resx** per le icone e le risorse dei moduli, sarà necessario includere anche questi. 

Aggiungere il nodo `<ItemGroup>` seguente al progetto. Ogni istruzione include un criterio GLOB per i file che include le directory figlio.

```xml
  <ItemGroup>
    <Compile Include="..\MyFormsApp\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
  </ItemGroup>
```

In alternativa, è possibile creare una voce `<Compile>` o `<EmbeddedResource>` per ogni file nel progetto .NET Framework.

## <a name="add-nuget-packages"></a>Aggiungere pacchetti NuGet

Aggiungere al progetto .NET Core ogni pacchetto NuGet a cui fa riferimento il progetto .NET Framework. 

È molto probabile che l'app Windows Forms di .NET Framework includa un file **packages.config** che contiene un elenco di tutti i pacchetti NuGet a cui fa riferimento il progetto. È possibile esaminare questo elenco per determinare quali pacchetti NuGet aggiungere al progetto .NET Core. Ad esempio, se il progetto .NET Framework fa riferimento ai pacchetti NuGet `MetroFramework`, `MetroFramework.Design` e `MetroFramework.Fonts`, aggiungerli al progetto con Visual Studio o l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Design
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package MetroFramework.Fonts
```

I comandi precedenti consentono di aggiungere i riferimenti NuGet seguenti al progetto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="MetroFramework" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Design" Version="1.2.0.3" />
    <PackageReference Include="MetroFramework.Fonts" Version="1.2.0.3" />
  </ItemGroup>
```

## <a name="port-control-libraries"></a>Convertire le librerie di controlli

Se è necessario convertire un progetto di libreria di controlli di Windows Forms, le istruzioni sono le stesse valide per la conversione di un progetto di app Windows Forms di .NET Framework, fatta eccezione per alcune impostazioni. Inoltre, anziché compilare un file eseguibile, si esegue la compilazione in una raccolta. La differenza tra il progetto eseguibile e il progetto di libreria, oltre ai percorsi dei GLOB per i file che includono il codice sorgente, è minima.

Riprendendo l'esempio del passaggio precedente, è possibile procedere espandendo i progetti e i file usati.

| File | Description |
| ---- | ----------- |
| **MyApps.sln** | Nome del file di soluzione. |
| **MyControls.csproj** | Nome del progetto per controlli Windows Forms di .NET Framework da convertire. |
| **MyControlsCore.csproj** | Nome del nuovo progetto di libreria .NET Core creato. |
| **MyCoreControls.dll** | Libreria di controlli Windows Forms .NET Core. |

```
SolutionFolder
├───MyApps.sln
├───MyFormsApp
│   └───MyForms.csproj
├───MyFormsAppCore
│   └───MyFormsCore.csproj
│
├───MyFormsControls
│   └───MyControls.csproj
└───MyFormsControlsCore
    └───MyControlsCore.csproj   <--- New project for core controls
```

Tenere conto delle differenze tra il progetto `MyControlsCore.csproj` e il progetto `MyFormsCore.csproj` creato in precedenza.

```diff
 <Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

   <PropertyGroup>
-    <OutputType>WinExe</OutputType>
     <TargetFramework>netcoreapp3.0</TargetFramework>
     <UseWindowsForms>true</UseWindowsForms>

     <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
-    <AssemblyName>MyCoreApp</AssemblyName>
-    <RootNamespace>WindowsFormsApp1</RootNamespace>
+    <AssemblyName>MyControlsCore</AssemblyName>
+    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
   </PropertyGroup>

   <ItemGroup>
-    <Compile Include="..\MyFormsApp\**\*.cs" />
-    <EmbeddedResource Include="..\MyFormsApp\**\*.resx" />
+    <Compile Include="..\MyFormsControls\**\*.cs" />
+    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
   </ItemGroup>

 </Project>
```

Di seguito è riportato un esempio dell'aspetto del file di progetto di libreria di controlli Windows Forms .NET Core:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreControls</AssemblyName>
    <RootNamespace>WindowsFormsControlLibrary1</RootNamespace>
  </PropertyGroup>
  
  <ItemGroup>
    <Compile Include="..\MyFormsControls\**\*.cs" />
    <EmbeddedResource Include="..\MyFormsControls\**\*.resx" />
  </ItemGroup>
  
</Project>
```

Come si può notare, il nodo `<OutputType>` è stato rimosso e per questo il compilatore produce una libreria anziché un file eseguibile per impostazione predefinita. Sono stati modificati `<AssemblyName>` e `<RootNamespace>`. In particolare, `<RootNamespace>` deve corrispondere allo spazio dei nomi della libreria di controlli Windows Forms da convertire. E, infine, i nodi `<Compile>` e `<EmbeddedResource>` sono stati modificati in modo da puntare alla cartella della libreria di controlli Windows Forms da convertire.

Successivamente, nel progetto **MyFormsCore.csproj** .NET Core principale aggiungere un riferimento alla nuova libreria di controlli Windows Forms .NET Core. Aggiungere un riferimento con Visual Studio o con l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj reference .\MyFormsControlsCore\MyControlsCore.csproj
```

Il comando precedente consente di aggiungere il codice seguente al progetto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <ProjectReference Include="..\MyFormsControlsCore\MyControlsCore.csproj" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Problemi di compilazione

Se si riscontrano problemi durante la compilazione dei progetti, è possibile che siano in uso alcune API solo per Windows disponibili in .NET Framework, ma non in .NET Core. È possibile provare ad aggiungere il pacchetto NuGet [Windows Compatibility Pack][compat-pack] al progetto. Questo pacchetto può essere eseguito solo in Windows e aggiunge circa 20.000 API Windows ai progetti .NET Core e .NET Standard.

```cli
dotnet add .\MyFormsAppCore\MyFormsCore.csproj package Microsoft.Windows.Compatibility
```

Il comando precedente consente di aggiungere il codice seguente al progetto **MyFormsCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="windows-forms-designer"></a>Progettazione Windows Form

Come descritto in dettaglio in questo articolo, Visual Studio 2019 supporta solo Progettazione Windows Form nei progetti .NET Framework. È possibile creare un progetto .NET Core affiancato per testare il progetto .NET Core mentre si usa progetto .NET Framework per la progettazione dei moduli. Il file di soluzione include sia i progetti .NET Framework che .NET Core. Aggiungere e progettare i moduli e i controlli nel progetto .NET Framework e, in base ai criteri GLOB per i file aggiunti ai progetti .NET Core, qualsiasi file nuovo o modificato verrà incluso automaticamente nei progetti .NET Core.

Quando Visual Studio 2019 supporterà la finestra di progettazione per Windows Forms, sarà possibile copiare e incollare il contenuto del file di progetto .NET Core nel file di progetto .NET Framework. Eliminare quindi i criteri GLOB per i file aggiunti con gli elementi `<Source>` e `<EmbeddedResource>`. Correggere i percorsi per qualsiasi riferimento del progetto usato dall'app. In questo modo il progetto .NET Framework viene effettivamente aggiornato a .NET Core.
 
## <a name="next-steps"></a>Passaggi successivi

* Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].
* Guardare un [video sulla conversione](https://www.youtube.com/watch?v=upVQEUc_KwU) del progetto Windows Forms di .NET Framework in .NET Core.

[compat-pack]: windows-compat-pack.md
