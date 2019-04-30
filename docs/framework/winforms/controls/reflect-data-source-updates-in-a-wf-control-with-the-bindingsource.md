---
title: "Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Forms con BindingSource"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: 16dbe4da1efecd120d4da4d66c3d79ec907b92a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947992"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="638ae-102">Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="638ae-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="638ae-103">Quando si usano controlli associati a dati, in alcuni casi è necessario rispondere alle modifiche che si sono verificate nell'origine dati, nel caso in cui quest'ultima non preveda la generazione di eventi di modifica degli elenchi.</span><span class="sxs-lookup"><span data-stu-id="638ae-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="638ae-104">Quando si usa il componente <xref:System.Windows.Forms.BindingSource> per associare l'origine dati a un controllo Windows Form, è possibile inviare al controllo la notifica di modifica dell'origine dati chiamando il metodo <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="638ae-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="638ae-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="638ae-105">Example</span></span>  
 <span data-ttu-id="638ae-106">Nell'esempio di codice riportato di seguito viene illustrato l'uso del metodo <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> per notificare a un controllo associato che l'origine dati è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="638ae-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="638ae-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="638ae-107">Compiling the Code</span></span>  
 <span data-ttu-id="638ae-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="638ae-108">This example requires:</span></span>  
  
- <span data-ttu-id="638ae-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="638ae-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="638ae-110">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="638ae-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="638ae-111">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="638ae-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638ae-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="638ae-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="638ae-113">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="638ae-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="638ae-114">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="638ae-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
