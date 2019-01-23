---
title: 'Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 49421fc6c673ffe090e58d733ff0a309464edbb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527744"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="a3ce1-102">Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="a3ce1-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="a3ce1-103">Questa procedura dettagliata illustra come selezionare i tipi di controllo Windows Presentation Foundation (WPF) da visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="a3ce1-104">È possibile selezionare qualsiasi tipo di controllo WPF incluso nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="a3ce1-105">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3ce1-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="a3ce1-106">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-106">Create the project.</span></span>

-   <span data-ttu-id="a3ce1-107">Creare i tipi di controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-107">Create the WPF control types.</span></span>

-   <span data-ttu-id="a3ce1-108">Selezionare i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="a3ce1-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a3ce1-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a3ce1-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a3ce1-111">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a3ce1-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3ce1-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a3ce1-112">Prerequisites</span></span>  
 <span data-ttu-id="a3ce1-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3ce1-113">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="a3ce1-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="a3ce1-115">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="a3ce1-115">Creating the Project</span></span>  
 <span data-ttu-id="a3ce1-116">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3ce1-117">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="a3ce1-118">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="a3ce1-118">To create the project</span></span>  
  
-   <span data-ttu-id="a3ce1-119">Creare un nuovo progetto Windows Forms Application in Visual Basic o Visual c# denominato `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="a3ce1-120">Creazione di tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="a3ce1-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="a3ce1-121">Dopo avere aggiunto i tipi di controllo WPF al progetto, è possibile includerli in controlli <xref:System.Windows.Forms.Integration.ElementHost> diversi.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="a3ce1-122">Per creare i tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="a3ce1-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="a3ce1-123">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="a3ce1-124">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="a3ce1-125">Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="a3ce1-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="a3ce1-126">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="a3ce1-127">Per altre informazioni, vedere [Procedura: Selezionare e spostare gli elementi nell'area di progettazione](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="a3ce1-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="a3ce1-128">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="a3ce1-129">Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="a3ce1-130">Aggiungere un secondo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="a3ce1-131">Usare il nome predefinito per il tipo di controllo, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="a3ce1-132">Nel **le proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà da `200`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="a3ce1-133">Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> il controllo al <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="a3ce1-134">**Nota** In generale, è opportuno ospitare contenuto WPF più sofisticato.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="a3ce1-135">Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="a3ce1-136">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="a3ce1-137">Selezione di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="a3ce1-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="a3ce1-138">È possibile assegnare contenuto WPF diverso a un controllo <xref:System.Windows.Forms.Integration.ElementHost> che include già contenuto.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="a3ce1-139">Per selezionare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="a3ce1-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="a3ce1-140">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="a3ce1-141">Nel **casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="a3ce1-142">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="a3ce1-143">Nel pannello smart tag per `elementHost1`, aprire il **selezione contenuto ospitato** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="a3ce1-144">Selezionare **UserControl2** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="a3ce1-145">Il controllo `elementHost1` include ora un'istanza del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="a3ce1-146">Nel **delle proprietà** finestra, verificare che il <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> è impostata su **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="a3ce1-147">Dal **casella degli strumenti**, nella **interoperabilità WPF** gruppo, trascinare un <xref:System.Windows.Forms.Integration.ElementHost> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="a3ce1-148">Il nome predefinito del nuovo controllo è `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="a3ce1-149">Nel pannello smart tag per `elementHost2`, aprire il **selezione contenuto ospitato** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="a3ce1-150">Selezionare **UserControl1** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="a3ce1-151">Il controllo `elementHost2` include ora un'istanza del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="a3ce1-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ce1-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3ce1-152">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a3ce1-153">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a3ce1-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="a3ce1-154">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="a3ce1-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="a3ce1-155">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3ce1-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
