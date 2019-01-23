---
title: 'Procedura: Creare un flusso di lavoro sequenziale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 33a4d6f7db140023bc33839fec7d5e28b7f5fe51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547306"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="99ba3-102">Procedura: Creare un flusso di lavoro sequenziale</span><span class="sxs-lookup"><span data-stu-id="99ba3-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="99ba3-103">I flussi di lavoro possono essere costruiti da attività incorporate e da attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="99ba3-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="99ba3-104">In questo argomento illustra la creazione di un flusso di lavoro che vengono usate sia attività incorporate, ad esempio la <xref:System.Activities.Statements.Sequence> attività e le attività personalizzate dal precedente [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="99ba3-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="99ba3-105">Il flusso di lavoro consente di modellare un gioco per determinare un numero.</span><span class="sxs-lookup"><span data-stu-id="99ba3-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99ba3-106">Ogni argomento nell'Esercitazione introduttiva dipende dagli argomenti precedenti.</span><span class="sxs-lookup"><span data-stu-id="99ba3-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="99ba3-107">Per completare questo argomento, è necessario completare prima [come: Creare un'attività](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="99ba3-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99ba3-108">Per scaricare una versione completa dell'esercitazione, vedere [Windows Workflow Foundation (WF45) - esercitazione introduttiva](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="99ba3-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="99ba3-109">Per creare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="99ba3-110">Fare doppio clic su **NumberGuessWorkflowActivities** nelle **Esplora soluzioni** e selezionare **Add**, **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="99ba3-111">Nel **Installed**, **elementi comuni** nodo, seleziona **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="99ba3-112">Selezionare **impegno** dalle **flusso di lavoro** elenco.</span><span class="sxs-lookup"><span data-stu-id="99ba3-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="99ba3-113">Tipo di `SequentialNumberGuessWorkflow` nella **Name** casella e fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="99ba3-114">Trascinare un **sequenza** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla il **Rilascia attività qui** etichetta nel area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="99ba3-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="99ba3-115">Per creare variabili e argomenti del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="99ba3-116">Fare doppio clic su **sequentialnumberguessworkflow. XAML** nelle **Esplora soluzioni** per visualizzare il flusso di lavoro nella finestra di progettazione, se non è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="99ba3-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="99ba3-117">Fare clic su **argomenti** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99ba3-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="99ba3-118">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="99ba3-119">Tipo `MaxNumber` nella **nome** , quindi selezionare **nel** dal **direzione** elenco a discesa, seleziona **Int32** dal **Tipo di argomento** elenco a discesa e quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="99ba3-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="99ba3-120">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="99ba3-121">Tipo `Turns` nella **Name** finestra che si trova sotto appena aggiunta `MaxNumber` argomento, selezionare **Out** dal **direzione** dall'elenco a discesa, seleziona  **Int32** dal **tipo di argomento** elenco a discesa e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="99ba3-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="99ba3-122">Fare clic su **argomenti** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99ba3-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="99ba3-123">Fare clic su **variabili** sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare i **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99ba3-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="99ba3-124">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="99ba3-125">Se nessun **Crea variabile** verrà visualizzata la finestra, fare clic sui **sequenza** attività nell'area di progettazione del flusso di lavoro per selezionarla.</span><span class="sxs-lookup"><span data-stu-id="99ba3-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="99ba3-126">Tipo di `Guess` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="99ba3-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="99ba3-127">Fare clic su **creare variabile**.</span><span class="sxs-lookup"><span data-stu-id="99ba3-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="99ba3-128">Tipo di `Target` nella **nome** , quindi selezionare **Int32** dal **tipo di variabile** elenco a discesa e quindi premere INVIO per salvare la variabile.</span><span class="sxs-lookup"><span data-stu-id="99ba3-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="99ba3-129">Fare clic su **variabili** sul lato sinistro inferiore dell'ActivityDesigner per chiudere la **variabili** riquadro.</span><span class="sxs-lookup"><span data-stu-id="99ba3-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="99ba3-130">Per aggiungere le attività del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="99ba3-131">Trascinare un' **assegnare** attività dalle **primitive** sezione del **della casella degli strumenti** e rilasciarla sul **sequenza** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="99ba3-132">Tipo `Target` nella **al** finestra e l'espressione seguente nella **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="99ba3-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="99ba3-133">Se il **casella degli strumenti** finestra non viene visualizzata, selezionare **della casella degli strumenti** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="99ba3-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="99ba3-134">Trascinare un **DoWhile** attività dalle **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla sul flusso di lavoro in modo che si trovi sotto il **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3.  <span data-ttu-id="99ba3-135">Digitare l'espressione seguente nella **DoWhile** dell'attività **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="99ba3-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="99ba3-136">Un'attività <xref:System.Activities.Statements.DoWhile> esegue le proprie attività figlio e successivamente valuta <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="99ba3-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="99ba3-137">Se <xref:System.Activities.Statements.DoWhile.Condition%2A> dà come risultato `True`, le attività in <xref:System.Activities.Statements.DoWhile> vengono eseguite nuovamente.</span><span class="sxs-lookup"><span data-stu-id="99ba3-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="99ba3-138">In questo esempio, viene valutata l'ipotesi dell'utente e <xref:System.Activities.Statements.DoWhile> continua finché l'ipotesi non è corretta.</span><span class="sxs-lookup"><span data-stu-id="99ba3-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4.  <span data-ttu-id="99ba3-139">Trascinare un **dei messaggi di richiesta** attività dal **NumberGuessWorkflowActivities** sezione del **della casella degli strumenti** e rilasciarla nel **DoWhile** attività nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="99ba3-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5.  <span data-ttu-id="99ba3-140">Nel **finestra delle proprietà**, tipo `"EnterGuess"` incluse le virgolette nella **BookmarkName** casella dei valori per i **dei messaggi di richiesta** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="99ba3-141">Tipo di `Guess` nella **risultato** casella del valore proprietà e digitare l'espressione seguente nella **testo** finestra delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="99ba3-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="99ba3-142">Se il **finestra delle proprietà** non è visualizzato, selezionare **finestra delle proprietà** dal **visualizzazione** menu.</span><span class="sxs-lookup"><span data-stu-id="99ba3-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6.  <span data-ttu-id="99ba3-143">Trascinare un **assegnare** attività dal **primitive** sezione del **della casella degli strumenti** e rilasciarla nel **DoWhile** attività in modo che segua il **Dei messaggi di richiesta** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99ba3-144">Quando si rilascia il **assegnare** attività, nota come la finestra di progettazione del flusso di lavoro aggiunge automaticamente un **sequenza** attività per contenere sia il **Prompt** appena aggiunto e attività **Assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7.  <span data-ttu-id="99ba3-145">Tipo `Turns` nella **al** casella e `Turns + 1` nel **immettere un'espressione c#** o **immettere un'espressione VB** casella.</span><span class="sxs-lookup"><span data-stu-id="99ba3-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8.  <span data-ttu-id="99ba3-146">Trascinare un **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **sequenza** attività in modo che segua il aggiunti di recente **assegnare** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="99ba3-147">Digitare l'espressione seguente nella **se** dell'attività **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="99ba3-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="99ba3-148">Trascinare un altro **se** attività dal **flusso di controllo** sezione del **della casella degli strumenti** e rilasciarla nel **quindi** sezione del primo **Se** attività.</span><span class="sxs-lookup"><span data-stu-id="99ba3-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="99ba3-149">Digitare l'espressione seguente nella nuova **se** dell'attività **condizione** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="99ba3-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="99ba3-150">Trascinare due **WriteLine** le attività eseguite dal **primitive** sezione del **della casella degli strumenti** e rilasciarle in modo che uno è il **quindi** sezione di appena aggiunta **se** attività e l'altro è nel **Else** sezione.</span><span class="sxs-lookup"><span data-stu-id="99ba3-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="99ba3-151">Fare clic sui **WriteLine** attività nel **quindi** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="99ba3-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="99ba3-152">Fare clic sui **WriteLine** attività nel **Else** sezione per selezionarlo, quindi digitare l'espressione seguente nella **testo** casella dei valori.</span><span class="sxs-lookup"><span data-stu-id="99ba3-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="99ba3-153">Nell'esempio seguente viene illustrato il flusso di lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="99ba3-153">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="99ba3-154">![Flusso di lavoro sequenza completo](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="99ba3-154">![Completed Sequential Workflow](../../../docs/framework/windows-workflow-foundation/media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="99ba3-155">Per compilare il flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-155">To build the workflow</span></span>  
  
1.  <span data-ttu-id="99ba3-156">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="99ba3-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="99ba3-157">Per istruzioni su come eseguire il flusso di lavoro, vedere l'argomento successivo, [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="99ba3-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="99ba3-158">Se sono già state completate le [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) passaggio con uno stile diverso del flusso di lavoro e si desidera eseguirlo tramite il flusso di lavoro sequenza da questo passaggio, andare direttamente al [per compilare ed eseguire l'applicazione](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sezione [come: Eseguire un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="99ba3-158">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ba3-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ba3-159">See also</span></span>
- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="99ba3-160">Programmazione di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="99ba3-160">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
- [<span data-ttu-id="99ba3-161">Progettazione di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-161">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)
- [<span data-ttu-id="99ba3-162">Esercitazione introduttiva</span><span class="sxs-lookup"><span data-stu-id="99ba3-162">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
- [<span data-ttu-id="99ba3-163">Procedura: Creare un'attività</span><span class="sxs-lookup"><span data-stu-id="99ba3-163">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)
- [<span data-ttu-id="99ba3-164">Procedura: Eseguire un flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="99ba3-164">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
