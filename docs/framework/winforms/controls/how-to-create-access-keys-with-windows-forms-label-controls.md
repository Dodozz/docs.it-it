---
title: 'Procedura: Creare tasti di scelta con i controlli Label di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: ff603ee784978a8b2bab2cccd4610fc50b45d477
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171717"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="2ce20-102">Procedura: Creare tasti di scelta con i controlli Label di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ce20-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="2ce20-103">Windows Form <xref:System.Windows.Forms.Label> controlli possono essere utilizzati per definire le chiavi di accesso per altri controlli.</span><span class="sxs-lookup"><span data-stu-id="2ce20-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="2ce20-104">Quando si definisce una chiave di accesso in un controllo etichetta, l'utente può premere il tasto ALT più il carattere che si è scelto di spostare lo stato attivo al controllo che lo segue nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="2ce20-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="2ce20-105">Poiché le etichette non possono ricevere lo stato attivo, lo stato attivo si sposta automaticamente al controllo successivo nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="2ce20-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="2ce20-106">Usare questa tecnica per assegnare le chiavi di accesso per le caselle di testo, caselle combinate, caselle di riepilogo e griglie di dati.</span><span class="sxs-lookup"><span data-stu-id="2ce20-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="2ce20-107">Per assegnare una chiave di accesso a un controllo con un'etichetta</span><span class="sxs-lookup"><span data-stu-id="2ce20-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="2ce20-108">Creare prima l'etichetta e quindi disegnare l'altro controllo.</span><span class="sxs-lookup"><span data-stu-id="2ce20-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="2ce20-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="2ce20-109">-or-</span></span>  
  
     <span data-ttu-id="2ce20-110">Disegnare i controlli in qualsiasi ordine e impostare il <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà dell'etichetta di altro controllo meno uno.</span><span class="sxs-lookup"><span data-stu-id="2ce20-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="2ce20-111">Impostare l'etichetta <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="2ce20-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="2ce20-112">Usare una e commerciale (&) dell'etichetta <xref:System.Windows.Forms.Label.Text%2A> proprietà da assegnare la chiave di accesso per l'etichetta.</span><span class="sxs-lookup"><span data-stu-id="2ce20-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="2ce20-113">Per altre informazioni, vedere [creazione di chiavi per i controlli Windows Form](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2ce20-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ce20-114">È possibile visualizzare le e commerciali in un controllo etichetta, anziché a usarle per creare le chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="2ce20-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="2ce20-115">Ciò può verificarsi se si associa un controllo etichetta a un campo in un set di record in cui i dati includono le e commerciali.</span><span class="sxs-lookup"><span data-stu-id="2ce20-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="2ce20-116">Per visualizzare le e commerciali in un controllo etichetta, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="2ce20-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="2ce20-117">Se si desidera visualizzare le e commerciali e anche di una chiave di accesso, impostare il <xref:System.Windows.Forms.Label.UseMnemonic%2A> proprietà `true` e indicare la chiave di accesso con una e commerciale (&) e la e commerciale da visualizzare con due caratteri e commerciale.</span><span class="sxs-lookup"><span data-stu-id="2ce20-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2ce20-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ce20-118">See also</span></span>

- [<span data-ttu-id="2ce20-119">Procedura: Ridimensionare un controllo Label di Windows Forms in base al contenuto</span><span class="sxs-lookup"><span data-stu-id="2ce20-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="2ce20-120">Panoramica del controllo Label</span><span class="sxs-lookup"><span data-stu-id="2ce20-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="2ce20-121">Controllo Label</span><span class="sxs-lookup"><span data-stu-id="2ce20-121">Label Control</span></span>](label-control-windows-forms.md)
