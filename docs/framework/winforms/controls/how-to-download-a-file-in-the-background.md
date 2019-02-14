---
title: 'Procedura: Scaricare un File in Background'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9b7bc5ae-051c-4904-9720-18f6667388bd
ms.openlocfilehash: e31008bcc9580c582effa3f0131a07aa4541db6f
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261011"
---
# <a name="how-to-download-a-file-in-the-background"></a><span data-ttu-id="2a7d7-102">Procedura: Scaricare un File in Background</span><span class="sxs-lookup"><span data-stu-id="2a7d7-102">How to: Download a File in the Background</span></span>
<span data-ttu-id="2a7d7-103">Il download di file è un'attività comune. Spesso è utile eseguire questa operazione potenzialmente dispendiosa in termini di tempo in un thread separato.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-103">Downloading a file is a common task, and it is often useful to run this potentially time-consuming operation on a separate thread.</span></span> <span data-ttu-id="2a7d7-104">Usare il componente <xref:System.ComponentModel.BackgroundWorker> per eseguire questa attività con una quantità di codice molto ridotta. </span><span class="sxs-lookup"><span data-stu-id="2a7d7-104">Use the <xref:System.ComponentModel.BackgroundWorker> component to accomplish this task with very little code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a7d7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="2a7d7-105">Example</span></span>  
 <span data-ttu-id="2a7d7-106">L'esempio di codice seguente illustra come usare un componente <xref:System.ComponentModel.BackgroundWorker> per caricare un file XML da un URL.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-106">The following code example demonstrates how to use a <xref:System.ComponentModel.BackgroundWorker> component to load an XML file from a URL.</span></span> <span data-ttu-id="2a7d7-107">Quando l'utente fa clic il **scaricare** pulsante, il <xref:System.Windows.Forms.Control.Click> chiamate del gestore eventi il <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> metodo di un <xref:System.ComponentModel.BackgroundWorker> componente per avviare l'operazione di download.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-107">When the user clicks the **Download** button, the <xref:System.Windows.Forms.Control.Click> event handler calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method of a <xref:System.ComponentModel.BackgroundWorker> component to start the download operation.</span></span> <span data-ttu-id="2a7d7-108">Il pulsante è disattivato per la durata del download e quindi abilitato una volta che il download è completato.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-108">The button is disabled for the duration of the download, and then enabled when the download is complete.</span></span> <span data-ttu-id="2a7d7-109">Un oggetto <xref:System.Windows.Forms.MessageBox> visualizza i contenuti del file.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-109">A <xref:System.Windows.Forms.MessageBox> displays the contents of the file.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#1)]  
  
 <span data-ttu-id="2a7d7-110">**Download del file**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-110">**Downloading the file**</span></span>  
  
 <span data-ttu-id="2a7d7-111">Il file viene scaricato nel thread di lavoro <xref:System.ComponentModel.BackgroundWorker> del componente, che esegue il gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-111">The file is downloaded on the <xref:System.ComponentModel.BackgroundWorker> component's worker thread, which runs the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="2a7d7-112">Questo thread inizia nel momento in cui il codice chiama il metodo <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-112">This thread starts when your code calls the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#3)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#3)]  
  
 <span data-ttu-id="2a7d7-113">**Attesa della fine di un metodo BackgroundWorker**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-113">**Waiting for a BackgroundWorker to finish**</span></span>  
  
 <span data-ttu-id="2a7d7-114">Il gestore eventi `downloadButton_Click` illustra come attendere il completamento di un'attività asincrona da parte di un componente <xref:System.ComponentModel.BackgroundWorker>.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-114">The `downloadButton_Click` event handler demonstrates how to wait for a <xref:System.ComponentModel.BackgroundWorker> component to finish its asynchronous task.</span></span>  
  
 <span data-ttu-id="2a7d7-115">Se si vuole solo che l'applicazione risponda ad eventi e non si vuole eseguire lavoro nel thread principale durante l'attesa del completamento del thread in background, è sufficiente uscire dal gestore.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-115">If you only want the application to respond to events and do not want to do any work in the main thread while you wait for the background thread to complete, just exit the handler.</span></span>  
  
 <span data-ttu-id="2a7d7-116">Se si vuole continuare a lavorare nel thread principale, usare la proprietà <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> per determinare se il thread <xref:System.ComponentModel.BackgroundWorker> è ancora in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-116">If you want to continue doing work in the main thread, use the <xref:System.ComponentModel.BackgroundWorker.IsBusy%2A> property to determine whether the <xref:System.ComponentModel.BackgroundWorker> thread is still running.</span></span> <span data-ttu-id="2a7d7-117">In questo esempio viene aggiornato un indicatore di stato durante l'elaborazione del download.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-117">In the example, a progress bar is updated while the download is processing.</span></span> <span data-ttu-id="2a7d7-118">Assicurarsi di chiamare il metodo <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> per mantenere reattiva l'interfaccia utente. </span><span class="sxs-lookup"><span data-stu-id="2a7d7-118">Be sure to call the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method to keep the UI responsive.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#2)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#2)]  
  
 <span data-ttu-id="2a7d7-119">**Visualizzazione del risultato**</span><span class="sxs-lookup"><span data-stu-id="2a7d7-119">**Displaying the result**</span></span>  
  
 <span data-ttu-id="2a7d7-120">Il metodo `backgroundWorker1_RunWorkerCompleted` gestisce l'evento <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> e viene chiamato quando l'operazione in background viene completata.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-120">The `backgroundWorker1_RunWorkerCompleted` method handles the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event and is called when the background operation is completed.</span></span> <span data-ttu-id="2a7d7-121">Questo metodo verifica prima di tutto la proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-121">This method first checks the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2a7d7-122">Se <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> è `null`, il metodo visualizza il contenuto del file,</span><span class="sxs-lookup"><span data-stu-id="2a7d7-122">If <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> is `null`, then this method displays the contents of the file.</span></span> <span data-ttu-id="2a7d7-123">quindi abilita il pulsante di download, disabilitato all'inizio del download, e reimposta l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-123">It then enables the download button, which was disabled when the download began, and it resets the progress bar.</span></span>  
  
 [!code-csharp[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/CS/Form1.cs#4)]
 [!code-vb[System.ComponentModel.BackgroundWorker.IsBusy#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.IsBusy/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a7d7-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2a7d7-124">Compiling the Code</span></span>  
 <span data-ttu-id="2a7d7-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a7d7-125">This example requires:</span></span>  
  
-   <span data-ttu-id="2a7d7-126">Riferimenti agli assembly System.Drawing, System.Windows.Forms e System.Xml.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-126">References to the System.Drawing, System.Windows.Forms, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="2a7d7-127">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2a7d7-127">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2a7d7-128">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-128">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2a7d7-129">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="2a7d7-129">Robust Programming</span></span>  
 <span data-ttu-id="2a7d7-130">Verificare sempre la presenza della proprietà <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> nel gestore eventi <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> prima di tentare di accedere alla proprietà <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> o ad eventuali altri oggetti che possano essere influenzati dal gestore eventi <xref:System.ComponentModel.BackgroundWorker.DoWork>.</span><span class="sxs-lookup"><span data-stu-id="2a7d7-130">Always check the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A?displayProperty=nameWithType> property in your <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler before attempting to access the <xref:System.ComponentModel.RunWorkerCompletedEventArgs.Result%2A?displayProperty=nameWithType> property or any other object that may have been affected by the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7d7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a7d7-131">See also</span></span>
- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="2a7d7-132">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="2a7d7-132">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="2a7d7-133">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="2a7d7-133">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
