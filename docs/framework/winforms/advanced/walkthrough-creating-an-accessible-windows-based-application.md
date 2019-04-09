---
title: "Procedura dettagliata: Creazione di un'applicazione Windows ad accesso facilitato"
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: 6d246c56af191189fa775be3248d3099d2aa2544
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203691"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="cae7d-102">Procedura dettagliata: Creazione di un'applicazione Windows ad accesso facilitato</span><span class="sxs-lookup"><span data-stu-id="cae7d-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="cae7d-103">La creazione di un'applicazione accessibile ha risvolti importanti per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="cae7d-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="cae7d-104">Molti governi hanno norme relative all'accessibilità per l'acquisto del software.</span><span class="sxs-lookup"><span data-stu-id="cae7d-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="cae7d-105">Il logo Certified for Windows include requisiti di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="cae7d-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="cae7d-106">È stato stimato che solo negli Stati Uniti risiedono 30 milioni di persone, molte delle quali potenziali clienti, interessate all'accessibilità del software.</span><span class="sxs-lookup"><span data-stu-id="cae7d-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="cae7d-107">Questa procedura dettagliata illustra i cinque requisiti di accessibilità per il logo Certified for Windows.</span><span class="sxs-lookup"><span data-stu-id="cae7d-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="cae7d-108">In base a questi requisiti, un'applicazione accessibile deve:</span><span class="sxs-lookup"><span data-stu-id="cae7d-108">According to these requirements, an accessible application will:</span></span>  
  
-   <span data-ttu-id="cae7d-109">Supportare le impostazioni di dimensioni, tipi di caratteri, colori e input del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="cae7d-110">La barra dei menu, la barra del titolo, i bordi e la barra di stato verranno ridimensionati automaticamente quando l'utente modifica le impostazioni del Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="cae7d-111">In questa applicazione non sono necessarie altre modifiche ai controlli o al codice.</span><span class="sxs-lookup"><span data-stu-id="cae7d-111">No additional changes to the controls or code are required in this application.</span></span>  
  
-   <span data-ttu-id="cae7d-112">Supportare la modalità contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="cae7d-112">Support High Contrast mode.</span></span>  
  
-   <span data-ttu-id="cae7d-113">Fornire l'accesso da tastiera documentato a tutte le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cae7d-113">Provide documented keyboard access to all features.</span></span>  
  
-   <span data-ttu-id="cae7d-114">Esporre la posizione dello stato attivo della tastiera a livello visivo o di programmazione.</span><span class="sxs-lookup"><span data-stu-id="cae7d-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
-   <span data-ttu-id="cae7d-115">Evitare di comunicare informazioni importanti solo tramite segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="cae7d-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="cae7d-116">Per altre informazioni, vedere [Risorse per la progettazione di applicazioni accessibili](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="cae7d-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="cae7d-117">Per informazioni sul supporto di diversi layout di tastiera, vedere [Procedure consigliate per lo sviluppo di applicazioni internazionali](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cae7d-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="cae7d-118">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="cae7d-118">Creating the Project</span></span>  
 <span data-ttu-id="cae7d-119">Questa procedura dettagliata crea l'interfaccia utente per un'applicazione che accetta ordini di pizza.</span><span class="sxs-lookup"><span data-stu-id="cae7d-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="cae7d-120">È costituita da un oggetto <xref:System.Windows.Forms.TextBox> per il nome del cliente, un gruppo di <xref:System.Windows.Forms.RadioButton> per selezionare la dimensione della pizza, un oggetto <xref:System.Windows.Forms.CheckedListBox> per selezionare i condimenti, due pulsanti con etichetta Order e Cancel e un menu con un comando Exit.</span><span class="sxs-lookup"><span data-stu-id="cae7d-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="cae7d-121">L'utente immette il nome del cliente, la dimensione della pizza e gli ingredienti desiderati.</span><span class="sxs-lookup"><span data-stu-id="cae7d-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="cae7d-122">Quando l'utente fa clic sul pulsante Order, in una finestra di messaggio vengono visualizzati un riepilogo dell'ordine e il costo. I controlli vengono cancellati e sono pronti per l'ordine successivo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="cae7d-123">Quando l'utente fa clic sul pulsante Cancel, i controlli vengono cancellati e sono pronti per l'ordine successivo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="cae7d-124">Quando l'utente fa clic sulla voce di menu Exit, il programma si chiude.</span><span class="sxs-lookup"><span data-stu-id="cae7d-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="cae7d-125">In questa procedura dettagliata l'elemento importante non è il codice per un sistema di ordini di vendita al dettaglio, ma l'accessibilità dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cae7d-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="cae7d-126">La procedura dettagliata illustra le funzionalità di accessibilità di diversi controlli usati di frequente, tra cui pulsanti, pulsanti di opzione, caselle di testo ed etichette.</span><span class="sxs-lookup"><span data-stu-id="cae7d-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="cae7d-127">Per iniziare a creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="cae7d-127">To begin making the application</span></span>  
  
-   <span data-ttu-id="cae7d-128">Creare una nuova applicazione Windows in Visual Basic o l'oggetto visivo C#.</span><span class="sxs-lookup"><span data-stu-id="cae7d-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="cae7d-129">Assegnare il nome **PizzaOrder** al progetto.</span><span class="sxs-lookup"><span data-stu-id="cae7d-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="cae7d-130">Per i dettagli, vedere [Creazione di nuove soluzioni e progetti](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="cae7d-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="cae7d-131">Aggiunta dei controlli al form</span><span class="sxs-lookup"><span data-stu-id="cae7d-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="cae7d-132">Quando si aggiungono i controlli a un form, tenere presenti le linee guida seguenti per creare un'applicazione accessibile:</span><span class="sxs-lookup"><span data-stu-id="cae7d-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
-   <span data-ttu-id="cae7d-133">Impostare le proprietà <xref:System.Windows.Forms.Control.AccessibleDescription%2A> e <xref:System.Windows.Forms.Control.AccessibleName%2A>.</span><span class="sxs-lookup"><span data-stu-id="cae7d-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="cae7d-134">In questo esempio, l'impostazione predefinita per <xref:System.Windows.Forms.Control.AccessibleRole%2A> è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="cae7d-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="cae7d-135">Per altre informazioni sulle proprietà di accessibilità, vedere [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md) (Specifica di informazioni di accessibilità per i controlli in un Windows Form).</span><span class="sxs-lookup"><span data-stu-id="cae7d-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
-   <span data-ttu-id="cae7d-136">Impostare le dimensioni del carattere su 10 o più punti.</span><span class="sxs-lookup"><span data-stu-id="cae7d-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cae7d-137">Se all'inizio si impostano le dimensioni del carattere del form su 10, tutti i controlli aggiunti successivamente al form avranno dimensioni del carattere pari a 10.</span><span class="sxs-lookup"><span data-stu-id="cae7d-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
-   <span data-ttu-id="cae7d-138">Assicurarsi che tutti i controlli etichetta che descrivono un controllo TextBox precedano immediatamente il controllo TextBox nell'ordine di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="cae7d-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
-   <span data-ttu-id="cae7d-139">Aggiungere una chiave di accesso, usando il carattere "&", al <xref:System.Windows.Forms.Control.Text%2A> proprietà di qualsiasi controllo potrebbe essere necessario l'utente a cui passare.</span><span class="sxs-lookup"><span data-stu-id="cae7d-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
-   <span data-ttu-id="cae7d-140">Aggiungere una chiave di accesso, usando il carattere "&", al <xref:System.Windows.Forms.Control.Text%2A> proprietà dell'etichetta che precede un controllo che l'utente desidera spostarsi.</span><span class="sxs-lookup"><span data-stu-id="cae7d-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="cae7d-141">Impostare la proprietà <xref:System.Windows.Forms.Label.UseMnemonic%2A> delle etichette su `true`, in modo che lo stato attivo venga impostato sul controllo successivo nell'ordine di tabulazione quando l'utente preme il tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="cae7d-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
-   <span data-ttu-id="cae7d-142">Aggiungere tasti di scelta a tutte le voci di menu.</span><span class="sxs-lookup"><span data-stu-id="cae7d-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="cae7d-143">Per rendere accessibile l'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="cae7d-143">To make your Windows Application accessible</span></span>  
  
-   <span data-ttu-id="cae7d-144">Aggiungere i controlli al form e impostare le proprietà come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="cae7d-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="cae7d-145">Vedere l'immagine alla fine della tabella per un modello di come disporre i controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="cae7d-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="cae7d-146">Object</span><span class="sxs-lookup"><span data-stu-id="cae7d-146">Object</span></span>|<span data-ttu-id="cae7d-147">Proprietà</span><span class="sxs-lookup"><span data-stu-id="cae7d-147">Property</span></span>|<span data-ttu-id="cae7d-148">Value</span><span class="sxs-lookup"><span data-stu-id="cae7d-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="cae7d-149">Form1</span><span class="sxs-lookup"><span data-stu-id="cae7d-149">Form1</span></span>|<span data-ttu-id="cae7d-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-150">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-151">Order form</span><span class="sxs-lookup"><span data-stu-id="cae7d-151">Order form</span></span>|  
    ||<span data-ttu-id="cae7d-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-152">AccessibleName</span></span>|<span data-ttu-id="cae7d-153">Order form</span><span class="sxs-lookup"><span data-stu-id="cae7d-153">Order form</span></span>|  
    ||<span data-ttu-id="cae7d-154">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="cae7d-154">Font Size</span></span>|<span data-ttu-id="cae7d-155">10</span><span class="sxs-lookup"><span data-stu-id="cae7d-155">10</span></span>|  
    ||<span data-ttu-id="cae7d-156">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-156">Text</span></span>|<span data-ttu-id="cae7d-157">Pizza Order Form</span><span class="sxs-lookup"><span data-stu-id="cae7d-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="cae7d-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="cae7d-158">PictureBox</span></span>|<span data-ttu-id="cae7d-159">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-159">Name</span></span>|<span data-ttu-id="cae7d-160">logo</span><span class="sxs-lookup"><span data-stu-id="cae7d-160">logo</span></span>|  
    ||<span data-ttu-id="cae7d-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-161">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-162">A slice of pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="cae7d-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-163">AccessibleName</span></span>|<span data-ttu-id="cae7d-164">Company logo</span><span class="sxs-lookup"><span data-stu-id="cae7d-164">Company logo</span></span>|  
    ||<span data-ttu-id="cae7d-165">Image</span><span class="sxs-lookup"><span data-stu-id="cae7d-165">Image</span></span>|<span data-ttu-id="cae7d-166">Un'icona o una bitmap</span><span class="sxs-lookup"><span data-stu-id="cae7d-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="cae7d-167">Label</span><span class="sxs-lookup"><span data-stu-id="cae7d-167">Label</span></span>|<span data-ttu-id="cae7d-168">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-168">Name</span></span>|<span data-ttu-id="cae7d-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="cae7d-169">companyLabel</span></span>|  
    ||<span data-ttu-id="cae7d-170">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-170">Text</span></span>|<span data-ttu-id="cae7d-171">Good Pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="cae7d-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-172">TabIndex</span></span>|<span data-ttu-id="cae7d-173">1</span><span class="sxs-lookup"><span data-stu-id="cae7d-173">1</span></span>|  
    ||<span data-ttu-id="cae7d-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-174">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-175">Company name</span><span class="sxs-lookup"><span data-stu-id="cae7d-175">Company name</span></span>|  
    ||<span data-ttu-id="cae7d-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-176">AccessibleName</span></span>|<span data-ttu-id="cae7d-177">Company name</span><span class="sxs-lookup"><span data-stu-id="cae7d-177">Company name</span></span>|  
    ||<span data-ttu-id="cae7d-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="cae7d-178">Backcolor</span></span>|<span data-ttu-id="cae7d-179">Blu</span><span class="sxs-lookup"><span data-stu-id="cae7d-179">Blue</span></span>|  
    ||<span data-ttu-id="cae7d-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="cae7d-180">Forecolor</span></span>|<span data-ttu-id="cae7d-181">Giallo</span><span class="sxs-lookup"><span data-stu-id="cae7d-181">Yellow</span></span>|  
    ||<span data-ttu-id="cae7d-182">Dimensione carattere</span><span class="sxs-lookup"><span data-stu-id="cae7d-182">Font size</span></span>|<span data-ttu-id="cae7d-183">18</span><span class="sxs-lookup"><span data-stu-id="cae7d-183">18</span></span>|  
    |<span data-ttu-id="cae7d-184">Label</span><span class="sxs-lookup"><span data-stu-id="cae7d-184">Label</span></span>|<span data-ttu-id="cae7d-185">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-185">Name</span></span>|<span data-ttu-id="cae7d-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="cae7d-186">customerLabel</span></span>|  
    ||<span data-ttu-id="cae7d-187">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-187">Text</span></span>|<span data-ttu-id="cae7d-188">&Name</span><span class="sxs-lookup"><span data-stu-id="cae7d-188">&Name</span></span>|  
    ||<span data-ttu-id="cae7d-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-189">TabIndex</span></span>|<span data-ttu-id="cae7d-190">2</span><span class="sxs-lookup"><span data-stu-id="cae7d-190">2</span></span>|  
    ||<span data-ttu-id="cae7d-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-191">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-192">Customer name label</span><span class="sxs-lookup"><span data-stu-id="cae7d-192">Customer name label</span></span>|  
    ||<span data-ttu-id="cae7d-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-193">AccessibleName</span></span>|<span data-ttu-id="cae7d-194">Customer name label</span><span class="sxs-lookup"><span data-stu-id="cae7d-194">Customer name label</span></span>|  
    ||<span data-ttu-id="cae7d-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="cae7d-195">UseMnemonic</span></span>|<span data-ttu-id="cae7d-196">True</span><span class="sxs-lookup"><span data-stu-id="cae7d-196">True</span></span>|  
    |<span data-ttu-id="cae7d-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="cae7d-197">TextBox</span></span>|<span data-ttu-id="cae7d-198">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-198">Name</span></span>|<span data-ttu-id="cae7d-199">customerName</span><span class="sxs-lookup"><span data-stu-id="cae7d-199">customerName</span></span>|  
    ||<span data-ttu-id="cae7d-200">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-200">Text</span></span>|<span data-ttu-id="cae7d-201">(nessuno)</span><span class="sxs-lookup"><span data-stu-id="cae7d-201">(none)</span></span>|  
    ||<span data-ttu-id="cae7d-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-202">TabIndex</span></span>|<span data-ttu-id="cae7d-203">3</span><span class="sxs-lookup"><span data-stu-id="cae7d-203">3</span></span>|  
    ||<span data-ttu-id="cae7d-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-204">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-205">Customer name</span><span class="sxs-lookup"><span data-stu-id="cae7d-205">Customer name</span></span>|  
    ||<span data-ttu-id="cae7d-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-206">AccessibleName</span></span>|<span data-ttu-id="cae7d-207">Customer name</span><span class="sxs-lookup"><span data-stu-id="cae7d-207">Customer name</span></span>|  
    |<span data-ttu-id="cae7d-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="cae7d-208">GroupBox</span></span>|<span data-ttu-id="cae7d-209">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-209">Name</span></span>|<span data-ttu-id="cae7d-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="cae7d-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="cae7d-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-211">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-212">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="cae7d-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="cae7d-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-213">AccessibleName</span></span>|<span data-ttu-id="cae7d-214">Pizza size options</span><span class="sxs-lookup"><span data-stu-id="cae7d-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="cae7d-215">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-215">Text</span></span>|<span data-ttu-id="cae7d-216">Pizza size</span><span class="sxs-lookup"><span data-stu-id="cae7d-216">Pizza size</span></span>|  
    ||<span data-ttu-id="cae7d-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-217">TabIndex</span></span>|<span data-ttu-id="cae7d-218">4</span><span class="sxs-lookup"><span data-stu-id="cae7d-218">4</span></span>|  
    |<span data-ttu-id="cae7d-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="cae7d-219">RadioButton</span></span>|<span data-ttu-id="cae7d-220">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-220">Name</span></span>|<span data-ttu-id="cae7d-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-221">smallPizza</span></span>|  
    ||<span data-ttu-id="cae7d-222">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-222">Text</span></span>|<span data-ttu-id="cae7d-223">&Small $6.00</span><span class="sxs-lookup"><span data-stu-id="cae7d-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="cae7d-224">Selezionato</span><span class="sxs-lookup"><span data-stu-id="cae7d-224">Checked</span></span>|<span data-ttu-id="cae7d-225">True</span><span class="sxs-lookup"><span data-stu-id="cae7d-225">True</span></span>|  
    ||<span data-ttu-id="cae7d-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-226">TabIndex</span></span>|<span data-ttu-id="cae7d-227">0</span><span class="sxs-lookup"><span data-stu-id="cae7d-227">0</span></span>|  
    ||<span data-ttu-id="cae7d-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-228">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-229">Small pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-229">Small pizza</span></span>|  
    ||<span data-ttu-id="cae7d-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-230">AccessibleName</span></span>|<span data-ttu-id="cae7d-231">Small pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-231">Small pizza</span></span>|  
    |<span data-ttu-id="cae7d-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="cae7d-232">RadioButton</span></span>|<span data-ttu-id="cae7d-233">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-233">Name</span></span>|<span data-ttu-id="cae7d-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-234">largePizza</span></span>|  
    ||<span data-ttu-id="cae7d-235">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-235">Text</span></span>|<span data-ttu-id="cae7d-236">&Large $10.00</span><span class="sxs-lookup"><span data-stu-id="cae7d-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="cae7d-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-237">TabIndex</span></span>|<span data-ttu-id="cae7d-238">1</span><span class="sxs-lookup"><span data-stu-id="cae7d-238">1</span></span>|  
    ||<span data-ttu-id="cae7d-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-239">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-240">Large pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-240">Large pizza</span></span>|  
    ||<span data-ttu-id="cae7d-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-241">AccessibleName</span></span>|<span data-ttu-id="cae7d-242">Large pizza</span><span class="sxs-lookup"><span data-stu-id="cae7d-242">Large pizza</span></span>|  
    |<span data-ttu-id="cae7d-243">Label</span><span class="sxs-lookup"><span data-stu-id="cae7d-243">Label</span></span>|<span data-ttu-id="cae7d-244">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-244">Name</span></span>|<span data-ttu-id="cae7d-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="cae7d-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="cae7d-246">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-246">Text</span></span>|<span data-ttu-id="cae7d-247">&Toppings ($0.75 each)</span><span class="sxs-lookup"><span data-stu-id="cae7d-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="cae7d-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-248">TabIndex</span></span>|<span data-ttu-id="cae7d-249">5</span><span class="sxs-lookup"><span data-stu-id="cae7d-249">5</span></span>|  
    ||<span data-ttu-id="cae7d-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-250">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-251">Toppings label</span><span class="sxs-lookup"><span data-stu-id="cae7d-251">Toppings label</span></span>|  
    ||<span data-ttu-id="cae7d-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-252">AccessibleName</span></span>|<span data-ttu-id="cae7d-253">Toppings label</span><span class="sxs-lookup"><span data-stu-id="cae7d-253">Toppings label</span></span>|  
    ||<span data-ttu-id="cae7d-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="cae7d-254">UseMnemonic</span></span>|<span data-ttu-id="cae7d-255">True</span><span class="sxs-lookup"><span data-stu-id="cae7d-255">True</span></span>|  
    |<span data-ttu-id="cae7d-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="cae7d-256">CheckedListBox</span></span>|<span data-ttu-id="cae7d-257">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-257">Name</span></span>|<span data-ttu-id="cae7d-258">toppings</span><span class="sxs-lookup"><span data-stu-id="cae7d-258">toppings</span></span>|  
    ||<span data-ttu-id="cae7d-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-259">TabIndex</span></span>|<span data-ttu-id="cae7d-260">6</span><span class="sxs-lookup"><span data-stu-id="cae7d-260">6</span></span>|  
    ||<span data-ttu-id="cae7d-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-261">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-262">Available toppings</span><span class="sxs-lookup"><span data-stu-id="cae7d-262">Available toppings</span></span>|  
    ||<span data-ttu-id="cae7d-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-263">AccessibleName</span></span>|<span data-ttu-id="cae7d-264">Available toppings</span><span class="sxs-lookup"><span data-stu-id="cae7d-264">Available toppings</span></span>|  
    ||<span data-ttu-id="cae7d-265">Elementi</span><span class="sxs-lookup"><span data-stu-id="cae7d-265">Items</span></span>|<span data-ttu-id="cae7d-266">Pepperoni, Sausage, Mushrooms</span><span class="sxs-lookup"><span data-stu-id="cae7d-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="cae7d-267">Button</span><span class="sxs-lookup"><span data-stu-id="cae7d-267">Button</span></span>|<span data-ttu-id="cae7d-268">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-268">Name</span></span>|<span data-ttu-id="cae7d-269">order</span><span class="sxs-lookup"><span data-stu-id="cae7d-269">order</span></span>|  
    ||<span data-ttu-id="cae7d-270">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-270">Text</span></span>|<span data-ttu-id="cae7d-271">&Ordina</span><span class="sxs-lookup"><span data-stu-id="cae7d-271">&Order</span></span>|  
    ||<span data-ttu-id="cae7d-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-272">TabIndex</span></span>|<span data-ttu-id="cae7d-273">7</span><span class="sxs-lookup"><span data-stu-id="cae7d-273">7</span></span>|  
    ||<span data-ttu-id="cae7d-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-274">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-275">Total the order</span><span class="sxs-lookup"><span data-stu-id="cae7d-275">Total the order</span></span>|  
    ||<span data-ttu-id="cae7d-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-276">AccessibleName</span></span>|<span data-ttu-id="cae7d-277">Total order</span><span class="sxs-lookup"><span data-stu-id="cae7d-277">Total order</span></span>|  
    |<span data-ttu-id="cae7d-278">Button</span><span class="sxs-lookup"><span data-stu-id="cae7d-278">Button</span></span>|<span data-ttu-id="cae7d-279">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-279">Name</span></span>|<span data-ttu-id="cae7d-280">cancel</span><span class="sxs-lookup"><span data-stu-id="cae7d-280">cancel</span></span>|  
    ||<span data-ttu-id="cae7d-281">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-281">Text</span></span>|<span data-ttu-id="cae7d-282">An&nulla</span><span class="sxs-lookup"><span data-stu-id="cae7d-282">&Cancel</span></span>|  
    ||<span data-ttu-id="cae7d-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="cae7d-283">TabIndex</span></span>|<span data-ttu-id="cae7d-284">8</span><span class="sxs-lookup"><span data-stu-id="cae7d-284">8</span></span>|  
    ||<span data-ttu-id="cae7d-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="cae7d-285">AccessibleDescription</span></span>|<span data-ttu-id="cae7d-286">Cancel the order</span><span class="sxs-lookup"><span data-stu-id="cae7d-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="cae7d-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="cae7d-287">AccessibleName</span></span>|<span data-ttu-id="cae7d-288">Cancel order</span><span class="sxs-lookup"><span data-stu-id="cae7d-288">Cancel order</span></span>|  
    |<span data-ttu-id="cae7d-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="cae7d-289">MainMenu</span></span>|<span data-ttu-id="cae7d-290">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-290">Name</span></span>|<span data-ttu-id="cae7d-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="cae7d-291">theMainMenu</span></span>|  
    |<span data-ttu-id="cae7d-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="cae7d-292">MenuItem</span></span>|<span data-ttu-id="cae7d-293">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-293">Name</span></span>|<span data-ttu-id="cae7d-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="cae7d-294">fileCommands</span></span>|  
    ||<span data-ttu-id="cae7d-295">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-295">Text</span></span>|<span data-ttu-id="cae7d-296">&File</span><span class="sxs-lookup"><span data-stu-id="cae7d-296">&File</span></span>|  
    |<span data-ttu-id="cae7d-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="cae7d-297">MenuItem</span></span>|<span data-ttu-id="cae7d-298">Nome</span><span class="sxs-lookup"><span data-stu-id="cae7d-298">Name</span></span>|<span data-ttu-id="cae7d-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="cae7d-299">exitApp</span></span>|  
    ||<span data-ttu-id="cae7d-300">Testo</span><span class="sxs-lookup"><span data-stu-id="cae7d-300">Text</span></span>|<span data-ttu-id="cae7d-301">&Esci</span><span class="sxs-lookup"><span data-stu-id="cae7d-301">E&xit</span></span>|
    
      <span data-ttu-id="cae7d-302">Il modulo avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cae7d-302">Your form will look something like the following image:</span></span>
    
      ![Il modulo d'ordine pizza con una selezione nella casella di testo, dimensioni e condimenti nome.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)  

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="cae7d-304">Supporto della modalità contrasto elevato</span><span class="sxs-lookup"><span data-stu-id="cae7d-304">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="cae7d-305">La modalità contrasto elevato è un'impostazione di sistema di Windows che migliora la leggibilità usando colori a contrasto e dimensioni del carattere che agevolano gli utenti con problemi di vista.</span><span class="sxs-lookup"><span data-stu-id="cae7d-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="cae7d-306">Il <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> proprietà viene fornita per determinare se è impostata la modalità contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="cae7d-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="cae7d-307">Se SystemInformation.HighContrast è `true`, l'applicazione dovrebbe:</span><span class="sxs-lookup"><span data-stu-id="cae7d-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
-   <span data-ttu-id="cae7d-308">Visualizzare tutti gli elementi dell'interfaccia utente con la combinazione colori di sistema.</span><span class="sxs-lookup"><span data-stu-id="cae7d-308">Display all user interface elements using the system color scheme</span></span>  
  
-   <span data-ttu-id="cae7d-309">Comunicare tramite segnali visivi o acustici tutte le informazioni comunicate mediante il colore.</span><span class="sxs-lookup"><span data-stu-id="cae7d-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="cae7d-310">Ad esempio, se determinati elementi elenco vengono evidenziati usando un tipo di carattere rosso, è possibile aggiungere al tipo di carattere anche il grassetto, in modo che l'utente veda un segnale non basato sul colore, indicante che gli elementi sono evidenziati.</span><span class="sxs-lookup"><span data-stu-id="cae7d-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
-   <span data-ttu-id="cae7d-311">Evitare di inserire immagini o motivi dietro il testo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-311">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="cae7d-312">All'avvio l'applicazione dovrebbe controllare l'impostazione di <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> e rispondere all'evento di sistema <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="cae7d-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="cae7d-313">L'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> viene generato ogni volta che il valore di <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> cambia.</span><span class="sxs-lookup"><span data-stu-id="cae7d-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="cae7d-314">Nell'applicazione l'unico elemento che non usa le impostazioni di sistema per il colore è `lblCompanyName`.</span><span class="sxs-lookup"><span data-stu-id="cae7d-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="cae7d-315">Il <xref:System.Drawing.SystemColors> classe viene utilizzata per modificare le impostazioni colore dell'etichetta con i colori di sistema selezionati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cae7d-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="cae7d-316">Per abilitare la modalità contrasto elevato in modo efficace</span><span class="sxs-lookup"><span data-stu-id="cae7d-316">To enable High Contrast mode in an effective way</span></span>  
  
1.  <span data-ttu-id="cae7d-317">Creare un metodo per impostare i colori dell'etichetta sui colori di sistema.</span><span class="sxs-lookup"><span data-stu-id="cae7d-317">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="cae7d-318">Chiamare la routine `SetColorScheme`nel costruttore del form (`Public Sub New()` in Visual Basic e `public class Form1` in Visual C#).</span><span class="sxs-lookup"><span data-stu-id="cae7d-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="cae7d-319">Per accedere al costruttore in Visual Basic, sarà necessario espandere l'area con l'etichetta **Codice generato da Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="cae7d-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3.  <span data-ttu-id="cae7d-320">Creare una routine evento, con la firma appropriata, per rispondere all'evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="cae7d-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4.  <span data-ttu-id="cae7d-321">Aggiungere il codice al costruttore del form, dopo la chiamata a `InitializeComponents`, per associare la routine evento all'evento di sistema.</span><span class="sxs-lookup"><span data-stu-id="cae7d-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="cae7d-322">Questo metodo chiama la routine `SetColorScheme`.</span><span class="sxs-lookup"><span data-stu-id="cae7d-322">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5.  <span data-ttu-id="cae7d-323">Aggiungere il codice al metodo <xref:System.Windows.Forms.Control.Dispose%2A> del form, prima della chiamata al metodo <xref:System.Windows.Forms.Control.Dispose%2A> della classe base, per rilasciare l'evento quando l'applicazione si chiude.</span><span class="sxs-lookup"><span data-stu-id="cae7d-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="cae7d-324">Per accedere al metodo <xref:System.Windows.Forms.Control.Dispose%2A> in Visual Basic, sarà necessario espandere l'area con l'etichetta Codice generato da Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cae7d-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cae7d-325">Il codice dell'evento di sistema esegue un thread separato dall'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="cae7d-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="cae7d-326">Se non si rilascia l'evento, il codice associato all'evento verrà eseguito anche dopo la chiusura del programma.</span><span class="sxs-lookup"><span data-stu-id="cae7d-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6.  <span data-ttu-id="cae7d-327">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cae7d-327">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="cae7d-328">Comunicazione di informazioni importanti con mezzi diversi dai segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="cae7d-328">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="cae7d-329">In questa applicazione, nessuna informazione viene comunicata solo mediante segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="cae7d-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="cae7d-330">Se si usano i segnagli acustici nell'applicazione, è necessario comunicare le informazioni anche con altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="cae7d-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="cae7d-331">Per fornire informazioni con mezzi diversi dai segnali acustici</span><span class="sxs-lookup"><span data-stu-id="cae7d-331">To supply information by some other means than sound</span></span>  
  
1.  <span data-ttu-id="cae7d-332">Far lampeggiare la barra del titolo usando la funzione FlashWindow dell'API Windows.</span><span class="sxs-lookup"><span data-stu-id="cae7d-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="cae7d-333">Per un esempio di come chiamare funzioni API Windows, vedere [procedura dettagliata: Chiamata delle API di Windows](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="cae7d-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cae7d-334">L'utente potrebbe aver abilitato il servizio Segnali visivi di Windows, che farà lampeggiare la finestra anche quando i suoni di sistema vengono riprodotti tramite l'altoparlante predefinito del computer.</span><span class="sxs-lookup"><span data-stu-id="cae7d-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2.  <span data-ttu-id="cae7d-335">Visualizzare le informazioni importanti in una finestra non modale in modo che l'utente rispondere a esse.</span><span class="sxs-lookup"><span data-stu-id="cae7d-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3.  <span data-ttu-id="cae7d-336">Visualizzare una finestra di messaggio che acquisisce lo stato attivo della tastiera.</span><span class="sxs-lookup"><span data-stu-id="cae7d-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="cae7d-337">Evitare questo metodo se è possibile che l'utente stia digitando.</span><span class="sxs-lookup"><span data-stu-id="cae7d-337">Avoid this method when the user may be typing.</span></span>  
  
4.  <span data-ttu-id="cae7d-338">Visualizzare un indicatore di stato nell'area di notifica dello stato della barra delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cae7d-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="cae7d-339">Per i dettagli, vedere [Aggiunta di icone alla barra delle applicazioni mediante il componente NotifyIcon di Windows Form](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="cae7d-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="cae7d-340">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="cae7d-340">Testing the Application</span></span>  
 <span data-ttu-id="cae7d-341">Prima di distribuire l'applicazione, è consigliabile testare le funzionalità di accessibilità implementate.</span><span class="sxs-lookup"><span data-stu-id="cae7d-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="cae7d-342">Per testare le funzionalità di accessibilità</span><span class="sxs-lookup"><span data-stu-id="cae7d-342">To test accessibility features</span></span>  
  
1.  <span data-ttu-id="cae7d-343">Per testare l'accesso tramite tastiera, scollegare il mouse ed esplorare l'interfaccia utente per ogni funzionalità solo con la tastiera.</span><span class="sxs-lookup"><span data-stu-id="cae7d-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="cae7d-344">Assicurarsi che tutte le attività possano essere eseguite solo con la tastiera.</span><span class="sxs-lookup"><span data-stu-id="cae7d-344">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2.  <span data-ttu-id="cae7d-345">Per testare il supporto del contrasto elevato, scegliere l'icona Accesso facilitato nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="cae7d-346">Fare clic sulla scheda Schermo e selezionare la casella di controllo Usa Contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="cae7d-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="cae7d-347">Spostarsi tra tutti gli elementi dell'interfaccia utente per verificare che siano state applicate le modifiche al colore e al tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="cae7d-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="cae7d-348">Assicurarsi anche non siano state inserite immagini o motivi dietro il testo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cae7d-349">Windows NT 4 non dispone dell'icona Accesso facilitato nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="cae7d-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="cae7d-350">Quindi questa procedura per cambiare l'impostazione SystemInformation.HighContrast non funziona in Windows NT 4.</span><span class="sxs-lookup"><span data-stu-id="cae7d-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3.  <span data-ttu-id="cae7d-351">Per testare l'accessibilità di un'applicazione, sono facilmente disponibili altri strumenti.</span><span class="sxs-lookup"><span data-stu-id="cae7d-351">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4.  <span data-ttu-id="cae7d-352">Per testare l'esposizione dello stato attivo della tastiera, eseguire Lente di ingrandimento.</span><span class="sxs-lookup"><span data-stu-id="cae7d-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="cae7d-353">Per aprirla, fare clic sul menu **Start**, scegliere **Programmi**, **Accessori**, **Accessibilità**, quindi fare clic su **Lente di ingrandimento**.</span><span class="sxs-lookup"><span data-stu-id="cae7d-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="cae7d-354">Spostarsi nell'interfaccia utente usando sia il mouse che il tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="cae7d-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="cae7d-355">Assicurarsi che tutti gli spostamenti vengano registrati correttamente in **Lente di ingrandimento**.</span><span class="sxs-lookup"><span data-stu-id="cae7d-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5.  <span data-ttu-id="cae7d-356">Per testare l'esposizione degli elementi dello schermo, eseguire Controlla e usare sia il mouse che il tasto TAB per raggiungere ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="cae7d-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="cae7d-357">Assicurarsi che le informazioni presentate nei campi Nome, Stato, Ruolo, Posizione e Valore della finestra Controlla abbiano senso per l'utente per ogni oggetto dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cae7d-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
