---
title: 'Procedura: Condividere dati associati tra form tramite il componente BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 6631fb4c4483853b3c4ba6c2e3484654c4f83342
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260842"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="2b1d8-102">Procedura: Condividere dati associati tra form tramite il componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="2b1d8-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="2b1d8-103">È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="2b1d8-104">Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="2b1d8-105">L'esempio illustra questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b1d8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b1d8-106">Example</span></span>  
 <span data-ttu-id="2b1d8-107">L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="2b1d8-108">In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="2b1d8-109">Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b1d8-110">Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati</span><span class="sxs-lookup"><span data-stu-id="2b1d8-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="2b1d8-111">Per altre informazioni sui motivi per cui questa operazione viene eseguita, vedere [come: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="2b1d8-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b1d8-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2b1d8-112">Compiling the Code</span></span>  
 <span data-ttu-id="2b1d8-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b1d8-113">This example requires:</span></span>  
  
-   <span data-ttu-id="2b1d8-114">Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="2b1d8-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2b1d8-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2b1d8-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="2b1d8-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1d8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1d8-117">See also</span></span>
- [<span data-ttu-id="2b1d8-118">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="2b1d8-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="2b1d8-119">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="2b1d8-119">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="2b1d8-120">Procedura: Gestire errori ed eccezioni che si verificano con il Data Binding</span><span class="sxs-lookup"><span data-stu-id="2b1d8-120">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
