---
title: Compilare una libreria di classi .NET Standard in C# con Visual Studio 2017
description: Informazioni su come creare una libreria di classi .NET Standard scritta in C# usando Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 0c98f8c8fc4847570964d8d4ea8deb221164441d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168936"
---
# <a name="build-a-net-standard-class-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="31d80-103">Compilare una libreria di classi .NET Standard con C# e .NET Core SDK in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="31d80-103">Build a .NET Standard class library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="31d80-104">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="31d80-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="31d80-105">Una libreria di classi che esegue la destinazione a .NET Standard 2.0 consente la chiamata alla libreria da qualsiasi implementazione di .NET che supporti questa versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="31d80-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="31d80-106">Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="31d80-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="31d80-107">Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="31d80-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="31d80-108">In questo argomento si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe,</span><span class="sxs-lookup"><span data-stu-id="31d80-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="31d80-109">che verrà implementato come [metodo di estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md), in modo da poter essere chiamato come se fosse un membro della classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="31d80-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="31d80-110">Creazione di una soluzione per la libreria di classi</span><span class="sxs-lookup"><span data-stu-id="31d80-110">Creating a class library solution</span></span>

<span data-ttu-id="31d80-111">Iniziare creando una soluzione per il progetto di libreria di classi e per i progetti correlati.</span><span class="sxs-lookup"><span data-stu-id="31d80-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="31d80-112">Una soluzione Visual Studio funge solo da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="31d80-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="31d80-113">Per creare la soluzione:</span><span class="sxs-lookup"><span data-stu-id="31d80-113">To create the solution:</span></span>

1. <span data-ttu-id="31d80-114">Nella barra dei menu di Visual Studio scegliere **File** > **Nuovo** > **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="31d80-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="31d80-115">Nella finestra di dialogo **Nuovo progetto** espandere il nodo **Altri tipi di progetti** e selezionare **Soluzioni di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="31d80-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="31d80-116">Assegnare alla soluzione il nome "ClassLibraryProjects" e selezionare il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="31d80-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Finestra di dialogo Nuovo progetto con la nuova soluzione vuota evidenziata](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="31d80-118">Creazione del progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="31d80-118">Creating the class library project</span></span>

<span data-ttu-id="31d80-119">Creare un progetto di libreria di classi:</span><span class="sxs-lookup"><span data-stu-id="31d80-119">Create your class library project:</span></span>

1. <span data-ttu-id="31d80-120">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file della soluzione **ClassLibraryProjects** e dal menu di scelta rapida selezionare **Aggiungi** > **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="31d80-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="31d80-121">Nella finestra di dialogo **Aggiungi nuovo progetto** espandere il nodo **Visual C#**, quindi selezionare il nodo **.NET Standard** seguito dal modello di progetto **Libreria di classi (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="31d80-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="31d80-122">Nella casella di testo **Nome** immettere "StringLibrary" come nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="31d80-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="31d80-123">Scegliere **OK** per creare il progetto di libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="31d80-123">Select **OK** to create the class library project.</span></span>

   ![Finestra di dialogo Aggiungi nuovo progetto per libreria di classi](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="31d80-125">La finestra di codice viene quindi aperta nell'ambiente di sviluppo di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31d80-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![Finestra dell'applicazione di Visual Studio che illustra il codice del modello della libreria di classi predefinito](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="31d80-127">Assicurarsi che sia stata eseguita la destinazione della libreria alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="31d80-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="31d80-128">Fare clic con il pulsante destro del mouse sul progetto libreria nelle finestre di **Esplora soluzioni**, quindi selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="31d80-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="31d80-129">La casella di testo **Framework di destinazione** indica che si sta eseguendo la destinazione a .NET 2.0 Standard.</span><span class="sxs-lookup"><span data-stu-id="31d80-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="31d80-131">Nella finestra del codice sostituire il codice con il seguente:</span><span class="sxs-lookup"><span data-stu-id="31d80-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="31d80-132">La libreria di classi `UtilityLibraries.StringLibrary` contiene un metodo denominato `StartsWithUpper`, che restituisce un valore <xref:System.Boolean> che indica se l'istanza della stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="31d80-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="31d80-133">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="31d80-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="31d80-134">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="31d80-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="31d80-135">Nella barra dei menu selezionare **Compila** > **Compila soluzione**.</span><span class="sxs-lookup"><span data-stu-id="31d80-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="31d80-136">Il progetto dovrebbe essere compilato senza errori.</span><span class="sxs-lookup"><span data-stu-id="31d80-136">The project should compile without error.</span></span>

   ![Riquadro di output che illustra che la compilazione ha avuto esito positivo](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="31d80-138">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="31d80-138">Next step</span></span>

<span data-ttu-id="31d80-139">La compilazione della libreria è stata completata.</span><span class="sxs-lookup"><span data-stu-id="31d80-139">You've successfully built the library.</span></span> <span data-ttu-id="31d80-140">Non è tuttavia possibile sapere se funziona come previsto poiché non è stato ancora chiamato uno dei metodi.</span><span class="sxs-lookup"><span data-stu-id="31d80-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="31d80-141">Il passaggio successivo per lo sviluppo della libreria consiste nel testarla usando un [Progetto unit test](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="31d80-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>