---
title: 'Procedura: Selezionare testo nel controllo TextBox di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 3bb1245cd47084935d632ff345a32058db6074e1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59321712"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="9737d-102">Procedura: Selezionare testo nel controllo TextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9737d-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="9737d-103">È possibile selezionare il testo a livello di codice nei moduli di Windows <xref:System.Windows.Forms.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="9737d-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="9737d-104">Ad esempio, se si crea una funzione che cerca il testo per una determinata stringa, è possibile selezionare il testo da mostrare all'utente il lettore della posizione della stringa trovata.</span><span class="sxs-lookup"><span data-stu-id="9737d-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="9737d-105">Per selezionare il testo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="9737d-105">To select text programmatically</span></span>  
  
1. <span data-ttu-id="9737d-106">Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà all'inizio del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="9737d-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="9737d-107">Il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è un numero che indica il punto di inserimento all'interno della stringa di testo, con 0 la posizione più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="9737d-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="9737d-108">Se il <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è impostata su un valore uguale o maggiore del numero di caratteri nella casella di testo, il punto di inserimento viene posizionato dopo l'ultimo carattere.</span><span class="sxs-lookup"><span data-stu-id="9737d-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="9737d-109">Impostare il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà per la lunghezza del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="9737d-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="9737d-110">Il <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà è un valore numerico che imposta la larghezza del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="9737d-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="9737d-111">L'impostazione di <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> su un numero maggiore di 0 fa sì che tale numero di caratteri da selezionare, a partire dal punto di inserimento corrente.</span><span class="sxs-lookup"><span data-stu-id="9737d-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="9737d-112">(Facoltativo) Accedere al testo selezionato tramite i <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9737d-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="9737d-113">Il codice seguente consente di selezionare il contenuto del testo di una finestra quando il controllo <xref:System.Windows.Forms.Control.Enter> evento si verifica.</span><span class="sxs-lookup"><span data-stu-id="9737d-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="9737d-114">In questo esempio controlla se la casella di testo ha un valore per il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà non `null` o una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="9737d-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="9737d-115">Quando la casella di testo riceve lo stato attivo, viene selezionato il testo corrente nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="9737d-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="9737d-116">Il `TextBox1_Enter` gestore dell'evento deve essere associato al controllo; per altre informazioni, vedere [come: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9737d-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="9737d-117">Per testare questo esempio, premere il tasto Tab fino a quando la casella di testo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="9737d-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="9737d-118">Se si fa clic nella casella di testo, il testo è deselezionato.</span><span class="sxs-lookup"><span data-stu-id="9737d-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9737d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9737d-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="9737d-120">Panoramica del controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="9737d-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="9737d-121">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9737d-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="9737d-122">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9737d-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="9737d-123">Procedura: Creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="9737d-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="9737d-124">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="9737d-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="9737d-125">Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9737d-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="9737d-126">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="9737d-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
