---
title: 'Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 938f1210eaa3479822e752327123737a3286fe9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624051"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a>Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms
Per impostazione predefinita, un <xref:System.Windows.Forms.TabControl> controllo contiene due <xref:System.Windows.Forms.TabPage> controlli. È possibile accedere a queste schede tramite il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
### <a name="to-add-a-tab-programmatically"></a>Per aggiungere una scheda a livello di codice  
  
- Usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a>Per rimuovere una scheda a livello di codice  
  
- Per rimuovere le schede selezionate, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
     -oppure-  
  
- Per rimuovere tutte le schede, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo TabControl](tabcontrol-control-overview-windows-forms.md)
- [Procedura: Aggiungere un controllo a un oggetto TabPage](how-to-add-a-control-to-a-tab-page.md)
- [Procedura: Disabilitare le schede](how-to-disable-tab-pages.md)
- [Procedura: Modificare l'aspetto del controllo TabControl Windows Form](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
