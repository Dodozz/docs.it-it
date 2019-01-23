---
title: 'Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 4e02fec0a131523059f88d4f12f62398d80fddf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632049"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="e62eb-102">Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form</span><span class="sxs-lookup"><span data-stu-id="e62eb-102">How to: Create Event Handlers at Run Time for Windows Forms</span></span>
<span data-ttu-id="e62eb-103">Oltre a creare gli eventi usando Progettazione Windows Form, è anche possibile creare un gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e62eb-103">In addition to creating events using the Windows Forms Designer, you can also create an event handler at run time.</span></span> <span data-ttu-id="e62eb-104">Questa azione consente di connettere i gestori eventi in base alle condizioni nel codice in fase di esecuzione invece di connetterli all'avvio iniziale del programma.</span><span class="sxs-lookup"><span data-stu-id="e62eb-104">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>  
  
### <a name="to-create-an-event-handler-at-run-time"></a><span data-ttu-id="e62eb-105">Per creare un gestore eventi in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e62eb-105">To create an event handler at run time</span></span>  
  
1.  <span data-ttu-id="e62eb-106">Aprire il form nell'editor di codice in cui si desidera aggiungere un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e62eb-106">Open the form in the Code Editor that you want to add an event handler to.</span></span>  
  
2.  <span data-ttu-id="e62eb-107">Aggiungere un metodo al modulo con la firma del metodo per l'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="e62eb-107">Add a method to your form with the method signature for the event that you want to handle.</span></span>  
  
     <span data-ttu-id="e62eb-108">Ad esempio, se si sta gestendo il <xref:System.Windows.Forms.Control.Click> eventi di un <xref:System.Windows.Forms.Button> (controllo), creare un metodo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e62eb-108">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  <span data-ttu-id="e62eb-109">Aggiungere un codice al gestore dell'evento appropriato per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e62eb-109">Add code to the event handler as appropriate to your application.</span></span>  
  
4.  <span data-ttu-id="e62eb-110">Stabilire per quale modulo o controllo si desidera creare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e62eb-110">Determine which form or control you want to create an event handler for.</span></span>  
  
5.  <span data-ttu-id="e62eb-111">In un metodo nella classe del modulo, aggiungere il codice che specifica il gestore eventi per gestire l'evento.</span><span class="sxs-lookup"><span data-stu-id="e62eb-111">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="e62eb-112">Ad esempio, il codice seguente specifica il gestore eventi `button1_Click` gestisce il <xref:System.Windows.Forms.Control.Click> eventi di un <xref:System.Windows.Forms.Button> controllo:</span><span class="sxs-lookup"><span data-stu-id="e62eb-112">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="e62eb-113">Il <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> metodo illustrato nel codice Visual Basic precedente stabilisce un evento Click del pulsante.</span><span class="sxs-lookup"><span data-stu-id="e62eb-113">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62eb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e62eb-114">See also</span></span>
- [<span data-ttu-id="e62eb-115">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e62eb-115">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="e62eb-116">Informazioni generali sui gestori eventi</span><span class="sxs-lookup"><span data-stu-id="e62eb-116">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="e62eb-117">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e62eb-117">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
