---
title: "Procedura: Modificare l'aspetto di TabControl di Windows Forms"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 05df05a52914f27a4b62cf7bde92e5d942b6ea06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331338"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="ebdc4-102">Procedura: Modificare l'aspetto di TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ebdc4-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="ebdc4-103">È possibile modificare l'aspetto delle schede in Windows Form usando le proprietà del <xref:System.Windows.Forms.TabControl> e il <xref:System.Windows.Forms.TabPage> gli oggetti che costituiscono le singole schede nel controllo.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="ebdc4-104">L'impostazione di queste proprietà è possibile visualizzare le immagini nelle schede, visualizzare le schede in verticale, anziché in orizzontale, visualizzare più righe di schede e abilitare o disabilitare le schede a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="ebdc4-105">Per visualizzare un'icona nella parte dell'etichetta di una scheda</span><span class="sxs-lookup"><span data-stu-id="ebdc4-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="ebdc4-106">Aggiungere un <xref:System.Windows.Forms.ImageList> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="ebdc4-107">Aggiungere immagini all'elenco di immagini.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="ebdc4-108">Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [come: Aggiungere o rimuovere immagini tramite il Windows Form componente ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="ebdc4-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="ebdc4-109">Impostare il <xref:System.Windows.Forms.TabControl.ImageList%2A> proprietà del <xref:System.Windows.Forms.TabControl> per il <xref:System.Windows.Forms.ImageList> controllo.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="ebdc4-110">Impostare il <xref:System.Windows.Forms.TabPage.ImageIndex%2A> proprietà del <xref:System.Windows.Forms.TabPage> all'indice di un'immagine appropriata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="ebdc4-111">Per creare più righe di schede</span><span class="sxs-lookup"><span data-stu-id="ebdc4-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="ebdc4-112">Aggiungere il numero di pagine di scheda desiderata.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="ebdc4-113">Impostare il <xref:System.Windows.Forms.TabControl.Multiline%2A> proprietà del <xref:System.Windows.Forms.TabControl> a `true`.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="ebdc4-114">Se le schede non è già visualizzata in più righe, impostare il <xref:System.Windows.Forms.Control.Width%2A> proprietà del <xref:System.Windows.Forms.TabControl> sia larghezza di tutte le schede.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="ebdc4-115">Per disporre le schede sul lato del controllo</span><span class="sxs-lookup"><span data-stu-id="ebdc4-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="ebdc4-116">Impostare il <xref:System.Windows.Forms.TabControl.Alignment%2A> proprietà del <xref:System.Windows.Forms.TabControl> al <xref:System.Windows.Forms.TabAlignment.Left> o <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="ebdc4-117">Per abilitare o disabilitare tutti i controlli in una scheda a livello di codice</span><span class="sxs-lookup"><span data-stu-id="ebdc4-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="ebdc4-118">Impostare il <xref:System.Windows.Forms.TabPage.Enabled%2A> proprietà del <xref:System.Windows.Forms.TabPage> al `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="ebdc4-119">Per visualizzare le schede sotto forma di pulsanti</span><span class="sxs-lookup"><span data-stu-id="ebdc4-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="ebdc4-120">Impostare il <xref:System.Windows.Forms.TabControl.Appearance%2A> proprietà del <xref:System.Windows.Forms.TabControl> al <xref:System.Windows.Forms.TabAppearance.Buttons> o <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="ebdc4-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebdc4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebdc4-121">See also</span></span>

- [<span data-ttu-id="ebdc4-122">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="ebdc4-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="ebdc4-123">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="ebdc4-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="ebdc4-124">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="ebdc4-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="ebdc4-125">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="ebdc4-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="ebdc4-126">Procedura: Aggiungere e rimuovere schede con il controllo TabControl di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ebdc4-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
