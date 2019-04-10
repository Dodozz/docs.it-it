---
title: "Procedura: Aggiungere una schermata iniziale in un'applicazione WPF"
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 3120ee64d65822d323800a89466c6b707169aaaa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307498"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="974ef-102">Procedura: Aggiungere una schermata iniziale in un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="974ef-102">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="974ef-103">In questo argomento viene illustrato come aggiungere una finestra di avvio, oppure *schermata iniziale*, a un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="974ef-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="974ef-104">Per aggiungere un'immagine esistente come schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="974ef-104">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="974ef-105">Creare o trovare un'immagine che si desidera utilizzare per la schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="974ef-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="974ef-106">È possibile usare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="974ef-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="974ef-107">Ad esempio, è possibile utilizzare il formato TIFF, GIF, JPEG, PNG o BMP.</span><span class="sxs-lookup"><span data-stu-id="974ef-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="974ef-108">Aggiungere il file di immagine al progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="974ef-108">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="974ef-109">Nelle **Esplora soluzioni**, selezionare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="974ef-109">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="974ef-110">Nella finestra Proprietà, fare clic sulla freccia giù per il **azione di compilazione** proprietà.</span><span class="sxs-lookup"><span data-stu-id="974ef-110">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="974ef-111">Selezionare **SplashScreen** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="974ef-111">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="974ef-112">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="974ef-112">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="974ef-113">Immagine della schermata iniziale viene visualizzato al centro dello schermo e quindi scompare quando viene visualizzata la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="974ef-113">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="974ef-114">Per escludere la schermata iniziale di compilazione</span><span class="sxs-lookup"><span data-stu-id="974ef-114">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="974ef-115">Nelle **Esplora soluzioni**, selezionare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="974ef-115">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="974ef-116">Nel **proprietà** impostare nella finestra di **azione di compilazione** a **None**.</span><span class="sxs-lookup"><span data-stu-id="974ef-116">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="974ef-117">Per rimuovere la schermata da un'applicazione</span><span class="sxs-lookup"><span data-stu-id="974ef-117">To remove the splash screen from an application</span></span>

<span data-ttu-id="974ef-118">Nelle **Esplora soluzioni**, eliminare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="974ef-118">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="974ef-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="974ef-119">See also</span></span>

- <xref:System.Windows.SplashScreen>
- [<span data-ttu-id="974ef-120">Procedura: Aggiungere elementi esistenti a un progetto</span><span class="sxs-lookup"><span data-stu-id="974ef-120">How to: Add Existing Items to a Project</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
