---
title: 'Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: 9487d4f82878ffefe17c576b16f654293ef01106
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316505"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="b500d-102">Procedura: Visualizzare le icone di errore per la convalida dei moduli con il componente ErrorProvider di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b500d-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="b500d-103">È possibile usare un controllo Windows Form <xref:System.Windows.Forms.ErrorProvider> componente per visualizzare un'icona di errore quando l'utente immette i dati non validi.</span><span class="sxs-lookup"><span data-stu-id="b500d-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="b500d-104">È necessario disporre almeno due controlli sul form per scheda tra di essi e quindi richiamare il codice di convalida.</span><span class="sxs-lookup"><span data-stu-id="b500d-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="b500d-105">Per visualizzare un'icona di errore quando il valore di un controllo è valido</span><span class="sxs-lookup"><span data-stu-id="b500d-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="b500d-106">Aggiungere due controlli, ad esempio, le caselle di testo, ovvero a un modulo di Windows.</span><span class="sxs-lookup"><span data-stu-id="b500d-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="b500d-107">Aggiungere un <xref:System.Windows.Forms.ErrorProvider> componente al form.</span><span class="sxs-lookup"><span data-stu-id="b500d-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="b500d-108">Selezionare il primo controllo e aggiungere codice al relativo <xref:System.Windows.Forms.Control.Validating> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b500d-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="b500d-109">Affinché il codice funzioni correttamente, la routine deve essere collegata all'evento.</span><span class="sxs-lookup"><span data-stu-id="b500d-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="b500d-110">Per altre informazioni, vedere [Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b500d-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="b500d-111">Il codice seguente verifica la validità dei dati che immessi dall'utente; Se i dati non sono validi, il <xref:System.Windows.Forms.ErrorProvider.SetError%2A> viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="b500d-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="b500d-112">Il primo argomento del <xref:System.Windows.Forms.ErrorProvider.SetError%2A> metodo specifica che il controllo viene visualizzata l'icona accanto a.</span><span class="sxs-lookup"><span data-stu-id="b500d-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="b500d-113">Il secondo argomento è il testo di errore da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b500d-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="b500d-114">(Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b500d-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="b500d-115">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="b500d-115">Run the project.</span></span> <span data-ttu-id="b500d-116">Digitare i dati non validi (in questo esempio, non numerico) nel primo controllo e quindi passare al secondo.</span><span class="sxs-lookup"><span data-stu-id="b500d-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="b500d-117">Quando viene visualizzata l'icona di errore, posizionare il puntatore del mouse per visualizzare il testo dell'errore.</span><span class="sxs-lookup"><span data-stu-id="b500d-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b500d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b500d-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="b500d-119">Panoramica sul componente ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="b500d-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="b500d-120">Procedura: Visualizzare gli errori all'interno di un set di dati con il componente ErrorProvider di Windows Form</span><span class="sxs-lookup"><span data-stu-id="b500d-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
