---
title: 'Procedura: Designare un pulsante di Windows Form come pulsante Annulla'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 74d025677682735fc7f1c68116b2364887f0519c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701469"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="91c8d-102">Procedura: Designare un pulsante di Windows Form come pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="91c8d-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="91c8d-103">In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento.</span><span class="sxs-lookup"><span data-stu-id="91c8d-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="91c8d-104">Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo sul form ha lo stato attivo, viene scelto un pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="91c8d-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="91c8d-105">Il pulsante di annullamento viene in genere programmate per consentire all'utente di abbandonare un'operazione senza il commit di alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="91c8d-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="91c8d-106">Per designare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="91c8d-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="91c8d-107">Impostare la maschera <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà appropriata <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="91c8d-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="91c8d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91c8d-108">See also</span></span>
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="91c8d-109">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="91c8d-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="91c8d-110">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="91c8d-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="91c8d-111">Procedura: Rispondere alle selezioni dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="91c8d-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="91c8d-112">Procedura: Designare un pulsante di Windows Form come pulsante di conferma</span><span class="sxs-lookup"><span data-stu-id="91c8d-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="91c8d-113">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="91c8d-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
