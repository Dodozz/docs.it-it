---
title: 'Procedura: Determinare gli elementi selezionati nel controllo CheckedListBox Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 2936a64338f47107b11b5f6eb85c5e94707bf926
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707963"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Procedura: Determinare gli elementi selezionati nel controllo CheckedListBox Windows Form
Quando la presentazione dei dati in un controllo Windows Form <xref:System.Windows.Forms.CheckedListBox> (controllo), è possibile scorrere la raccolta archiviata nel <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> proprietà o esaminare l'elenco utilizzando il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo per determinare quali elementi vengono controllati. Il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo accetta un numero di indice di elemento come argomento e restituisce `true` o `false`. Contrariamente a quanto si potrebbe pensare, la <xref:System.Windows.Forms.ListBox.SelectedItems%2A> e <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> proprietà non determinano quali elementi sono selezionati; esse determinano a quali elementi vengono evidenziati.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Per determinare gli elementi selezionati in un controllo CheckedListBox  
  
1.  Eseguire l'iterazione attraverso la <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> insieme, partendo da 0, poiché la raccolta è in base zero. Si noti che questo metodo fornirà il numero di elementi nell'elenco di elementi controllati, non nell'intero elenco. Pertanto in se il primo elemento nell'elenco non è selezionato e la seconda voce è selezionata, il codice seguente viene visualizzato testo, ad esempio "elemento selezionato 1 = MyListItem2".  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - oppure -  
  
2.  Esaminare i <xref:System.Windows.Forms.CheckedListBox.Items%2A> insieme, partendo da 0, poiché è in base zero, la raccolta e chiamare il <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> metodo per ogni elemento. Si noti che questo metodo verrà visualizzato il numero di elementi nell'elenco globale, in modo che se il primo elemento nell'elenco non viene controllato e la seconda voce è selezionata, verrà visualizzato un testo, ad esempio "l'elemento 2 = MyListItem2".  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a>Vedere anche
- [Controlli Windows Form usati per elencare opzioni](windows-forms-controls-used-to-list-options.md)
