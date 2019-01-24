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
ms.openlocfilehash: 6bd2c0aca7e24ed903e31f1c27e7e173ade6086b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619954"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="70e80-102">Procedura: Condividere dati associati tra form tramite il componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="70e80-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="70e80-103">È possibile condividere facilmente i dati tra i form con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="70e80-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="70e80-104">Ad esempio, è possibile visualizzare un form di sola lettura che riepiloga i dati dell'origine dati e un altro form modificabile che contiene informazioni dettagliate sull'elemento attualmente selezionato nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="70e80-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="70e80-105">L'esempio illustra questo scenario.</span><span class="sxs-lookup"><span data-stu-id="70e80-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e80-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="70e80-106">Example</span></span>  
 <span data-ttu-id="70e80-107">L'esempio di codice seguente illustra come condividere un oggetto <xref:System.Windows.Forms.BindingSource> e i dati associati tra i form.</span><span class="sxs-lookup"><span data-stu-id="70e80-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="70e80-108">In questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> condiviso viene passato al costruttore del form figlio.</span><span class="sxs-lookup"><span data-stu-id="70e80-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="70e80-109">Il form figlio consente all'utente di modificare i dati per l'elemento attualmente selezionato nel form principale.</span><span class="sxs-lookup"><span data-stu-id="70e80-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70e80-110">Nell'esempio viene gestito l'evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> per essere certi che i due form rimangano sincronizzati</span><span class="sxs-lookup"><span data-stu-id="70e80-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="70e80-111">Per altre informazioni sui motivi per cui questa operazione viene eseguita, vedere [come: Verificare che più controlli associati alla stessa origine dati rimangano sincronizzati](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span><span class="sxs-lookup"><span data-stu-id="70e80-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70e80-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="70e80-112">Compiling the Code</span></span>  
 <span data-ttu-id="70e80-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="70e80-113">This example requires:</span></span>  
  
-   <span data-ttu-id="70e80-114">Riferimenti agli assembly System, System.Windows.Forms, System.Drawing, System.Data e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="70e80-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="70e80-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="70e80-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="70e80-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="70e80-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="70e80-117">Vedere anche [come: Compilare ed eseguire un esempio di codice completo di Windows Form con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="70e80-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e80-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70e80-118">See also</span></span>
- [<span data-ttu-id="70e80-119">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="70e80-119">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="70e80-120">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="70e80-120">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="70e80-121">Procedura: Gestire errori ed eccezioni che si verificano con il Data Binding</span><span class="sxs-lookup"><span data-stu-id="70e80-121">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
