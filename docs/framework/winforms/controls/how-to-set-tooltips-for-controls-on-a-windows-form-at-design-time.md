---
title: 'Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: cc8f8c620516a943d6d70187e19b72f5a2a99888
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013075"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="1b0a4-102">Procedura: Impostare le descrizioni comando per i controlli in un Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1b0a4-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="1b0a4-103">È possibile impostare un <xref:System.Windows.Forms.ToolTip> stringa nel codice o nella finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="1b0a4-104">Per altre informazioni sul <xref:System.Windows.Forms.ToolTip> componente, vedere [Cenni preliminari sul componente ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1b0a4-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0a4-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1b0a4-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1b0a4-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1b0a4-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1b0a4-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="1b0a4-108">Per impostare una descrizione comandi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1b0a4-108">To set a ToolTip programmatically</span></span>  
  
1. <span data-ttu-id="1b0a4-109">Aggiungere il controllo che verrà visualizzata la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-109">Add the control that will display the ToolTip.</span></span>  
  
2. <span data-ttu-id="1b0a4-110">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="1b0a4-111">Per impostare una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1b0a4-111">To set a ToolTip in the designer</span></span>  
  
1. <span data-ttu-id="1b0a4-112">Aggiungere un componente <xref:System.Windows.Forms.ToolTip> al form.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2. <span data-ttu-id="1b0a4-113">Selezionare il controllo che consente di visualizzare la descrizione comando o aggiungerlo al form.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3. <span data-ttu-id="1b0a4-114">Nel **proprietà** impostare nella finestra di **descrizione comando su ToolTip1** valore da una stringa di testo appropriata.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="1b0a4-115">Per rimuovere una descrizione comandi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1b0a4-115">To remove a ToolTip programmatically</span></span>  
  
1. <span data-ttu-id="1b0a4-116">Usare il <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> metodo di <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-116">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a><span data-ttu-id="1b0a4-117">Per rimuovere una descrizione comando nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1b0a4-117">To remove a ToolTip in the designer</span></span>  
  
1. <span data-ttu-id="1b0a4-118">Selezionare il controllo che visualizza la descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-118">Select the control that is displaying the ToolTip.</span></span>  
  
2. <span data-ttu-id="1b0a4-119">Nel **delle proprietà** finestra, eliminare il testo nel **descrizione comando su ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-119">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1b0a4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b0a4-120">See also</span></span>

- [<span data-ttu-id="1b0a4-121">Panoramica sul componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="1b0a4-121">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="1b0a4-122">Procedura: Modifica del ritardo del componente di descrizione comando di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1b0a4-122">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="1b0a4-123">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="1b0a4-123">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
