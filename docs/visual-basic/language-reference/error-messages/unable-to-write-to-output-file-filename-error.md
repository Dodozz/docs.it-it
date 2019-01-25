---
title: 'Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;'
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: c82f1e6e4a01af87cc7dce49cfaa78f9be1631db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572695"
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a><span data-ttu-id="f2517-102">Impossibile scrivere nel file di output &#39; &lt;filename&gt;&#39;: &lt;errore&gt;</span><span class="sxs-lookup"><span data-stu-id="f2517-102">Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;</span></span>
<span data-ttu-id="f2517-103">Si è verificato un problema durante la creazione del file.</span><span class="sxs-lookup"><span data-stu-id="f2517-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="f2517-104">Non è possibile aprire un file di output per la scrittura.</span><span class="sxs-lookup"><span data-stu-id="f2517-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="f2517-105">È possibile che il file (o la cartella contenente il file) sia aperto per l'uso esclusivo da parte di un altro processo o è stato impostato l'attributo di sola lettura del file.</span><span class="sxs-lookup"><span data-stu-id="f2517-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="f2517-106">Di seguito sono elencate alcune situazioni comuni in cui un file è aperto in modo esclusivo:</span><span class="sxs-lookup"><span data-stu-id="f2517-106">Common situations where a file is opened exclusively are:</span></span>  
  
-   <span data-ttu-id="f2517-107">L'applicazione è già in esecuzione e sta usando i file correlati.</span><span class="sxs-lookup"><span data-stu-id="f2517-107">The application is already running and using its files.</span></span> <span data-ttu-id="f2517-108">Per risolvere il problema, assicurarsi che l'applicazione non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f2517-108">To solve this problem, make sure that the application is not running.</span></span>  
  
-   <span data-ttu-id="f2517-109">Un'altra applicazione ha aperto il file.</span><span class="sxs-lookup"><span data-stu-id="f2517-109">Another application has opened the file.</span></span> <span data-ttu-id="f2517-110">Per risolvere il problema, assicurarsi che altre applicazioni non accedano ai file.</span><span class="sxs-lookup"><span data-stu-id="f2517-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="f2517-111">Non è sempre semplice capire quale applicazione sta accedendo ai file. In questo caso, riavviare il computer potrebbe rappresentare il modo più semplice per arrestare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f2517-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="f2517-112">Se anche uno solo dei file di output del progetto è contrassegnato come di sola lettura, sarà generata questa eccezione.</span><span class="sxs-lookup"><span data-stu-id="f2517-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="f2517-113">**ID errore:** BC31019</span><span class="sxs-lookup"><span data-stu-id="f2517-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2517-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f2517-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2517-115">Ripetere la compilazione del programma, per controllare se l'errore si verifica di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f2517-115">Compile the program again to see if the error recurs.</span></span>  
  
2.  <span data-ttu-id="f2517-116">Se l'errore si ripresenta, salvare il lavoro e riavviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2517-116">If the error continues, save your work and restart Visual Studio.</span></span>  
  
3.  <span data-ttu-id="f2517-117">Se l'errore si ripresenta, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="f2517-117">If the error continues, restart the computer.</span></span>  
  
4.  <span data-ttu-id="f2517-118">Se l'errore si ripete, reinstallare Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2517-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5.  <span data-ttu-id="f2517-119">Se l'errore persiste dopo la reinstallazione, inviare una notifica al Servizio supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2517-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="f2517-120">Per controllare gli attributi di file in Esplora file</span><span class="sxs-lookup"><span data-stu-id="f2517-120">To check file attributes in File Explorer</span></span>  
  
1.  <span data-ttu-id="f2517-121">Aprire la cartella a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="f2517-121">Open the folder you are interested in.</span></span>  
  
2.  <span data-ttu-id="f2517-122">Fare clic sui **viste** icona e scegliere **dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f2517-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3.  <span data-ttu-id="f2517-123">Fare doppio clic sull'intestazione di colonna e scegliere **attributi** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="f2517-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="f2517-124">Per modificare gli attributi di un file o una cartella</span><span class="sxs-lookup"><span data-stu-id="f2517-124">To change the attributes of a file or folder</span></span>  
  
1.  <span data-ttu-id="f2517-125">Nelle **Esplora File**, fare doppio clic su file o della cartella e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f2517-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="f2517-126">Nel **attributi** sezione del **generali** scheda, deseleziona il **Read-only** casella.</span><span class="sxs-lookup"><span data-stu-id="f2517-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3.  <span data-ttu-id="f2517-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2517-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2517-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2517-128">See also</span></span>
- <span data-ttu-id="f2517-129">[Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)</span><span class="sxs-lookup"><span data-stu-id="f2517-129">[Talk to Us](/visualstudio/ide/talk-to-us)</span></span>
