---
title: "Procedura dettagliata: Localizzazione di un'applicazione ibrida"
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 6b7db8182b5764e3df65ccbdef3b54330c1ee64a
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223006"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="ec555-102">Procedura dettagliata: Localizzazione di un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="ec555-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="ec555-103">Questa procedura dettagliata mostra come localizzare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-basato su un'applicazione ibrida.</span><span class="sxs-lookup"><span data-stu-id="ec555-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="ec555-104">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec555-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="ec555-105">Creazione di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] progetto host.</span><span class="sxs-lookup"><span data-stu-id="ec555-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

-   <span data-ttu-id="ec555-106">Aggiunta di contenuto localizzabile.</span><span class="sxs-lookup"><span data-stu-id="ec555-106">Adding localizable content.</span></span>

-   <span data-ttu-id="ec555-107">Abilitazione della localizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec555-107">Enabling localization.</span></span>

-   <span data-ttu-id="ec555-108">Assegnazione di identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="ec555-108">Assigning resource identifiers.</span></span>

-   <span data-ttu-id="ec555-109">Utilizzo dello strumento LocBaml per produrre un assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="ec555-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="ec555-110">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [localizzazione di un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="ec555-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="ec555-111">Al termine, sarà disponibile un'applicazione ibrida localizzata.</span><span class="sxs-lookup"><span data-stu-id="ec555-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec555-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ec555-112">Prerequisites</span></span>

<span data-ttu-id="ec555-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec555-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="ec555-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="ec555-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="ec555-115">Creazione del progetto host Windows Form</span><span class="sxs-lookup"><span data-stu-id="ec555-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="ec555-116">Il primo passaggio consiste nel creare il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazione del progetto e aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento con contenuto da localizzare.</span><span class="sxs-lookup"><span data-stu-id="ec555-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="ec555-117">Per creare il progetto host</span><span class="sxs-lookup"><span data-stu-id="ec555-117">To create the host project</span></span>

1.  <span data-ttu-id="ec555-118">Creare un **applicazione WPF** progetto denominato `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="ec555-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="ec555-119">(**File** > **nuova** > **progetto** > **Visual C#** o **Visual Basic**   >  **Desktop classico** > **applicazione WPF**).</span><span class="sxs-lookup"><span data-stu-id="ec555-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2.  <span data-ttu-id="ec555-120">Aggiungere un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> elemento denominato `SimpleControl` al progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3.  <span data-ttu-id="ec555-121">Usare la <xref:System.Windows.Forms.Integration.ElementHost> controllo di posizionarsi un `SimpleControl` elemento nel form.</span><span class="sxs-lookup"><span data-stu-id="ec555-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="ec555-122">Per altre informazioni, vedere [Procedura dettagliata: Hosting di controlli compositi 3D di WPF in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ec555-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="ec555-123">Aggiunta di contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="ec555-123">Adding Localizable Content</span></span>

<span data-ttu-id="ec555-124">Successivamente, si aggiungerà un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo etichetta e impostare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto dell'elemento in una stringa localizzabile.</span><span class="sxs-lookup"><span data-stu-id="ec555-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="ec555-125">Per aggiungere contenuto localizzabile</span><span class="sxs-lookup"><span data-stu-id="ec555-125">To add localizable content</span></span>

1.  <span data-ttu-id="ec555-126">Nella **Esplora soluzioni**, fare doppio clic su **SimpleControl** aprirla nel [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec555-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2.  <span data-ttu-id="ec555-127">Impostare il contenuto del <xref:System.Windows.Controls.Button> controllo usando il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ec555-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3.  <span data-ttu-id="ec555-128">Nelle **Esplora soluzioni**, fare doppio clic su **Form1** per aprirlo in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ec555-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4.  <span data-ttu-id="ec555-129">Aprire il **casella degli strumenti** e fare doppio clic su **etichetta** per aggiungere un controllo etichetta al form.</span><span class="sxs-lookup"><span data-stu-id="ec555-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="ec555-130">Impostare il valore della proprietà <xref:System.Windows.Forms.Control.Text%2A> su `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="ec555-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5.  <span data-ttu-id="ec555-131">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ec555-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="ec555-132">Entrambi i `SimpleControl` elemento e il controllo etichetta il testo viene visualizzato **"Hello"**.</span><span class="sxs-lookup"><span data-stu-id="ec555-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="ec555-133">Abilitazione della localizzazione</span><span class="sxs-lookup"><span data-stu-id="ec555-133">Enabling Localization</span></span>

<span data-ttu-id="ec555-134">Progettazione Windows Form fornisce le impostazioni per abilitare la localizzazione in un assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="ec555-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="ec555-135">Per abilitare la localizzazione</span><span class="sxs-lookup"><span data-stu-id="ec555-135">To enable localization</span></span>

1.  <span data-ttu-id="ec555-136">Nelle **Esplora soluzioni**, fare doppio clic su **Form1.cs** per aprirlo in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ec555-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2.  <span data-ttu-id="ec555-137">Nel **delle proprietà** finestra, impostare il valore dell'oggetto del form **Localizable** proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="ec555-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3.  <span data-ttu-id="ec555-138">Nel **le proprietà** finestra, impostare il valore della **Language** proprietà **spagnolo (Spagna)**.</span><span class="sxs-lookup"><span data-stu-id="ec555-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4.  <span data-ttu-id="ec555-139">In Progettazione Windows Form selezionare il controllo etichetta.</span><span class="sxs-lookup"><span data-stu-id="ec555-139">In the Windows Forms Designer, select the label control.</span></span>

5.  <span data-ttu-id="ec555-140">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Control.Text%2A> proprietà `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="ec555-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="ec555-141">Un nuovo file di risorse denominato Form1.es-ES.resx verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6.  <span data-ttu-id="ec555-142">Nelle **Esplora soluzioni**, fare doppio clic su **Form1.cs** e fare clic su **Visualizza codice** per aprirlo nell'Editor del codice.</span><span class="sxs-lookup"><span data-stu-id="ec555-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7.  <span data-ttu-id="ec555-143">Copiare il codice seguente nel `Form1` costruttore, prima di chiamare `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="ec555-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8.  <span data-ttu-id="ec555-144">Nelle **Esplora soluzioni**, fare doppio clic su **LocalizingWpfInWf** e fare clic su **Scarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="ec555-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="ec555-145">Il nome del progetto viene etichettato **(non disponibile)**.</span><span class="sxs-lookup"><span data-stu-id="ec555-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="ec555-146">Fare doppio clic su **LocalizingWpfInWf**, fare clic su **Modifica LocalizingWpfInWf**.</span><span class="sxs-lookup"><span data-stu-id="ec555-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="ec555-147">Il file di progetto verrà aperto nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="ec555-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="ec555-148">Copiare la riga seguente nel primo `PropertyGroup` nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="ec555-149">Salvare e chiudere il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="ec555-150">Nelle **Esplora soluzioni**, fare doppio clic su **LocalizingWpfInWf** e fare clic su **Ricarica progetto**.</span><span class="sxs-lookup"><span data-stu-id="ec555-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="ec555-151">Assegnazione di identificatori di risorsa</span><span class="sxs-lookup"><span data-stu-id="ec555-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="ec555-152">È possibile eseguire il mapping del contenuto localizzabile agli assembly di risorse usando identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="ec555-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="ec555-153">L'applicazione MsBuild.exe assegna automaticamente gli identificatori di risorsa quando si specifica il `updateuid` opzione.</span><span class="sxs-lookup"><span data-stu-id="ec555-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="ec555-154">Per assegnare identificatori di risorsa</span><span class="sxs-lookup"><span data-stu-id="ec555-154">To assign resource identifiers</span></span>

1.  <span data-ttu-id="ec555-155">Dal Menu Start, aprire il prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec555-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2.  <span data-ttu-id="ec555-156">Per assegnare identificatori di risorsa al contenuto localizzabile, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="ec555-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3.  <span data-ttu-id="ec555-157">Nelle **Esplora soluzioni**, fare doppio clic su **SimpleControl** per aprirlo nell'Editor del codice.</span><span class="sxs-lookup"><span data-stu-id="ec555-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="ec555-158">Si noterà che il `msbuild` comando è stato aggiunto il `Uid` attributo per tutti gli elementi.</span><span class="sxs-lookup"><span data-stu-id="ec555-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="ec555-159">In tal modo si semplifica la localizzazione mediante l'assegnazione di identificatori di risorsa.</span><span class="sxs-lookup"><span data-stu-id="ec555-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4.  <span data-ttu-id="ec555-160">Premere **F6** per compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="ec555-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="ec555-161">Utilizzo dello strumento LocBaml per produrre un assembly satellite</span><span class="sxs-lookup"><span data-stu-id="ec555-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="ec555-162">Il contenuto localizzato viene memorizzato in una risorsa sola *assembly satellite*.</span><span class="sxs-lookup"><span data-stu-id="ec555-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="ec555-163">Usare lo strumento da riga di comando LocBaml.exe per produrre un assembly localizzato per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto.</span><span class="sxs-lookup"><span data-stu-id="ec555-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="ec555-164">Per produrre un assembly satellite</span><span class="sxs-lookup"><span data-stu-id="ec555-164">To produce a satellite assembly</span></span>

1.  <span data-ttu-id="ec555-165">Copiare LocBaml.exe nella cartella obj\Debug del progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="ec555-166">Per altre informazioni, vedere [localizzare un'applicazione](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="ec555-166">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>

2.  <span data-ttu-id="ec555-167">Nella finestra del prompt dei comandi usare il comando seguente per estrarre stringhe di risorsa in un file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="ec555-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3.  <span data-ttu-id="ec555-168">Aprire il file TEMP con Visual Studio o un altro editor di testo.</span><span class="sxs-lookup"><span data-stu-id="ec555-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="ec555-169">Sostituire la stringa `"Hello"` con la relativa traduzione spagnola, `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="ec555-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4.  <span data-ttu-id="ec555-170">Salvare il file temp.csv.</span><span class="sxs-lookup"><span data-stu-id="ec555-170">Save the temp.csv file.</span></span>

5.  <span data-ttu-id="ec555-171">Per generare il file di risorse localizzato, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="ec555-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="ec555-172">Il file LocalizingWpfInWf.g.es-ES.resources viene creato nella cartella obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="ec555-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6.  <span data-ttu-id="ec555-173">Per compilare l'assembly satellite localizzato, usare il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="ec555-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="ec555-174">Il file LocalizingWpfInWf.resources.dll viene creato nella cartella obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="ec555-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7.  <span data-ttu-id="ec555-175">Copiare il file LocalizingWpfInWf.resources.dll nella cartella bin\Debug\es-ES del progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="ec555-176">Sostituire il file esistente.</span><span class="sxs-lookup"><span data-stu-id="ec555-176">Replace the existing file.</span></span>

8.  <span data-ttu-id="ec555-177">Eseguire LocalizingWpfInWf.exe, situato nella cartella bin\Debug del progetto.</span><span class="sxs-lookup"><span data-stu-id="ec555-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="ec555-178">Non ricompilare l'applicazione altrimenti l'assembly satellite verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="ec555-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="ec555-179">Nell'applicazione vengono visualizzate le stringhe localizzate invece delle stringhe in inglese.</span><span class="sxs-lookup"><span data-stu-id="ec555-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec555-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec555-180">See Also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ec555-181">Localizzare un'applicazione</span><span class="sxs-lookup"><span data-stu-id="ec555-181">Localize an Application</span></span>](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)
- [<span data-ttu-id="ec555-182">Procedura dettagliata: Localizzazione di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ec555-182">Walkthrough: Localizing Windows Forms</span></span>](https://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)
- [<span data-ttu-id="ec555-183">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ec555-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
