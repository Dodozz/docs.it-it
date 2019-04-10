---
title: 'Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: e8bc4aa4ecd2bff2981b7d4faf1e270337f346e7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346210"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="b97b5-102">Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="b97b5-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="b97b5-103">Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b97b5-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="b97b5-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b97b5-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b97b5-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b97b5-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b97b5-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="b97b5-107">Per copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="b97b5-107">To copy and paste an ElementHost control at design time</span></span>  
  
1. <span data-ttu-id="b97b5-108">Aggiungere un nuovo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="b97b5-109">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="b97b5-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="b97b5-110">Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="b97b5-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="b97b5-111">Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di `UserControl1` per `200`.</span><span class="sxs-lookup"><span data-stu-id="b97b5-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3. <span data-ttu-id="b97b5-112">Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.</span><span class="sxs-lookup"><span data-stu-id="b97b5-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4. <span data-ttu-id="b97b5-113">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b97b5-113">Build the project.</span></span>  
  
5. <span data-ttu-id="b97b5-114">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6. <span data-ttu-id="b97b5-115">Dal **casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="b97b5-116">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="b97b5-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7. <span data-ttu-id="b97b5-117">Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="b97b5-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8. <span data-ttu-id="b97b5-118">Premere CTRL + V per incollare il controllo copiato nel form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="b97b5-119">Una nuova <xref:System.Windows.Forms.Integration.ElementHost> controllo denominato `elementHost2` viene creato nel form.</span><span class="sxs-lookup"><span data-stu-id="b97b5-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97b5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b97b5-120">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b97b5-121">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b97b5-121">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="b97b5-122">Utilizzo di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="b97b5-122">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="b97b5-123">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b97b5-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
