---
title: Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac
description: In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: f751e7532e9627de3d3733476f7214654089e468
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744114"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="75e2f-103">Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="75e2f-103">Getting started with .NET Core on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="75e2f-104">Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75e2f-104">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="75e2f-105">In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75e2f-105">This topic walks you through building a simple console application using Visual Studio for Mac and .NET Core.</span></span>

> [!NOTE]
> <span data-ttu-id="75e2f-106">Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="75e2f-106">Your feedback is highly valued.</span></span> <span data-ttu-id="75e2f-107">Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="75e2f-107">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="75e2f-108">In Visual Studio per Mac scegliere **Aiuto** > **Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per l'archiviazione di un report sul bug.</span><span class="sxs-lookup"><span data-stu-id="75e2f-108">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="75e2f-109">È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="75e2f-109">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="75e2f-110">Per inviare un suggerimento, scegliere **Aiuto** > **Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web Developer Community di Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="75e2f-110">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75e2f-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="75e2f-111">Prerequisites</span></span>

<span data-ttu-id="75e2f-112">Vedere l'argomento [Prerequisiti per .NET Core in Mac](../../core/macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="75e2f-112">See the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md) topic.</span></span>

## <a name="getting-started"></a><span data-ttu-id="75e2f-113">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="75e2f-113">Getting started</span></span>

<span data-ttu-id="75e2f-114">Se i prerequisiti e Visual Studio per Mac sono già installati, ignorare questa sezione e passare a [Creazione di un progetto](#creating-a-project).</span><span class="sxs-lookup"><span data-stu-id="75e2f-114">If you've already installed the prerequisites and Visual Studio for Mac, skip this section and proceed to [Creating a project](#creating-a-project).</span></span> <span data-ttu-id="75e2f-115">Seguire questa procedura per installare i prerequisiti e Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="75e2f-115">Follow these steps to install the prerequisites and Visual Studio for Mac:</span></span>

<span data-ttu-id="75e2f-116">Scaricare il [programma di installazione di Visual Studio per Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="75e2f-116">Download the [Visual Studio for Mac installer](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> <span data-ttu-id="75e2f-117">Eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="75e2f-117">Run the installer.</span></span> <span data-ttu-id="75e2f-118">Leggere e accettare il contratto di licenza.</span><span class="sxs-lookup"><span data-stu-id="75e2f-118">Read and accept the license agreement.</span></span> <span data-ttu-id="75e2f-119">Durante l'installazione viene offerta la possibilità di installare Xamarin, una tecnologia per lo sviluppo di app per dispositivi mobili multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="75e2f-119">During the install, you're provided the opportunity to install Xamarin, a cross-platform mobile app development technology.</span></span> <span data-ttu-id="75e2f-120">L'installazione di Xamarin e dei relativi componenti è facoltativa per lo sviluppo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75e2f-120">Installing Xamarin and its related components is optional for .NET Core development.</span></span> <span data-ttu-id="75e2f-121">Per una descrizione dettagliata del processo di installazione di Visual Studio per Mac, vedere [Presentazione di Visual Studio per Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="75e2f-121">For a walk-through of the Visual Studio for Mac install process, see [Introducing Visual Studio for Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/).</span></span> <span data-ttu-id="75e2f-122">Al termine dell'installazione, avviare l'IDE di Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="75e2f-122">When the install is complete, start the Visual Studio for Mac IDE.</span></span>

## <a name="creating-a-project"></a><span data-ttu-id="75e2f-123">Creazione di un progetto</span><span class="sxs-lookup"><span data-stu-id="75e2f-123">Creating a project</span></span>

1. <span data-ttu-id="75e2f-124">Nella schermata iniziale selezionare **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="75e2f-124">Select **New Project** on the Welcome screen.</span></span>

   ![Nuovo pulsante di progetto nella schermata iniziale di Visual Studio per Mac](./media/using-on-mac-vs/vsmac1.png)

1. <span data-ttu-id="75e2f-126">Nella finestra di dialogo **Nuovo progetto** selezionare **App** sotto il nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="75e2f-126">In the **New Project** dialog, select **App** under the **.NET Core** node.</span></span> <span data-ttu-id="75e2f-127">Selezionare il modello **Applicazione console** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="75e2f-127">Select the **Console Application** template followed by **Next**.</span></span>

   ![Nuovo elenco di modelli di progetto](./media/using-on-mac-vs/vsmac2.png)

1. <span data-ttu-id="75e2f-129">Digitare "HelloWorld" nel campo **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="75e2f-129">Type "HelloWorld" for the **Project Name**.</span></span> <span data-ttu-id="75e2f-130">Scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="75e2f-130">Select **Create**.</span></span>

   ![Finestra di dialogo di configurazione della nuova applicazione console](./media/using-on-mac-vs/vsmac3.png)

1. <span data-ttu-id="75e2f-132">Attendere che vengano ripristinate le dipendenze del progetto.</span><span class="sxs-lookup"><span data-stu-id="75e2f-132">Wait while the project's dependencies are restored.</span></span> <span data-ttu-id="75e2f-133">Il progetto è costituito da un unico file C#, *Program.cs*, contenente una classe `Program` con un metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="75e2f-133">The project has a single C# file, *Program.cs*, containing a `Program` class with a `Main` method.</span></span> <span data-ttu-id="75e2f-134">L'istruzione `Console.WriteLine` consentirà la visualizzazione di "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="75e2f-134">The `Console.WriteLine` statement will output "Hello World!"</span></span> <span data-ttu-id="75e2f-135">nella console all'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="75e2f-135">to the console when the app is run.</span></span>

   ![Finestra principale con il file Program.cs aperto](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a><span data-ttu-id="75e2f-137">Esecuzione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="75e2f-137">Run the application</span></span>

<span data-ttu-id="75e2f-138">Eseguire l'app in modalità di debug premendo <kbd>F5</kbd> o in modalità di rilascio premendo <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="75e2f-138">Run the app in Debug mode using <kbd>F5</kbd> or in Release mode using <kbd>CTRL</kbd>+<kbd>F5</kbd>.</span></span>

![Nel riquadro di output dell'applicazione viene visualizzato Hello World!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a><span data-ttu-id="75e2f-140">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="75e2f-140">Next step</span></span>

<span data-ttu-id="75e2f-141">L'argomento [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](using-on-mac-vs-full-solution.md) illustra come creare una soluzione .NET Core completa contenente librerie riutilizzabili e unit test.</span><span class="sxs-lookup"><span data-stu-id="75e2f-141">The [Building a complete .NET Core solution on macOS using Visual Studio for Mac](using-on-mac-vs-full-solution.md) topic shows you how to build a complete .NET Core solution that includes a reusable library and unit testing.</span></span>
