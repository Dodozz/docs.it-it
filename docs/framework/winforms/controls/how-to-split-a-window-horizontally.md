---
title: 'Procedura: Suddividere una finestra orizzontalmente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: e11e1d6730c6c8c9c0a1ac170aeb5393bf3153b7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708041"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="5d178-102">Procedura: Suddividere una finestra orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="5d178-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="5d178-103">Esempio di codice seguente effettua il divisore che divide il <xref:System.Windows.Forms.SplitContainer> controllo orizzontale.</span><span class="sxs-lookup"><span data-stu-id="5d178-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d178-104">Il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo determina la direzione della barra di divisione, non del controllo stesso.</span><span class="sxs-lookup"><span data-stu-id="5d178-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="5d178-105">Per suddividere una finestra orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="5d178-105">To split a window horizontally</span></span>  
  
1.  <span data-ttu-id="5d178-106">All'interno di una procedura, impostare il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo <xref:System.Windows.Forms.Orientation.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="5d178-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5d178-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d178-107">See also</span></span>
- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="5d178-108">Controllo SplitContainer</span><span class="sxs-lookup"><span data-stu-id="5d178-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
