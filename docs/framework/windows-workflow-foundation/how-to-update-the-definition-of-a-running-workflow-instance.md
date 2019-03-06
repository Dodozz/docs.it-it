---
title: "Procedura: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26dfac36-ae23-4909-9867-62495b55fb5e
ms.openlocfilehash: 1f5980ed360e8dfb4aaac92e1e5e7236ffb9f409
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376593"
---
# <a name="how-to-update-the-definition-of-a-running-workflow-instance"></a><span data-ttu-id="72f10-102">Procedura: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione</span><span class="sxs-lookup"><span data-stu-id="72f10-102">How to: Update the Definition of a Running Workflow Instance</span></span>
<span data-ttu-id="72f10-103">L'aggiornamento dinamico fornisce agli sviluppatori di applicazioni del flusso di lavoro un meccanismo per aggiornare la definizione del flusso di lavoro di un'istanza persistente del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="72f10-104">La modifica richiesta può servire a implementare la correzione di un bug, nuovi requisiti o modifiche impreviste.</span><span class="sxs-lookup"><span data-stu-id="72f10-104">The required change can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="72f10-105">Questo passaggio dell'esercitazione viene illustrato come utilizzare aggiornamento dinamico per modificare le istanze persistenti del `v1` numero un'ipotesi del flusso di lavoro in modo che corrisponda alla nuova funzionalità introdotta [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="72f10-105">This step in the tutorial demonstrates how to use dynamic update to modify  persisted instances of the `v1` number guessing workflow to match the new functionality introduced in [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="72f10-106">Per scaricare una versione completa o visualizzare una procedura dettagliata video dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="72f10-106">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="72f10-107">Contenuto dell'argomento</span><span class="sxs-lookup"><span data-stu-id="72f10-107">In this topic</span></span>  
  
-   [<span data-ttu-id="72f10-108">Per creare il progetto CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="72f10-108">To create the CreateUpdateMaps project</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateProject)  
  
-   [<span data-ttu-id="72f10-109">Per aggiornare StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-109">To update StateMachineNumberGuessWorkflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StateMachine)  
  
-   [<span data-ttu-id="72f10-110">Per aggiornare FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-110">To update FlowchartNumberGuessWorkflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Flowchart)  
  
-   [<span data-ttu-id="72f10-111">Per aggiornare SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-111">To update SequentialNumberGuessWorkflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_Sequential)  
  
-   [<span data-ttu-id="72f10-112">Per compilare ed eseguire l'applicazione CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="72f10-112">To build and run the CreateUpdateMaps application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_CreateUpdateMaps)  
  
-   [<span data-ttu-id="72f10-113">Per compilare l'assembly del flusso di lavoro aggiornata</span><span class="sxs-lookup"><span data-stu-id="72f10-113">To build the updated workflow assembly</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAssembly)  
  
-   [<span data-ttu-id="72f10-114">Per aggiornare WorkflowVersionMap con le nuove versioni</span><span class="sxs-lookup"><span data-stu-id="72f10-114">To update WorkflowVersionMap with the new versions</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [<span data-ttu-id="72f10-115">Per applicare gli aggiornamenti dinamici</span><span class="sxs-lookup"><span data-stu-id="72f10-115">To apply the dynamic updates</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_ApplyUpdate)  
  
-   [<span data-ttu-id="72f10-116">Per eseguire l'applicazione con i flussi di lavoro aggiornate</span><span class="sxs-lookup"><span data-stu-id="72f10-116">To run the application with the updated workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_BuildAndRun)  
  
-   [<span data-ttu-id="72f10-117">Per abilitare l'avvio delle versioni precedenti dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="72f10-117">To enable starting previous versions of the workflows</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md#BKMK_StartPreviousVersions)  
  
### <a name="BKMK_CreateProject"></a> <span data-ttu-id="72f10-118">Per creare il progetto CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="72f10-118">To create the CreateUpdateMaps project</span></span>  
  
1.  <span data-ttu-id="72f10-119">Fare doppio clic su **WF45GettingStartedTutorial** nelle **Esplora soluzioni** e scegliere **Add**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="72f10-119">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="72f10-120">Nel **Installed** nodo, seleziona **Visual c#**, **Windows** (oppure **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="72f10-120">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72f10-121">A seconda del linguaggio di programmazione configurato come linguaggio principale in Visual Studio, sotto il nodo **Altri linguaggi** del nodo **Installato** viene visualizzato il nodo **Visual C#** o **Visual Basic** .</span><span class="sxs-lookup"><span data-stu-id="72f10-121">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="72f10-122">Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionata l'opzione **.NET Framework 4.5** .</span><span class="sxs-lookup"><span data-stu-id="72f10-122">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="72f10-123">Selezionare **applicazione Console** dalle **Windows** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-123">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="72f10-124">Tipo di **CreateUpdateMaps** nel **Name** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="72f10-124">Type **CreateUpdateMaps** into the **Name** box and click **OK**.</span></span>

3.  <span data-ttu-id="72f10-125">Fare doppio clic su **CreateUpdateMaps** nelle **Esplora soluzioni** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="72f10-125">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Add Reference**.</span></span>

4.  <span data-ttu-id="72f10-126">Selezionare **Framework** dal **assembly** nodo il **Aggiungi riferimento** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-126">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="72f10-127">Tipo di **System. Activities** nel **cerca assembly** casella per filtrare gli assembly e rendere più semplice selezionare i riferimenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="72f10-127">Type **System.Activities** into the **Search Assemblies** box to filter the assemblies and make the desired references easier to select.</span></span>

5.  <span data-ttu-id="72f10-128">Selezionare la casella di controllo accanto **System. Activities** dalle **i risultati della ricerca** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-128">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

6.  <span data-ttu-id="72f10-129">Tipo di **serializzazione** nel **cerca assembly** casella e selezionare la casella di controllo accanto a **Serialization** dal **i risultati della ricerca**  elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-129">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

7.  <span data-ttu-id="72f10-130">Tipo di **System. XAML** nel **cerca assembly** casella e selezionare la casella di controllo accanto a **System. XAML** dal **i risultati della ricerca** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-130">Type **System.Xaml** into the **Search Assemblies** box, and check the checkbox beside **System.Xaml** from the **Search Results** list.</span></span>

8.  <span data-ttu-id="72f10-131">Fare clic su **OK** per chiudere **gestione riferimenti** e aggiungere i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="72f10-131">Click **OK** to close **Reference Manager** and add the references.</span></span>

9. <span data-ttu-id="72f10-132">Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="72f10-132">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.Statements
    Imports System.Xaml
    Imports System.Reflection
    Imports System.IO
    Imports System.Activities.XamlIntegration
    Imports System.Activities.DynamicUpdate
    Imports System.Runtime.Serialization
    Imports Microsoft.VisualBasic.Activities
    ```

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    using System.IO;
    using System.Xaml;
    using System.Reflection;
    using System.Activities.XamlIntegration;
    using System.Activities.DynamicUpdate;
    using System.Runtime.Serialization;
    using Microsoft.CSharp.Activities;
    ```

10. <span data-ttu-id="72f10-133">Aggiungere i due membri stringa seguenti alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-133">Add the following two string members to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const mapPath = "..\..\..\PreviousVersions"
    Const definitionPath = "..\..\..\NumberGuessWorkflowActivities_du"
    ```

    ```csharp
    const string mapPath = @"..\..\..\PreviousVersions";
    const string definitionPath = @"..\..\..\NumberGuessWorkflowActivities_du";
    ```

11. <span data-ttu-id="72f10-134">Aggiungere il seguente metodo `StartUpdate` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-134">Add the following `StartUpdate` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-135">Tramite questo metodo viene caricata la definizione del flusso di lavoro XAML specificata in un oggetto `ActivityBuilder`, quindi viene chiamato `DynamicUpdate.PrepareForUpdate`.</span><span class="sxs-lookup"><span data-stu-id="72f10-135">This method loads up the specified xaml workflow definition into an `ActivityBuilder`, and then calls `DynamicUpdate.PrepareForUpdate`.</span></span> <span data-ttu-id="72f10-136">Tramite `PrepareForUpdate` viene creata una copia della definizione del flusso di lavoro nell'oggetto `ActivityBuilder`.</span><span class="sxs-lookup"><span data-stu-id="72f10-136">`PrepareForUpdate` makes a copy of the workflow definition inside the `ActivityBuilder`.</span></span> <span data-ttu-id="72f10-137">Al termine della modifica della definizione del flusso di lavoro, questa copia viene usata insieme alla definizione in questione modificata per creare il mapping di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="72f10-137">After the workflow definition is modified, this copy is used along with the modified workflow definition to create the update map.</span></span>

    ```vb
    Private Function StartUpdate(name As String) As ActivityBuilder
        'Create the XamlXmlReaderSettings.
        Dim readerSettings As XamlReaderSettings = New XamlXmlReaderSettings()
        'In the XAML the "local" namespace referes to artifacts that come from
        'the same project as the XAML. When loading XAML if the currently executing
        'assembly is not the same assembly that was referred to as "local" in the XAML
        'LocalAssembly must be set to the assembly containing the artifacts.
        'Assembly.LoadFile requires an absolute path so convert this relative path
        'to an absolute path.
        readerSettings.LocalAssembly = Assembly.LoadFile(
            Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))

        Dim fullPath As String = Path.Combine(definitionPath, name)
        Dim xamlReader As XamlXmlReader = New XamlXmlReader(fullPath, readerSettings)

        'Load the workflow definition into an ActivityBuilder.
        Dim wf As ActivityBuilder = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))

        'PrepareForUpdate makes a copy of the workflow definition in the
        'ActivityBuilder that is used for comparison when the update
        'map is created.
        DynamicUpdateServices.PrepareForUpdate(wf)

        Return wf
    End Function
    ```

    ```csharp
    private static ActivityBuilder StartUpdate(string name)
    {
        // Create the XamlXmlReaderSettings.
        XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
        {
            // In the XAML the "local" namespace referes to artifacts that come from
            // the same project as the XAML. When loading XAML if the currently executing
            // assembly is not the same assembly that was referred to as "local" in the XAML
            // LocalAssembly must be set to the assembly containing the artifacts.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            LocalAssembly = Assembly.LoadFile(
                Path.GetFullPath(Path.Combine(mapPath, "NumberGuessWorkflowActivities_v1.dll")))
        };

        string path = Path.Combine(definitionPath, name);
        XamlXmlReader xamlReader = new XamlXmlReader(path, readerSettings);

        // Load the workflow definition into an ActivityBuilder.
        ActivityBuilder wf = XamlServices.Load(
            ActivityXamlServices.CreateBuilderReader(xamlReader))
            as ActivityBuilder;

        // PrepareForUpdate makes a copy of the workflow definition in the
        // ActivityBuilder that is used for comparison when the update
        // map is created.
        DynamicUpdateServices.PrepareForUpdate(wf);

        return wf;
    }
    ```

12. <span data-ttu-id="72f10-138">Successivamente, aggiungere l'oggetto `CreateUpdateMethod` seguente alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-138">Next, add the following `CreateUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-139">In questo modo viene creato un mapping di aggiornamento dinamico tramite la chiamata a DynamicUpdateServices.CreateUpdateMap, quindi viene salvato il mapping di aggiornamento usando il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="72f10-139">This creates a dynamic update map by calling DynamicUpdateServices.CreateUpdateMap, and then saves the update map using the specified name.</span></span> <span data-ttu-id="72f10-140">In questo mapping di aggiornamento sono contenute le informazioni richieste dal runtime del flusso di lavoro per aggiornare un'istanza persistente del flusso di lavoro che è stata avviata usando la definizione originale del flusso di lavoro contenuta nell'oggetto `ActivityBuilder` in modo che venga completata usando la definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-140">This update map contains the information needed by the workflow runtime to update a persisted workflow instance that was started using the original workflow definition contained in the `ActivityBuilder` so that it completes using the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateUpdateMaps(wf As ActivityBuilder, name As String)
        'Create the UpdateMap.
        Dim map As DynamicUpdateMap =
            DynamicUpdateServices.CreateUpdateMap(wf)

        'Serialize it to a file.
        Dim mapFullPath As String = Path.Combine(mapPath, name)
        Dim sz As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
        Using fs As FileStream = File.Open(mapFullPath, FileMode.Create)
            sz.WriteObject(fs, map)
        End Using
    End Sub
    ```

    ```csharp
    private static void CreateUpdateMaps(ActivityBuilder wf, string name)
    {
        // Create the UpdateMap.
        DynamicUpdateMap map =
            DynamicUpdateServices.CreateUpdateMap(wf);

        // Serialize it to a file.
        string path = Path.Combine(mapPath, name);
        DataContractSerializer sz = new DataContractSerializer(typeof(DynamicUpdateMap));
        using (FileStream fs = System.IO.File.Open(path, FileMode.Create))
        {
            sz.WriteObject(fs, map);
        }
    }
    ```

13. <span data-ttu-id="72f10-141">Aggiungere il seguente metodo `SaveUpdatedDefinition` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-141">Add the following `SaveUpdatedDefinition` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-142">Tramite questo metodo la definizione aggiornata del flusso di lavoro viene salvata una volta creato il mapping di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="72f10-142">This method saves the updated workflow definition once the update map is created.</span></span>

    ```vb
    Private Sub SaveUpdatedDefinition(wf As ActivityBuilder, name As String)
        Dim xamlPath As String = Path.Combine(definitionPath, name)
        Dim sw As StreamWriter = File.CreateText(xamlPath)
        Dim xw As XamlWriter = ActivityXamlServices.CreateBuilderWriter(
            New XamlXmlWriter(sw, New XamlSchemaContext()))
        XamlServices.Save(xw, wf)
        sw.Close()
    End Sub
    ```

    ```csharp
    private static void SaveUpdatedDefinition(ActivityBuilder wf, string name)
    {
        string xamlPath = Path.Combine(definitionPath, name);
        StreamWriter sw = File.CreateText(xamlPath);
        XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(
            new XamlXmlWriter(sw, new XamlSchemaContext()));
        XamlServices.Save(xw, wf);
        sw.Close();
    }
    ```

### <a name="BKMK_StateMachine"></a> <span data-ttu-id="72f10-143">Per aggiornare StateMachineNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-143">To update StateMachineNumberGuessWorkflow</span></span>

1.  <span data-ttu-id="72f10-144">Aggiungere un oggetto `CreateStateMachineUpdateMap` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-144">Add a `CreateStateMachineUpdateMap` to the `Program` class (or `Module1`).</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()

    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
    }
    ```

2.  <span data-ttu-id="72f10-145">Effettuare una chiamata a `StartUpdate`, quindi ottenere un riferimento all'attività `StateMachine` radice del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-145">Make a call to `StartUpdate` and then get a reference to the root `StateMachine` activity of the workflow.</span></span>

    ```vb
    Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

    'Get a reference to the root StateMachine activity.
    Dim sm As StateMachine = wf.Implementation
    ```

    ```csharp
    ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

    // Get a reference to the root StateMachine activity.
    StateMachine sm = wf.Implementation as StateMachine;
    ```

3.  <span data-ttu-id="72f10-146">Successivamente, aggiornare le espressioni delle due `WriteLine` le attività che consentono di visualizzare se l'ipotesi dell'utente è troppo alta o troppo basso in modo che corrispondano gli aggiornamenti apportati nel [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="72f10-146">Next, update the expressions of the two `WriteLine` activities that display whether the user's guess is too high or too low so that they match the updates made in [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

    ```vb
    'Update the Text of the two WriteLine activities that write the
    'results of the user's guess. They are contained in the workflow as the
    'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

    'Update the "too low" message.
    Dim tooLow As WriteLine = guessLow.Then
    tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

    'Update the "too high" message.
    Dim tooHigh As WriteLine = guessLow.Else
    tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")
    ```

    ```csharp
    // Update the Text of the two WriteLine activities that write the
    // results of the user's guess. They are contained in the workflow as the
    // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
    If guessLow = sm.States[1].Transitions[1].Action as If;

    // Update the "too low" message.
    WriteLine tooLow = guessLow.Then as WriteLine;
    tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

    // Update the "too high" message.
    WriteLine tooHigh = guessLow.Else as WriteLine;
    tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");
    ```

4.  <span data-ttu-id="72f10-147">Successivamente, aggiungere una nuova attività `WriteLine` tramite cui viene visualizzato il messaggio di chiusura.</span><span class="sxs-lookup"><span data-stu-id="72f10-147">Next, add the new `WriteLine` activity that displays the closing message.</span></span>

    ```vb
    'Create the new WriteLine that displays the closing message.
    Dim wl As New WriteLine() With
    {
        .Text = New VisualBasicValue(Of String) _
            ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
    }

    'Add it as the Action for the Guess Correct transition. The Guess Correct
    'transition is the first transition of States[1]. The transitions are listed
    'at the bottom of the State activity designer.
    sm.States(1).Transitions(0).Action = wl
    ```

    ```csharp
    // Create the new WriteLine that displays the closing message.
    WriteLine wl = new WriteLine
    {
        Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
    };

    // Add it as the Action for the Guess Correct transition. The Guess Correct
    // transition is the first transition of States[1]. The transitions are listed
    // at the bottom of the State activity designer.
    sm.States[1].Transitions[0].Action = wl;
    ```

5.  <span data-ttu-id="72f10-148">Dopo aver aggiornato il flusso di lavoro, chiamare `CreateUpdateMaps` e `SaveUpdatedDefinition`.</span><span class="sxs-lookup"><span data-stu-id="72f10-148">After the workflow is updated, call `CreateUpdateMaps` and `SaveUpdatedDefinition`.</span></span> <span data-ttu-id="72f10-149">Tramite `CreateUpdateMaps` viene creato e salvato l'oggetto `DynamicUpdateMap`, mentre tramite `SaveUpdatedDefinition` viene salvata la definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-149">`CreateUpdateMaps` creates and saves the `DynamicUpdateMap`, and `SaveUpdatedDefinition` saves the updated workflow definition.</span></span>

    ```vb
    'Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

    'Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    ```

    ```csharp
    // Create the update map.
    CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

    // Save the updated workflow definition.
    SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    ```

     <span data-ttu-id="72f10-150">Nell'esempio seguente viene mostrato il metodo `CreateStateMachineUpdateMap` completato.</span><span class="sxs-lookup"><span data-stu-id="72f10-150">The following example is the completed `CreateStateMachineUpdateMap` method.</span></span>

    ```vb
    Private Sub CreateStateMachineUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("StateMachineNumberGuessWorkflow.xaml")

        'Get a reference to the root StateMachine activity.
        Dim sm As StateMachine = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        Dim guessLow As Statements.If = sm.States(1).Transitions(1).Action

        'Update the "too low" message.
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Add it as the Action for the Guess Correct transition. The Guess Correct
        'transition is the first transition of States[1]. The transitions are listed
        'at the bottom of the State activity designer.
        sm.States(1).Transitions(0).Action = wl

        'Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateStateMachineUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("StateMachineNumberGuessWorkflow.xaml");

        // Get a reference to the root StateMachine activity.
        StateMachine sm = wf.Implementation as StateMachine;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the If activity in sm.States[1].Transitions[1].Action.
        If guessLow = sm.States[1].Transitions[1].Action as If;

        // Update the "too low" message.
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Create the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Add it as the Action for the Guess Correct transition. The Guess Correct
        // transition is the first transition of States[1]. The transitions are listed
        // at the bottom of the State activity designer.
        sm.States[1].Transitions[0].Action = wl;

        // Create the update map.
        CreateUpdateMaps(wf, "StateMachineNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "StateMachineNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_Flowchart"></a> <span data-ttu-id="72f10-151">Per aggiornare FlowchartNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-151">To update FlowchartNumberGuessWorkflow</span></span>

1.  <span data-ttu-id="72f10-152">Aggiungere l'oggetto `CreateFlowchartUpdateMethod` seguente alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-152">Add the following `CreateFlowchartUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-153">Questo metodo è simile a `CreateStateMachineUpdateMap`.</span><span class="sxs-lookup"><span data-stu-id="72f10-153">This method is similar to `CreateStateMachineUpdateMap`.</span></span> <span data-ttu-id="72f10-154">Inizia con una chiamata all'oggetto `StartUpdate`, consente di aggiornare la definizione del flusso di lavoro del diagramma di flusso, quindi termina salvando il mapping di aggiornamento e la definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-154">It starts with a call to `StartUpdate`, updates the flowchart workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateFlowchartUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("FlowchartNumberGuessWorkflow.xaml")

        'Get a reference to the root Flowchart activity.
        Dim fc As Flowchart = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'True and False action of the "Guess < Target" FlowDecision, which is
        'Nodes[4].
        Dim guessLow As FlowDecision = fc.Nodes(4)

        'Update the "too low" message.
        Dim trueStep As FlowStep = guessLow.True
        Dim tooLow As WriteLine = trueStep.Action
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")

        'Update the "too high" message.
        Dim falseStep As FlowStep = guessLow.False
        Dim tooHigh As WriteLine = falseStep.Action
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Create a FlowStep to hold the WriteLine.
        Dim closingStep As New FlowStep() With
        {
            .Action = wl
        }

        'Add this new FlowStep to the True action of the
        '"Guess = Guess" FlowDecision
        Dim guessCorrect As FlowDecision = fc.Nodes(3)
        guessCorrect.True = closingStep

        'Add the new FlowStep to the Nodes collection.
        'If closingStep was replacing an existing node then
        'we would need to remove that Step from the collection.
        'In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep)

        'Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateFlowchartUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("FlowchartNumberGuessWorkflow.xaml");

        // Get a reference to the root Flowchart activity.
        Flowchart fc = wf.Implementation as Flowchart;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // True and False action of the "Guess < Target" FlowDecision, which is
        // Nodes[4].
        FlowDecision guessLow = fc.Nodes[4] as FlowDecision;

        // Update the "too low" message.
        FlowStep trueStep = guessLow.True as FlowStep;
        WriteLine tooLow = trueStep.Action as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");

        // Update the "too high" message.
        FlowStep falseStep = guessLow.False as FlowStep;
        WriteLine tooHigh = falseStep.Action as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Create a FlowStep to hold the WriteLine.
        FlowStep closingStep = new FlowStep
        {
            Action = wl
        };

        // Add this new FlowStep to the True action of the
        // "Guess == Guess" FlowDecision
        FlowDecision guessCorrect = fc.Nodes[3] as FlowDecision;
        guessCorrect.True = closingStep;

        // Add the new FlowStep to the Nodes collection.
        // If closingStep was replacing an existing node then
        // we would need to remove that Step from the collection.
        // In this example there was no existing True step to remove.
        fc.Nodes.Add(closingStep);

        // Create the update map.
        CreateUpdateMaps(wf, "FlowchartNumberGuessWorkflow.map");

        //  Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "FlowchartNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_Sequential"></a> <span data-ttu-id="72f10-155">Per aggiornare SequentialNumberGuessWorkflow</span><span class="sxs-lookup"><span data-stu-id="72f10-155">To update SequentialNumberGuessWorkflow</span></span>

1.  <span data-ttu-id="72f10-156">Aggiungere l'oggetto `CreateSequentialUpdateMethod` seguente alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-156">Add the following `CreateSequentialUpdateMethod` to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-157">Questo metodo è simile ad altri due metodi.</span><span class="sxs-lookup"><span data-stu-id="72f10-157">This method is similar to the other two methods.</span></span> <span data-ttu-id="72f10-158">Inizia con una chiamata all'oggetto `StartUpdate`, consente di aggiornare la definizione del flusso di lavoro sequenziale, quindi termina salvando il mapping di aggiornamento e la definizione aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-158">It starts with a call to `StartUpdate`, updates the sequential workflow definition, and finishes by saving the update map and the updated workflow definition.</span></span>

    ```vb
    Private Sub CreateSequentialUpdateMap()
        Dim wf As ActivityBuilder = StartUpdate("SequentialNumberGuessWorkflow.xaml")

        'Get a reference to the root activity in the workflow.
        Dim rootSequence As Sequence = wf.Implementation

        'Update the Text of the two WriteLine activities that write the
        'results of the user's guess. They are contained in the workflow as the
        'Then and Else action of the "Guess < Target" If activity.
        'Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        Dim gameLoop As Statements.DoWhile = rootSequence.Activities(1)
        Dim gameBody As Sequence = gameLoop.Body
        Dim guessCorrect As Statements.If = gameBody.Activities(2)
        Dim guessLow As Statements.If = guessCorrect.Then
        Dim tooLow As WriteLine = guessLow.Then
        tooLow.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too low.""")
        Dim tooHigh As WriteLine = guessLow.Else
        tooHigh.Text = New VisualBasicValue(Of String)("Guess.ToString() & "" is too high.""")

        'Create the new WriteLine that displays the closing message.
        Dim wl As New WriteLine() With
        {
            .Text = New VisualBasicValue(Of String) _
                ("Guess.ToString() + "" is correct. You guessed it in "" & Turns.ToString() & "" turns.""")
        }

        'Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl)

        'Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map")

        'Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml")
    End Sub
    ```

    ```csharp
    private static void CreateSequentialUpdateMap()
    {
        ActivityBuilder wf = StartUpdate("SequentialNumberGuessWorkflow.xaml");

        // Get a reference to the root activity in the workflow.
        Sequence rootSequence = wf.Implementation as Sequence;

        // Update the Text of the two WriteLine activities that write the
        // results of the user's guess. They are contained in the workflow as the
        // Then and Else action of the "Guess < Target" If activity.
        // Sequence[1]->DoWhile->Body->Sequence[2]->If->Then->If
        DoWhile gameLoop = rootSequence.Activities[1] as DoWhile;
        Sequence gameBody = gameLoop.Body as Sequence;
        If guessCorrect = gameBody.Activities[2] as If;
        If guessLow = guessCorrect.Then as If;
        WriteLine tooLow = guessLow.Then as WriteLine;
        tooLow.Text = new CSharpValue<string>("Guess.ToString() + \" is too low.\"");
        WriteLine tooHigh = guessLow.Else as WriteLine;
        tooHigh.Text = new CSharpValue<string>("Guess.ToString() + \" is too high.\"");

        // Add the new WriteLine that displays the closing message.
        WriteLine wl = new WriteLine
        {
            Text = new CSharpValue<string>("Guess.ToString() + \" is correct. You guessed it in \" + Turns.ToString() + \" turns.\"")
        };

        // Insert it as the third activity in the root sequence
        rootSequence.Activities.Insert(2, wl);

        // Create the update map.
        CreateUpdateMaps(wf, "SequentialNumberGuessWorkflow.map");

        // Save the updated workflow definition.
        SaveUpdatedDefinition(wf, "SequentialNumberGuessWorkflow_du.xaml");
    }
    ```

### <a name="BKMK_CreateUpdateMaps"></a> <span data-ttu-id="72f10-159">Per compilare ed eseguire l'applicazione CreateUpdateMaps</span><span class="sxs-lookup"><span data-stu-id="72f10-159">To build and run the CreateUpdateMaps application</span></span>

1.  <span data-ttu-id="72f10-160">Aggiornare il metodo `Main` e aggiungere le seguenti tre chiamate ai metodi.</span><span class="sxs-lookup"><span data-stu-id="72f10-160">Update the `Main` method and add the following three method calls.</span></span> <span data-ttu-id="72f10-161">Questi metodi vengono aggiunti nelle sezioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="72f10-161">These methods are added in the following sections.</span></span> <span data-ttu-id="72f10-162">Tramite ciascun metodo viene aggiornato il flusso di lavoro per determinare il numero corrispondente e viene creato un oggetto `DynamicUpdateMap` mediante il quale vengono descritti gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="72f10-162">Each method updates the corresponding number guess workflow and creates a `DynamicUpdateMap` that describes the updates.</span></span>

    ```vb
    Sub Main()
        'Create the update maps for the changes needed to the v1 activities
        'so they match the v2 activities.
        CreateSequentialUpdateMap()
        CreateFlowchartUpdateMap()
        CreateStateMachineUpdateMap()
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        // Create the update maps for the changes needed to the v1 activities
        // so they match the v2 activities.
        CreateSequentialUpdateMap();
        CreateFlowchartUpdateMap();
        CreateStateMachineUpdateMap();
    }
    ```

2.  <span data-ttu-id="72f10-163">Fare doppio clic su **CreateUpdateMaps** nelle **Esplora soluzioni** e scegliere **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="72f10-163">Right-click **CreateUpdateMaps** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

3.  <span data-ttu-id="72f10-164">Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere CTRL+F5 per eseguire l'applicazione `CreateUpdateMaps`.</span><span class="sxs-lookup"><span data-stu-id="72f10-164">Press CTRL+SHIFT+B to build the solution, and then CTRL+F5 to run the `CreateUpdateMaps` application.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="72f10-165">Il `CreateUpdateMaps` applicazione non viene visualizzata alcuna informazione sullo stato durante l'esecuzione, ma se si osservano le **NumberGuessWorkflowActivities_du** cartella e il **PreviousVersions** cartella verrà visualizzato i file di definizione aggiornata del flusso di lavoro e i mapping di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="72f10-165">The `CreateUpdateMaps` application does not display any status information while running, but if you look in the **NumberGuessWorkflowActivities_du** folder and the **PreviousVersions** folder you will see the updated workflow definition files and the update maps.</span></span>

     <span data-ttu-id="72f10-166">Una volta creati i mapping di aggiornamento e aggiornate le definizioni del flusso di lavoro, il passaggio successivo consiste nel compilare un assembly aggiornato del flusso di lavoro contenente le definizioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="72f10-166">Once the update maps are created and the workflow definitions updated, the next step is to build an updated workflow assembly containing the updated definitions.</span></span>

### <a name="BKMK_BuildAssembly"></a> <span data-ttu-id="72f10-167">Per compilare l'assembly del flusso di lavoro aggiornata</span><span class="sxs-lookup"><span data-stu-id="72f10-167">To build the updated workflow assembly</span></span>

1.  <span data-ttu-id="72f10-168">Aprire una seconda istanza di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="72f10-168">Open a second instance of Visual Studio 2012.</span></span>

2.  <span data-ttu-id="72f10-169">Scegli **aperto**, **progetto/soluzione** dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="72f10-169">Choose **Open**, **Project/Solution** from the **File** menu.</span></span>

3.  <span data-ttu-id="72f10-170">Passare il **NumberGuessWorkflowActivities_du** creato nella cartella [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), selezionare **numberguessworkflowactivities. csproj** (oppure **vbproj**), fare clic su **Open**.</span><span class="sxs-lookup"><span data-stu-id="72f10-170">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), select **NumberGuessWorkflowActivities.csproj** (or **vbproj**), and click **Open**.</span></span>

4.  <span data-ttu-id="72f10-171">Nelle **Esplora soluzioni**, fare clic destro **sequentialnumberguessworkflow. XAML** e scegliere **Escludi dal progetto**.</span><span class="sxs-lookup"><span data-stu-id="72f10-171">In **Solution Explorer**, right click **SequentialNumberGuessWorkflow.xaml** and choose **Exclude From Project**.</span></span> <span data-ttu-id="72f10-172">Eseguire la stessa operazione **Flowchartnumberguessworkflow** e **Statemachinenumberguessworkflow**.</span><span class="sxs-lookup"><span data-stu-id="72f10-172">Do the same thing for **FlowchartNumberGuessWorkflow.xaml** and **StateMachineNumberGuessWorkflow.xaml**.</span></span> <span data-ttu-id="72f10-173">Questo passaggio consente di rimuovere le versioni precedenti delle definizioni del flusso di lavoro dal progetto.</span><span class="sxs-lookup"><span data-stu-id="72f10-173">This step removes the previous versions of the workflow definitions from the project.</span></span>

5.  <span data-ttu-id="72f10-174">Scegli **Aggiungi elemento esistente** dalle **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="72f10-174">Choose **Add Existing Item** from the **Project** menu.</span></span>

6.  <span data-ttu-id="72f10-175">Passare il **NumberGuessWorkflowActivities_du** creato nella cartella [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="72f10-175">Navigate to the **NumberGuessWorkflowActivities_du** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

7.  <span data-ttu-id="72f10-176">Scegli **i file XAML (\*XAML;\*. xoml)** dal **file di tipo** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="72f10-176">Choose **XAML Files (\*.xaml;\*.xoml)** from the **Files of type** drop-down list.</span></span>

8.  <span data-ttu-id="72f10-177">Selezionare **sequentialnumberguessworkflow_du. XAML**, **flowchartnumberguessworkflow_du. XAML**, e **statemachinenumberguessworkflow_du. XAML** e fare clic su  **Aggiungere**.</span><span class="sxs-lookup"><span data-stu-id="72f10-177">Select **SequentialNumberGuessWorkflow_du.xaml**, **FlowchartNumberGuessWorkflow_du.xaml**, and **StateMachineNumberGuessWorkflow_du.xaml** and click **Add**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="72f10-178">Premere CTRL e fare clic per selezionare più elementi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="72f10-178">CTRL+Click to select multiple items at a time.</span></span>

     <span data-ttu-id="72f10-179">Questo passaggio consente di aggiungere le versioni aggiornate delle definizioni del flusso di lavoro al progetto.</span><span class="sxs-lookup"><span data-stu-id="72f10-179">This step adds the updated versions of the workflow definitions to the project.</span></span>

9. <span data-ttu-id="72f10-180">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="72f10-180">Press CTRL+SHIFT+B to build the project.</span></span>

10. <span data-ttu-id="72f10-181">Scegli **Chiudi soluzione** dalle **File** menu.</span><span class="sxs-lookup"><span data-stu-id="72f10-181">Choose **Close Solution** from the **File** menu.</span></span> <span data-ttu-id="72f10-182">Un file di soluzione per il progetto non è necessario, quindi fare clic su **No** per chiudere Visual Studio senza salvare un file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="72f10-182">A solution file for the project is not required, so click **No** to close Visual Studio without saving a solution file.</span></span> <span data-ttu-id="72f10-183">Scegli **Exit** dal **File** menu per chiudere Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72f10-183">Choose **Exit** from the **File** menu to close Visual Studio.</span></span>

11. <span data-ttu-id="72f10-184">Aprire Windows Explorer e passare al **NumberGuessWorkflowActivities_du\bin\Debug** cartella (o **bin\Release** a seconda delle impostazioni di progetto).</span><span class="sxs-lookup"><span data-stu-id="72f10-184">Open Windows Explorer and navigate to the **NumberGuessWorkflowActivities_du\bin\Debug** folder (or **bin\Release** depending on your project settings).</span></span>

12. <span data-ttu-id="72f10-185">Rinominare **numberguessworkflowactivities. dll** al **NumberGuessWorkflowActivities_v15.dll**e copiarlo per la **PreviousVersions** cartella creata nel [Procedura: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="72f10-185">Rename **NumberGuessWorkflowActivities.dll** to **NumberGuessWorkflowActivities_v15.dll**, and copy it to the **PreviousVersions** folder you created in [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>

### <a name="BKMK_UpdateWorkflowVersionMap"></a> <span data-ttu-id="72f10-186">Per aggiornare WorkflowVersionMap con le nuove versioni</span><span class="sxs-lookup"><span data-stu-id="72f10-186">To update WorkflowVersionMap with the new versions</span></span>

1.  <span data-ttu-id="72f10-187">Passare all'istanza iniziale di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="72f10-187">Switch back to the initial instance of Visual Studio 2012.</span></span>

2.  <span data-ttu-id="72f10-188">Fare doppio clic su **WorkflowVersionMap.cs** (o **workflowversionmap. vb**) sotto il **NumberGuessWorkflowHost** per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="72f10-188">Double-click **WorkflowVersionMap.cs** (or **WorkflowVersionMap.vb**) under the **NumberGuessWorkflowHost** project to open it.</span></span>

3.  <span data-ttu-id="72f10-189">Aggiungere tre nuove identità del flusso di lavoro subito dopo le sei dichiarazioni di identità del flusso di lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="72f10-189">Add three new workflow identities just below the six existing workflow identity declarations.</span></span> <span data-ttu-id="72f10-190">In questa esercitazione `1.5.0.0` viene usato come `WorkflowIdentity.Version` per le identità dinamiche di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="72f10-190">In this tutorial, `1.5.0.0` is used as the `WorkflowIdentity.Version` for the dynamic update identities.</span></span> <span data-ttu-id="72f10-191">Queste nuove identità del flusso di lavoro `v15` verranno usate per fornire la definizione corretta del flusso di lavoro per le istanze persistenti del flusso di lavoro aggiornate in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="72f10-191">These new `v15` workflow identities will be used provide the correct workflow definition for the dynamically updated persisted workflow instances.</span></span>

    ```vb
    'Current version identities.
    Public StateMachineNumberGuessIdentity As WorkflowIdentity
    Public FlowchartNumberGuessIdentity As WorkflowIdentity
    Public SequentialNumberGuessIdentity As WorkflowIdentity

    'v1 identities.
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

    'v1.5 (Dynamimc Update) identities.
    Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
    Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
    Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity
    ```

    ```csharp
    // Current version identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity;
    static public WorkflowIdentity FlowchartNumberGuessIdentity;
    static public WorkflowIdentity SequentialNumberGuessIdentity;

    // v1 identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

    // v1.5 (Dynamic Update) identities.
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
    static public WorkflowIdentity SequentialNumberGuessIdentity_v15;
    ```

4.  <span data-ttu-id="72f10-192">Aggiungere il codice riportato di seguito alla fine del costruttore.</span><span class="sxs-lookup"><span data-stu-id="72f10-192">Add the following code at the end of the constructor.</span></span> <span data-ttu-id="72f10-193">Tramite questo codice vengono inizializzate le identità dinamiche del flusso di lavoro di aggiornamento, vengono caricate le definizioni del flusso di lavoro corrispondenti e vengono aggiunte queste ultime al dizionario della versione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-193">This code initializes the dynamic update workflow identities, loads the corresponding workflow definitions, and adds them to the workflow version dictionary.</span></span>

    ```vb
    'Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "StateMachineNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "FlowchartNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
    {
        .Name = "SequentialNumberGuessWorkflow",
        .Version = New Version(1, 5, 0, 0)
    }

    'Add the dynamic update workflow identities to the dictionary along with
    'the corresponding workflow definitions loaded from the v15 assembly.
    'Assembly.LoadFile requires an absolute path so convert this relative path
    'to an absolute path.
    Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
    Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
    ```

    ```csharp
    // Initialize the dynamic update workflow identities.
    StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "StateMachineNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "FlowchartNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
    {
        Name = "SequentialNumberGuessWorkflow",
        Version = new Version(1, 5, 0, 0)
    };

    // Add the dynamic update workflow identities to the dictionary along with
    // the corresponding workflow definitions loaded from the v15 assembly.
    // Assembly.LoadFile requires an absolute path so convert this relative path
    // to an absolute path.
    string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
    v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
    Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

    map.Add(StateMachineNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

    map.Add(SequentialNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

    map.Add(FlowchartNumberGuessIdentity_v15,
        v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
    ```

     <span data-ttu-id="72f10-194">Nell'esempio seguente viene mostrata la classe `WorkflowVersionMap` completata.</span><span class="sxs-lookup"><span data-stu-id="72f10-194">The following example is the completed `WorkflowVersionMap` class.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        'Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        'v1 identities.
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity

        'v1.5 (Dynamimc Update) identities.
        Public StateMachineNumberGuessIdentity_v15 As WorkflowIdentity
        Public FlowchartNumberGuessIdentity_v15 As WorkflowIdentity
        Public SequentialNumberGuessIdentity_v15 As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            'Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(2, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())

            'Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            'Add the previous version workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v1 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))

            'Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            FlowchartNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            SequentialNumberGuessIdentity_v15 = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 5, 0, 0)
            }

            'Add the dynamic update workflow identities to the dictionary along with
            'the corresponding workflow definitions loaded from the v15 assembly.
            'Assembly.LoadFile requires an absolute path so convert this relative path
            'to an absolute path.
            Dim v15AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll"
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath)
            Dim v15Assembly As Assembly = Assembly.LoadFile(v15AssemblyPath)

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        // v1 identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;

        // v1.5 (Dynamic Update) identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v15;
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v15;
        static public WorkflowIdentity SequentialNumberGuessIdentity_v15;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                // Version = new Version(1, 0, 0, 0),
                Version = new Version(2, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());

            // Initialize the previous workflow version identities.
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            // Add the previous version workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v1 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v1,
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);

            // Initialize the dynamic update workflow identities.
            StateMachineNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            FlowchartNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            SequentialNumberGuessIdentity_v15 = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 5, 0, 0)
            };

            // Add the dynamic update workflow identities to the dictionary along with
            // the corresponding workflow definitions loaded from the v15 assembly.
            // Assembly.LoadFile requires an absolute path so convert this relative path
            // to an absolute path.
            string v15AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v15.dll";
            v15AssemblyPath = Path.GetFullPath(v15AssemblyPath);
            Assembly v15Assembly = Assembly.LoadFile(v15AssemblyPath);

            map.Add(StateMachineNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);

            map.Add(SequentialNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);

            map.Add(FlowchartNumberGuessIdentity_v15,
                v15Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
        }
    }
    ```

5.  <span data-ttu-id="72f10-195">Premere CTRL+MAIUSC+B per compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="72f10-195">Press CTRL+SHIFT+B to build the project.</span></span>

### <a name="BKMK_ApplyUpdate"></a> <span data-ttu-id="72f10-196">Per applicare gli aggiornamenti dinamici</span><span class="sxs-lookup"><span data-stu-id="72f10-196">To apply the dynamic updates</span></span>

1.  <span data-ttu-id="72f10-197">Fare doppio clic su **WF45GettingStartedTutorial** nelle **Esplora soluzioni** e scegliere **Add**, **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="72f10-197">Right-click **WF45GettingStartedTutorial** in **Solution Explorer** and choose **Add**, **New Project**.</span></span>

2.  <span data-ttu-id="72f10-198">Nel **Installed** nodo, seleziona **Visual c#**, **Windows** (oppure **Visual Basic**, **Windows**).</span><span class="sxs-lookup"><span data-stu-id="72f10-198">In the **Installed** node, select **Visual C#**, **Windows** (or **Visual Basic**, **Windows**).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="72f10-199">A seconda del linguaggio di programmazione configurato come linguaggio principale in Visual Studio, sotto il nodo **Altri linguaggi** del nodo **Installato** viene visualizzato il nodo **Visual C#** o **Visual Basic** .</span><span class="sxs-lookup"><span data-stu-id="72f10-199">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="72f10-200">Assicurarsi che nell'elenco a discesa della versione di .NET Framework sia selezionata l'opzione **.NET Framework 4.5** .</span><span class="sxs-lookup"><span data-stu-id="72f10-200">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="72f10-201">Selezionare **applicazione Console** dalle **Windows** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-201">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="72f10-202">Tipo di **ApplyDynamicUpdate** nel **Name** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="72f10-202">Type **ApplyDynamicUpdate** into the **Name** box and click **OK**.</span></span>

3.  <span data-ttu-id="72f10-203">Fare doppio clic su **ApplyDynamicUpdate** nelle **Esplora soluzioni** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="72f10-203">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Add Reference**.</span></span>

4.  <span data-ttu-id="72f10-204">Fare clic su **soluzione** e selezionare la casella accanto a **NumberGuessWorkflowHost**.</span><span class="sxs-lookup"><span data-stu-id="72f10-204">Click **Solution** and check the box next to **NumberGuessWorkflowHost**.</span></span> <span data-ttu-id="72f10-205">Questo riferimento è necessario affinché la classe `ApplyDynamicUpdate` possa essere usata dall'oggetto `NumberGuessWorkflowHost.WorkflowVersionMap`.</span><span class="sxs-lookup"><span data-stu-id="72f10-205">This reference is needed so that `ApplyDynamicUpdate` can use the `NumberGuessWorkflowHost.WorkflowVersionMap` class.</span></span>

5.  <span data-ttu-id="72f10-206">Selezionare **Framework** dal **assembly** nodo il **Aggiungi riferimento** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-206">Select **Framework** from the **Assemblies** node in the **Add Reference** list.</span></span> <span data-ttu-id="72f10-207">Tipo di **System. Activities** nel **cerca assembly** casella.</span><span class="sxs-lookup"><span data-stu-id="72f10-207">Type **System.Activities** into the **Search Assemblies** box.</span></span> <span data-ttu-id="72f10-208">Gli assembly verranno filtrati e sarà più semplice selezionare i riferimenti desiderati.</span><span class="sxs-lookup"><span data-stu-id="72f10-208">This will filter the assemblies and make the desired references easier to select.</span></span>

6.  <span data-ttu-id="72f10-209">Selezionare la casella di controllo accanto **System. Activities** dalle **i risultati della ricerca** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-209">Check the checkbox beside **System.Activities** from the **Search Results** list.</span></span>

7.  <span data-ttu-id="72f10-210">Tipo di **serializzazione** nel **cerca assembly** casella e selezionare la casella di controllo accanto a **Serialization** dal **i risultati della ricerca**  elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-210">Type **Serialization** into the **Search Assemblies** box, and check the checkbox beside **System.Runtime.Serialization** from the **Search Results** list.</span></span>

8.  <span data-ttu-id="72f10-211">Tipo di **DurableInstancing** nel **cerca assembly** casella e selezionare la casella di controllo accanto a **System.Activities.DurableInstancing** e  **System.Runtime.DurableInstancing** dal **i risultati della ricerca** elenco.</span><span class="sxs-lookup"><span data-stu-id="72f10-211">Type **DurableInstancing** into the **Search Assemblies** box, and check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list.</span></span>

9. <span data-ttu-id="72f10-212">Fare clic su **OK** per chiudere **gestione riferimenti** e aggiungere i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="72f10-212">Click **OK** to close **Reference Manager** and add the references.</span></span>

10. <span data-ttu-id="72f10-213">Fare doppio clic su **ApplyDynamicUpdate** in Esplora soluzioni e scegliere **Add**, **classe**.</span><span class="sxs-lookup"><span data-stu-id="72f10-213">Right-click **ApplyDynamicUpdate** in Solution Explorer and choose **Add**, **Class**.</span></span> <span data-ttu-id="72f10-214">Tipo di `DynamicUpdateInfo` nella **Name** casella e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="72f10-214">Type `DynamicUpdateInfo` into the **Name** box and click **Add**.</span></span>

11. <span data-ttu-id="72f10-215">Aggiungere i due membri riportati di seguito alla classe `DynamicUpdateInfo`.</span><span class="sxs-lookup"><span data-stu-id="72f10-215">Add the following two members to the `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="72f10-216">Nell'esempio seguente viene mostrata la classe `DynamicUpdateInfo` completata.</span><span class="sxs-lookup"><span data-stu-id="72f10-216">The following example is the completed `DynamicUpdateInfo` class.</span></span> <span data-ttu-id="72f10-217">In questa classe sono contenute le informazioni sul mapping di aggiornamento e la nuova identità del flusso di lavoro usata quando un'istanza del flusso di lavoro viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="72f10-217">This class contains information on the update map and new workflow identity used when a workflow instance is updated.</span></span>

    ```vb
    Public Class DynamicUpdateInfo
        Public updateMap As DynamicUpdateMap
        Public newIdentity As WorkflowIdentity
    End Class
    ```

    ```csharp
    class DynamicUpdateInfo
    {
        public DynamicUpdateMap updateMap;
        public WorkflowIdentity newIdentity;
    }
    ```

12. <span data-ttu-id="72f10-218">Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="72f10-218">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DynamicUpdate
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DynamicUpdate;
    ```

13. <span data-ttu-id="72f10-219">Fare doppio clic su **Program.cs** (o **Module1.vb**) in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="72f10-219">Double-click **Program.cs** (or **Module1.vb**) in Solution Explorer.</span></span>

14. <span data-ttu-id="72f10-220">Aggiungere le seguenti istruzioni `using` (o `Imports`) nella parte superiore del file con le altre istruzioni `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="72f10-220">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowHost
    Imports System.Data.SqlClient
    Imports System.Activities.DynamicUpdate
    Imports System.IO
    Imports System.Runtime.Serialization
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    ```

    ```csharp
    using NumberGuessWorkflowHost;
    using System.Data;
    using System.Data.SqlClient;
    using System.Activities;
    using System.Activities.DynamicUpdate;
    using System.IO;
    using System.Runtime.Serialization;
    using System.Activities.DurableInstancing;
    ```

15. <span data-ttu-id="72f10-221">Aggiungere il membro della stringa di connessione seguente alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-221">Add the following connection string member to the `Program` class (or `Module1`).</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    ```

    > [!NOTE]
    >  <span data-ttu-id="72f10-222">Il nome del server della stringa di connessione potrebbe essere diverso a seconda dell'edizione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="72f10-222">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

16. <span data-ttu-id="72f10-223">Aggiungere il seguente metodo `GetIDs` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-223">Add the following `GetIDs` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-224">Questo metodo restituisce un elenco di ID persistenti dell'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-224">This method returns a list of persisted workflow instance ids.</span></span>

    ```vb
    Function GetIds() As IList(Of Guid)
        Dim Ids As New List(Of Guid)
        Dim localCmd = _
            String.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]")
        Using localCon = New SqlConnection(connectionString)
            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)
                While reader.Read()
                    'Get the InstanceId of the persisted Workflow
                    Dim id As Guid = Guid.Parse(reader(0).ToString())

                    'Add it to the list.
                    Ids.Add(id)
                End While
            End Using
        End Using

        Return Ids
    End Function
    ```

    ```csharp
    static IList<Guid> GetIds()
    {
        List<Guid> Ids = new List<Guid>();
        string localCmd = string.Format("Select [InstanceId] from [System.Activities.DurableInstancing].[Instances] Order By [CreationTime]");
        using (SqlConnection localCon = new SqlConnection(connectionString))
        {
            SqlCommand cmd = localCon.CreateCommand();
            cmd.CommandText = localCmd;
            localCon.Open();
            using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
            {
                while (reader.Read())
                {
                    // Get the InstanceId of the persisted Workflow
                    Guid id = Guid.Parse(reader[0].ToString());

                    // Add it to the list.
                    Ids.Add(id);
                }
            }
        }

        return Ids;
    }
    ```

17. <span data-ttu-id="72f10-225">Aggiungere il seguente metodo `LoadMap` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-225">Add the following `LoadMap` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-226">Questo metodo consente di creare un dizionario tramite cui viene eseguito il mapping delle identità del flusso di lavoro `v1` ai mapping di aggiornamento e alle nuove identità del flusso di lavoro usate per aggiornare le istanze corrispondenti del flusso di lavoro persistente.</span><span class="sxs-lookup"><span data-stu-id="72f10-226">This method creates a dictionary that maps `v1` workflow identities to the update maps and new workflow identities used to update the corresponding persisted workflow instances.</span></span>

    ```vb
    Function LoadMap(mapName As String) As DynamicUpdateMap
        Dim mapPath As String = Path.Combine("..\..\..\PreviousVersions", mapName)

        Dim map As DynamicUpdateMap
        Using fs As FileStream = File.Open(mapPath, FileMode.Open)
            Dim serializer As DataContractSerializer = New DataContractSerializer(GetType(DynamicUpdateMap))
            Dim updateMap = serializer.ReadObject(fs)
            If updateMap Is Nothing Then
                Throw New ApplicationException("DynamicUpdateMap is null.")
            End If

            map = updateMap
        End Using

        Return map
    End Function
    ```

    ```csharp
    static DynamicUpdateMap LoadMap(string mapName)
    {
        string path = Path.Combine(@"..\..\..\PreviousVersions", mapName);

        DynamicUpdateMap map;
        using (FileStream fs = File.Open(path, FileMode.Open))
        {
            DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
            object updateMap = serializer.ReadObject(fs);
            if (updateMap == null)
            {
                throw new ApplicationException("DynamicUpdateMap is null.");
            }

            map = updateMap as DynamicUpdateMap;
        }

        return map;
    }
    ```

18. <span data-ttu-id="72f10-227">Aggiungere il seguente metodo `LoadMaps` alla classe `Program` (o `Module1`).</span><span class="sxs-lookup"><span data-stu-id="72f10-227">Add the following `LoadMaps` method to the `Program` class (or `Module1`).</span></span> <span data-ttu-id="72f10-228">Tramite questo metodo vengono caricati i tre mapping di aggiornamento e viene creato un dizionario mediante il quale viene eseguito il mapping delle identità del flusso di lavoro `v1` ai mapping di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="72f10-228">This method loads the three update maps and creates a dictionary that maps `v1` workflow identities to the update maps.</span></span>

    ```vb
    Function LoadMaps() As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo)
        'There are 3 update maps to describe the changes to update v1 workflows,
        'one for reach of the 3 workflow types in the tutorial.
        Dim maps = New Dictionary(Of WorkflowIdentity, DynamicUpdateInfo)()

        Dim sequentialMap As DynamicUpdateMap = LoadMap("SequentialNumberGuessWorkflow.map")
        Dim sequentialInfo = New DynamicUpdateInfo With
        {
            .updateMap = sequentialMap,
            .newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo)

        Dim stateMap As DynamicUpdateMap = LoadMap("StateMachineNumberGuessWorkflow.map")
        Dim stateInfo = New DynamicUpdateInfo With
        {
            .updateMap = stateMap,
            .newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo)

        Dim flowchartMap As DynamicUpdateMap = LoadMap("FlowchartNumberGuessWorkflow.map")
        Dim flowchartInfo = New DynamicUpdateInfo With
        {
            .updateMap = flowchartMap,
            .newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        }
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo)

        Return maps
    End Function
    ```

    ```csharp
    static IDictionary<WorkflowIdentity, DynamicUpdateInfo> LoadMaps()
    {
        // There are 3 update maps to describe the changes to update v1 workflows,
        // one for reach of the 3 workflow types in the tutorial.
        Dictionary<WorkflowIdentity, DynamicUpdateInfo> maps =
            new Dictionary<WorkflowIdentity, DynamicUpdateInfo>();

        DynamicUpdateMap sequentialMap = LoadMap("SequentialNumberGuessWorkflow.map");
        DynamicUpdateInfo sequentialInfo = new DynamicUpdateInfo
        {
            updateMap = sequentialMap,
            newIdentity = WorkflowVersionMap.SequentialNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.SequentialNumberGuessIdentity_v1, sequentialInfo);

        DynamicUpdateMap stateMap = LoadMap("StateMachineNumberGuessWorkflow.map");
        DynamicUpdateInfo stateInfo = new DynamicUpdateInfo
        {
            updateMap = stateMap,
            newIdentity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.StateMachineNumberGuessIdentity_v1, stateInfo);

        DynamicUpdateMap flowchartMap = LoadMap("FlowchartNumberGuessWorkflow.map");
        DynamicUpdateInfo flowchartInfo = new DynamicUpdateInfo
        {
            updateMap = flowchartMap,
            newIdentity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v15
        };
        maps.Add(WorkflowVersionMap.FlowchartNumberGuessIdentity_v1, flowchartInfo);

        return maps;
    }
    ```

19. <span data-ttu-id="72f10-229">Aggiungere il seguente codice a `Main`.</span><span class="sxs-lookup"><span data-stu-id="72f10-229">Add the following code to `Main`.</span></span> <span data-ttu-id="72f10-230">Con questo codice è possibile scorrere le istanze del flusso di lavoro persistente ed esaminare ogni oggetto `WorkflowIdentity`.</span><span class="sxs-lookup"><span data-stu-id="72f10-230">This code iterates the persisted workflow instances and examines each `WorkflowIdentity`.</span></span> <span data-ttu-id="72f10-231">Se tramite `WorkflowIdentity` viene eseguito il mapping a un'istanza del flusso di lavoro `v1`, un oggetto `WorkflowApplication` è configurato con la definizione aggiornata del flusso di lavoro e un'identità aggiornata del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-231">If the `WorkflowIdentity` maps to a `v1` workflow instance, a `WorkflowApplication` is configured with the updated workflow definition and an updated workflow identity.</span></span> <span data-ttu-id="72f10-232">Successivamente, l'oggetto `WorkflowApplication.Load` viene chiamato con l'istanza e il mapping di aggiornamento, con cui è possibile applicare il mapping di aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="72f10-232">Next, `WorkflowApplication.Load` is called with the instance and the update map, which applies the dynamic update map.</span></span> <span data-ttu-id="72f10-233">Una volta applicato l'aggiornamento, l'istanza aggiornata è persistente con una chiamata a `Unload`.</span><span class="sxs-lookup"><span data-stu-id="72f10-233">Once the update is applied, the updated instance is persisted with a call to `Unload`.</span></span>

    ```vb
    Dim store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    Dim updateMaps As IDictionary(Of WorkflowIdentity, DynamicUpdateInfo) = LoadMaps()

    For Each id As Guid In GetIds()
        'Get a proxy to the instance.
        Dim instance As WorkflowApplicationInstance = WorkflowApplication.GetInstance(id, store)

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity)

        'Only update v1 workflows.
        If Not instance.DefinitionIdentity Is Nothing AndAlso _
            instance.DefinitionIdentity.Version.Equals(New Version(1, 0, 0, 0)) Then

            Dim info As DynamicUpdateInfo = updateMaps(instance.DefinitionIdentity)

            'Associate the persisted WorkflowApplicationInstance with
            'a WorkflowApplication that is configured with the updated
            'definition and updated WorkflowIdentity.
            Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity)
            Dim wfApp = New WorkflowApplication(wf, info.newIdentity)

            'Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap)

            'Persist the updated instance.
            wfApp.Unload()

            Console.WriteLine("Updated to: {0}", info.newIdentity)
        Else
            'Not updating this instance, so unload it.
            instance.Abandon()
        End If
    Next
    ```

    ```csharp
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    IDictionary<WorkflowIdentity, DynamicUpdateInfo> updateMaps = LoadMaps();

    foreach (Guid id in GetIds())
    {
        // Get a proxy to the instance.
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(id, store);

        Console.WriteLine("Inspecting: {0}", instance.DefinitionIdentity);

        // Only update v1 workflows.
        if (instance.DefinitionIdentity != null &&
            instance.DefinitionIdentity.Version.Equals(new Version(1, 0, 0, 0)))
        {
            DynamicUpdateInfo info = updateMaps[instance.DefinitionIdentity];

            // Associate the persisted WorkflowApplicationInstance with
            // a WorkflowApplication that is configured with the updated
            // definition and updated WorkflowIdentity.
            Activity wf = WorkflowVersionMap.GetWorkflowDefinition(info.newIdentity);
            WorkflowApplication wfApp =
                new WorkflowApplication(wf, info.newIdentity);

            // Apply the Dynamic Update.
            wfApp.Load(instance, info.updateMap);

            // Persist the updated instance.
            wfApp.Unload();

            Console.WriteLine("Updated to: {0}", info.newIdentity);
        }
        else
        {
            // Not updating this instance, so unload it.
            instance.Abandon();
        }
    }
    ```

20. <span data-ttu-id="72f10-234">Fare doppio clic su **ApplyDynamicUpdate** nelle **Esplora soluzioni** e scegliere **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="72f10-234">Right-click **ApplyDynamicUpdate** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

21. <span data-ttu-id="72f10-235">Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere CTRL+F5 per eseguire l'applicazione `ApplyDynamicUpdate` e aggiornare le istanze del flusso di lavoro persistente.</span><span class="sxs-lookup"><span data-stu-id="72f10-235">Press CTRL+SHIFT+B to build the solution, and then press CTRL+F5 to run the `ApplyDynamicUpdate` application and update the persisted workflow instances.</span></span> <span data-ttu-id="72f10-236">Si dovrebbe visualizzare un output simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="72f10-236">You should see output similar to the following.</span></span> <span data-ttu-id="72f10-237">I flussi di lavoro della versione 1.0.0.0 vengono aggiornati alla versione 1.5.0.0, mentre i flussi di lavoro della versione 2.0.0.0 non vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="72f10-237">The version 1.0.0.0 workflows are updated to version 1.5.0.0, while the version 2.0.0.0 workflows are not updated.</span></span>

 <span data-ttu-id="72f10-238">**Esaminare: StateMachineNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: StateMachineNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: StateMachineNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: StateMachineNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: FlowchartNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: FlowchartNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: FlowchartNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: FlowchartNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: SequentialNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: SequentialNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: SequentialNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: SequentialNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: SequentialNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: SequentialNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: StateMachineNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: StateMachineNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: FlowchartNumberGuessWorkflow; Versione Version=1.0.0.0**
**aggiornato da: FlowchartNumberGuessWorkflow; Versione = 1.5.0.0**
**controllo: StateMachineNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: StateMachineNumberGuessWorkflow; Versione = 2.0.0.0**
**controllo: FlowchartNumberGuessWorkflow; Versione = 2.0.0.0**
**controllo: FlowchartNumberGuessWorkflow; Versione = 2.0.0.0**
**controllo: SequentialNumberGuessWorkflow; Versione = 2.0.0.0**
**controllo: SequentialNumberGuessWorkflow; Versione = 2.0.0.0**
**premere un tasto qualsiasi per continuare...**</span><span class="sxs-lookup"><span data-stu-id="72f10-238">**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: SequentialNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: SequentialNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: StateMachineNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: StateMachineNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: FlowchartNumberGuessWorkflow; Version=1.0.0.0**
**Updated to: FlowchartNumberGuessWorkflow; Version=1.5.0.0**
**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: StateMachineNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: FlowchartNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**
**Inspecting: SequentialNumberGuessWorkflow; Version=2.0.0.0**
**Press any key to continue . . .**</span></span>

### <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="72f10-239">Per eseguire l'applicazione con i flussi di lavoro aggiornate</span><span class="sxs-lookup"><span data-stu-id="72f10-239">To run the application with the updated workflows</span></span>

1.  <span data-ttu-id="72f10-240">Fare doppio clic su **NumberGuessWorkflowHost** nelle **Esplora soluzioni** e scegliere **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="72f10-240">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Set as StartUp Project**.</span></span>

2.  <span data-ttu-id="72f10-241">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72f10-241">Press CTRL+F5 to run the application.</span></span>

3.  <span data-ttu-id="72f10-242">Fare clic su **nuova partita** per avviare un nuovo flusso di lavoro e tenere presente le informazioni sulla versione sotto la finestra di stato che indica il flusso di lavoro è un `v2` flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-242">Click **New Game** to start a new workflow and note the version information below the status window that indicates the workflow is a `v2` workflow.</span></span>

4.  <span data-ttu-id="72f10-243">Selezionare una delle `v1` flussi di lavoro avviati all'inizio del [come: Ospitare più versioni di un flusso di lavoro Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="72f10-243">Select one of the `v1` workflows you started at the beginning of the [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) topic.</span></span> <span data-ttu-id="72f10-244">Si noti che le informazioni sulla versione nella finestra di stato indica che il flusso di lavoro è una versione **1.5.0.0** flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-244">Note that the version information under the status window indicates that the workflow is a version **1.5.0.0** workflow.</span></span> <span data-ttu-id="72f10-245">Si noti inoltre che non sono disponibili informazioni sui tentativi precedenti, eccetto se troppo alti o troppo bassi.</span><span class="sxs-lookup"><span data-stu-id="72f10-245">Note that there is no information indicated about previous guesses other than whether they were too high or too low.</span></span>

 <span data-ttu-id="72f10-246">**Immettere un numero compreso tra 1 e 10**
**la stima è troppo basso.**</span><span class="sxs-lookup"><span data-stu-id="72f10-246">**Please enter a number between 1 and 10**
**Your guess is too low.**</span></span>

5.  <span data-ttu-id="72f10-247">Prendere nota dell'oggetto `InstanceId`, quindi immettere dei tentativi finché il flusso di lavoro non viene completato.</span><span class="sxs-lookup"><span data-stu-id="72f10-247">Make a note of the `InstanceId` and then enter guesses until the workflow completes.</span></span> <span data-ttu-id="72f10-248">Nella finestra di stato vengono visualizzate le informazioni sul contenuto del tentativo, dal momento che le attività `WriteLine` sono state aggiornate dall'aggiornamento dinamico.</span><span class="sxs-lookup"><span data-stu-id="72f10-248">The status window displays information about the content of the guess because the `WriteLine` activities were updated by the dynamic update.</span></span>

 <span data-ttu-id="72f10-249">**Immettere un numero compreso tra 1 e 10**
**il valore indicato è troppo basso.** 
 **Immettere un numero compreso tra 1 e 10**
**5 è un valore troppo basso.** 
 **Immettere un numero compreso tra 1 e 10**
**7 è troppo elevato.** 
 **Immettere un numero compreso tra 1 e 10**
**Congratulazioni, è stata ipotizzata il numero a sua 4 volta.**</span><span class="sxs-lookup"><span data-stu-id="72f10-249">**Please enter a number between 1 and 10**
**Your guess is too low.**
**Please enter a number between 1 and 10**
**5 is too low.**
**Please enter a number between 1 and 10**
**7 is too high.**
**Please enter a number between 1 and 10**
**Congratulations, you guessed the number in 4 turns.**</span></span>

6.  <span data-ttu-id="72f10-250">Aprire Windows Explorer e passare al **NumberGuessWorkflowHost\bin\debug** cartella (o **bin\release** a seconda delle impostazioni di progetto) e aprire il file di rilevamento mediante blocco note corrispondente per il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="72f10-250">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings) and open the tracking file using Notepad that corresponds to the completed workflow.</span></span> <span data-ttu-id="72f10-251">Se non si è presa nota del `InstanceId` sarà in grado di identificare i file di rilevamento corretto usando la **data modificata** in Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="72f10-251">If you did not make a note of the `InstanceId` you may be able to identify the correct tracking file by using the **Date modified** information in Windows Explorer.</span></span> <span data-ttu-id="72f10-252">Nell'ultima riga delle informazioni di rilevamento è contenuto l'output dell'attività `WriteLine` appena aggiunta.</span><span class="sxs-lookup"><span data-stu-id="72f10-252">The last line of the tracking information contains the output of the newly added `WriteLine` activity.</span></span>

 <span data-ttu-id="72f10-253">**Immettere un numero compreso tra 1 e 10**
**il valore indicato è troppo basso.** 
 **Immettere un numero compreso tra 1 e 10**
**5 è un valore troppo basso.** 
 **Immettere un numero compreso tra 1 e 10**
**7 è troppo elevato.** 
 **Immettere un numero compreso tra 1 e 10**
**6 sia corretto. Avete indovinato a sua 4 volta.**</span><span class="sxs-lookup"><span data-stu-id="72f10-253">**Please enter a number between 1 and 10**
**Your guess is too low.**
**Please enter a number between 1 and 10**
**5 is too low.**
**Please enter a number between 1 and 10**
**7 is too high.**
**Please enter a number between 1 and 10**
**6 is correct. You guessed it in 4 turns.**</span></span>

### <a name="BKMK_StartPreviousVersions"></a> <span data-ttu-id="72f10-254">Per abilitare l'avvio delle versioni precedenti dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="72f10-254">To enable starting previous versions of the workflows</span></span>
 <span data-ttu-id="72f10-255">Se si esauriscono i flussi di lavoro da aggiornare, è possibile modificare l'applicazione `NumberGuessWorkflowHost` per abilitare l'avvio delle versioni precedenti dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="72f10-255">If you run out of workflows to update, you can modify the `NumberGuessWorkflowHost` application to enable starting previous versions of the workflows.</span></span>

1.  <span data-ttu-id="72f10-256">Fare doppio clic su **WorkflowHostForm** nelle **Esplora soluzioni**e selezionare il **WorkflowType** casella combinata.</span><span class="sxs-lookup"><span data-stu-id="72f10-256">Double-click **WorkflowHostForm** in **Solution Explorer**, and select the **WorkflowType** combo box.</span></span>

2.  <span data-ttu-id="72f10-257">Nel **delle proprietà** finestra, seleziona il **elementi** proprietà e fare clic sul pulsante dei puntini di sospensione per modificare il **elementi** raccolta.</span><span class="sxs-lookup"><span data-stu-id="72f10-257">In the **Properties** window, select the **Items** property and click the ellipsis button to edit the **Items** collection.</span></span>

3.  <span data-ttu-id="72f10-258">Aggiungere alla raccolta i seguenti tre elementi.</span><span class="sxs-lookup"><span data-stu-id="72f10-258">Add the following three items to the collection.</span></span>

    ```
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

     <span data-ttu-id="72f10-259">La raccolta `Items` completata avrà sei elementi.</span><span class="sxs-lookup"><span data-stu-id="72f10-259">The completed `Items` collection will have six items.</span></span>

    ```
    StateMachineNumberGuessWorkflow
    FlowchartNumberGuessWorkflow
    SequentialNumberGuessWorkflow
    StateMachineNumberGuessWorkflow v1
    FlowchartNumberGuessWorkflow v1
    SequentialNumberGuessWorkflow v1
    ```

4.  <span data-ttu-id="72f10-260">Fare doppio clic su **WorkflowHostForm** nelle **Esplora soluzioni**e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="72f10-260">Double-click **WorkflowHostForm** in **Solution Explorer**, and select **View Code**.</span></span>

5.  <span data-ttu-id="72f10-261">Aggiungere tre nuovi casi al `switch` (o `Select Case`) istruzione il `NewGame_Click` gestore per eseguire il mapping di nuovi elementi nel **WorkflowType** casella combinata per le identità del flusso di lavoro corrispondente.</span><span class="sxs-lookup"><span data-stu-id="72f10-261">Add three new cases to the `switch` (or `Select Case`) statement in the `NewGame_Click` handler to map the new items in the **WorkflowType** combo box to the matching workflow identities.</span></span>

    ```vb
    Case "SequentialNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

    Case "StateMachineNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

    Case "FlowchartNumberGuessWorkflow v1"
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    ```

    ```csharp
    case "SequentialNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
        break;

    case "StateMachineNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
        break;

    case "FlowchartNumberGuessWorkflow v1":
        identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
        break;
    ```

     <span data-ttu-id="72f10-262">L'esempio riportato di seguito contiene l'istruzione completa `switch` (o `Select Case`).</span><span class="sxs-lookup"><span data-stu-id="72f10-262">The following example contains the complete `switch` (or `Select Case`) statement.</span></span>

    ```vb
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity

        Case "SequentialNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1

        Case "StateMachineNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1

        Case "FlowchartNumberGuessWorkflow v1"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1
    End Select
    ```

    ```csharp
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;

        case "SequentialNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity_v1;
            break;

        case "StateMachineNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity_v1;
            break;

        case "FlowchartNumberGuessWorkflow v1":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity_v1;
            break;
    };
    ```

6.  <span data-ttu-id="72f10-263">Premere CTRL+F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72f10-263">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="72f10-264">È possibile avviare le versioni `v1` del flusso di lavoro nonché le versioni correnti.</span><span class="sxs-lookup"><span data-stu-id="72f10-264">You can now start the `v1` versions of the workflow as well as the current versions.</span></span> <span data-ttu-id="72f10-265">Per aggiornare dinamicamente questi nuove istanze, eseguire la **ApplyDynamicUpdate** dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72f10-265">To dynamically update these new instances, run the **ApplyDynamicUpdate** application.</span></span>
