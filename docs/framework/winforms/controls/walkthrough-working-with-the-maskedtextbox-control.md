---
title: 'Procedura dettagliata: Utilizzo del controllo MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: 9633f2f871d08b70d6286f510a9ba5cac78ae529
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703080"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Procedura dettagliata: Utilizzo del controllo MaskedTextBox
Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   L'inizializzazione di <xref:System.Windows.Forms.MaskedTextBox> controllo  
  
-   Uso di <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> gestore eventi per avvisare l'utente quando un carattere non corrisponde alla maschera  
  
-   Assegnazione di un tipo per il <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà e usando il <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> gestore eventi per avvisare l'utente quando il valore si sta tentando di eseguire il commit non è valido per il tipo  
  
## <a name="creating-the-project-and-adding-a-control"></a>Creazione del progetto e aggiungendo un controllo  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>Per aggiungere un controllo MaskedTextBox al form  
  
1.  Aprire il form in cui si desidera posizionare la <xref:System.Windows.Forms.MaskedTextBox> controllo.  
  
2.  Trascinare un <xref:System.Windows.Forms.MaskedTextBox> controllare dal **casella degli strumenti** al form.  
  
3.  Il pulsante destro del controllo e scegliere **proprietà**. Nel **delle proprietà** finestra, seleziona la **maschera** proprietà e fare clic sul **...**  pulsante (puntini di sospensione) accanto al nome della proprietà.  
  
4.  Nel **maschera di Input** finestra di dialogo, seleziona la **data breve** mask e fare clic su **OK**.  
  
5.  Nel **delle proprietà** set finestra la <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> proprietà `true`. Questa proprietà fa sì che un breve segnale acustico ogni volta che l'utente prova a un carattere che viola la definizione della maschera di input.  
  
 Per un riepilogo dei caratteri che supporta la proprietà Mask, vedere la sezione Osservazioni del <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.  
  
## <a name="alert-the-user-to-input-errors"></a>Avvisare l'utente per gli errori di Input  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Aggiungere una descrizione comandi per l'input mask rifiutati  
  
1.  Tornare al **casella degli strumenti** e aggiungere un <xref:System.Windows.Forms.ToolTip> al form.  
  
2.  Creare un gestore eventi per il <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> evento che genera il <xref:System.Windows.Forms.ToolTip> quando si verifica un errore di input. Il fumetto suggerimento rimane visibile per cinque secondi o fino a quando non viene selezionato dall'utente.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Avvisare l'utente a un tipo che non è valido  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Aggiungere una descrizione comandi per tipi di dati non valido  
  
1.  Il modulo <xref:System.Windows.Forms.Form.Load> gestore eventi, assegnare un <xref:System.Type> oggetto che rappresenta il <xref:System.DateTime> digitare per il <xref:System.Windows.Forms.MaskedTextBox> del controllo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  Aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.MaskedTextBox>
- [Controllo MaskedTextBox](maskedtextbox-control-windows-forms.md)
