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
ms.openlocfilehash: 723e05803b1f7d2bc56476248987085dbe5e23f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011112"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="98432-102">Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98432-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="98432-103">Per impostazione predefinita, un <xref:System.Windows.Forms.TabControl> controllo contiene due <xref:System.Windows.Forms.TabPage> controlli.</span><span class="sxs-lookup"><span data-stu-id="98432-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="98432-104">È possibile accedere a queste schede tramite il <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="98432-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="98432-105">Per aggiungere una scheda a livello di codice</span><span class="sxs-lookup"><span data-stu-id="98432-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="98432-106">Usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="98432-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="98432-107">Per rimuovere una scheda a livello di codice</span><span class="sxs-lookup"><span data-stu-id="98432-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="98432-108">Per rimuovere le schede selezionate, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="98432-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="98432-109">-oppure-</span><span class="sxs-lookup"><span data-stu-id="98432-109">-or-</span></span>  
  
- <span data-ttu-id="98432-110">Per rimuovere tutte le schede, usare il <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> metodo di <xref:System.Windows.Forms.TabControl.TabPages%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="98432-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98432-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98432-111">See also</span></span>

- [<span data-ttu-id="98432-112">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="98432-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="98432-113">Procedura: Aggiungere un controllo a un oggetto TabPage</span><span class="sxs-lookup"><span data-stu-id="98432-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="98432-114">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="98432-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="98432-115">Procedura: Modificare l'aspetto del controllo TabControl Windows Form</span><span class="sxs-lookup"><span data-stu-id="98432-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
