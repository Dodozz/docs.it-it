---
title: "Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 7aa5208a4f378408a01a08a2f4c9dbf2edfa5243
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776142"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="739b5-102">Procedura: Abilitare stili di visualizzazione in un'applicazione ibrida</span><span class="sxs-lookup"><span data-stu-id="739b5-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="739b5-103">In questo argomento viene illustrato come abilitare [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] gli stili di visualizzazione in un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.</span><span class="sxs-lookup"><span data-stu-id="739b5-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="739b5-104">Se l'applicazione chiama il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo, la maggior parte delle [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli userà automaticamente gli stili di visualizzazione quando l'applicazione viene eseguita in [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="739b5-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="739b5-105">Per altre informazioni, vedere [Rendering dei controlli con stili visivi](../../winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="739b5-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="739b5-106">Per un listato di codice completo delle attività illustrate in questo argomento, vedere [abilitazione stili di visualizzazione in un'applicazione ibrida](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="739b5-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="739b5-107">Attivazione degli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="739b5-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="739b5-108">Per attivare gli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="739b5-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="739b5-109">Creare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto di applicazione denominato `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="739b5-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="739b5-110">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.</span><span class="sxs-lookup"><span data-stu-id="739b5-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="739b5-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="739b5-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="739b5-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="739b5-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="739b5-113">Nella casella degli strumenti, fare doppio clic il <xref:System.Windows.Controls.Grid> icona per posizionare un <xref:System.Windows.Controls.Grid> elemento nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="739b5-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="739b5-114">Nella finestra Proprietà, impostare i valori del <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> delle proprietà per **Auto**.</span><span class="sxs-lookup"><span data-stu-id="739b5-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="739b5-115">Nella visualizzazione progettazione o XAML, selezionare il <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="739b5-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="739b5-116">Nella finestra Proprietà scegliere il **eventi** scheda.</span><span class="sxs-lookup"><span data-stu-id="739b5-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="739b5-117">Fare doppio clic il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="739b5-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="739b5-118">In MainWindow.xaml.cs o MainWindow. Xaml. vb, inserire il codice seguente per gestire il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="739b5-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="739b5-119">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="739b5-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="739b5-120">Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene disegnato con stili visivi.</span><span class="sxs-lookup"><span data-stu-id="739b5-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="739b5-121">Disattivazione degli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="739b5-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="739b5-122">Per disabilitare gli stili di visualizzazione, rimuovere semplicemente la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="739b5-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="739b5-123">Per disattivare gli stili di visualizzazione Windows Form</span><span class="sxs-lookup"><span data-stu-id="739b5-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="739b5-124">Aprire MainWindow.xaml.vb o MainWindow.xaml.cs nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="739b5-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="739b5-125">Commentare la chiamata al <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="739b5-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="739b5-126">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="739b5-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="739b5-127">Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo viene disegnato con lo stile di sistema predefinito.</span><span class="sxs-lookup"><span data-stu-id="739b5-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739b5-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="739b5-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="739b5-129">Rendering dei controlli con stili visivi</span><span class="sxs-lookup"><span data-stu-id="739b5-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="739b5-130">Procedura dettagliata: Hosting di controlli Windows Form in WPF</span><span class="sxs-lookup"><span data-stu-id="739b5-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
