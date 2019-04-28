---
title: 'Procedura: Gestire eventi di input utente nei controlli Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: 5dc1997dffc53632ce8b36bc5fe89e768871fd0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802423"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="4b1f3-102">Procedura: Gestire eventi di input utente nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b1f3-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="4b1f3-103">In questo esempio viene illustrato come gestire la maggior parte degli eventi di convalida, stato attivo, mouse e tastiera che possono verificarsi in un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="4b1f3-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="4b1f3-104">La casella di testo denominata `TextBoxInput` riceve gli eventi quando è attiva e le informazioni relative a ogni evento vengono scritte nella casella di testo denominata `TextBoxOutput` nell'ordine di generazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="4b1f3-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="4b1f3-105">L'applicazione include anche un set di caselle di controllo che possono essere usate per filtrare gli eventi da segnalare.</span><span class="sxs-lookup"><span data-stu-id="4b1f3-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b1f3-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b1f3-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b1f3-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4b1f3-107">Compiling the Code</span></span>  
 <span data-ttu-id="4b1f3-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b1f3-108">This example requires:</span></span>  
  
- <span data-ttu-id="4b1f3-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4b1f3-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4b1f3-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4b1f3-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4b1f3-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="4b1f3-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b1f3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b1f3-112">See also</span></span>

- [<span data-ttu-id="4b1f3-113">Input dell'utente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b1f3-113">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
