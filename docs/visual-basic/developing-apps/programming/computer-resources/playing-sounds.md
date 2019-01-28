---
title: Riproduzione di suoni (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
ms.openlocfilehash: f303687fb86e23191727df769af52811a93fe71e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715790"
---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="35e81-102">Riproduzione di suoni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35e81-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="35e81-103">Il metodo `My.Computer.Audio` offre metodi per la riproduzione di suoni.</span><span class="sxs-lookup"><span data-stu-id="35e81-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="35e81-104">Riproduzione di suoni</span><span class="sxs-lookup"><span data-stu-id="35e81-104">Playing Sounds</span></span>  
 <span data-ttu-id="35e81-105">La riproduzione in background consente all'applicazione di eseguire altro codice durante la riproduzione di suoni.</span><span class="sxs-lookup"><span data-stu-id="35e81-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="35e81-106">Il metodo `My.Computer.Audio.Play` consente all'applicazione di riprodurre un solo suono di sottofondo alla volta: quando l'applicazione riproduce un nuovo suono di sottofondo, viene interrotta la riproduzione del suono di sottofondo precedente.</span><span class="sxs-lookup"><span data-stu-id="35e81-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="35e81-107">È anche possibile riprodurre un suono e attendere il completamento della riproduzione.</span><span class="sxs-lookup"><span data-stu-id="35e81-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="35e81-108">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono.</span><span class="sxs-lookup"><span data-stu-id="35e81-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="35e81-109">Quando è specificato `AudioPlayMode.WaitToComplete`, `My.Computer.Audio.Play` attende il completamento del suono prima di continuare a chiamare codice.</span><span class="sxs-lookup"><span data-stu-id="35e81-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="35e81-110">Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="35e81-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 [!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]  
  
 <span data-ttu-id="35e81-111">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce un suono.</span><span class="sxs-lookup"><span data-stu-id="35e81-111">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="35e81-112">Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.</span><span class="sxs-lookup"><span data-stu-id="35e81-112">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="35e81-113">Riproduzione di file audio a ciclo continuo</span><span class="sxs-lookup"><span data-stu-id="35e81-113">Playing Looping Sounds</span></span>  
 <span data-ttu-id="35e81-114">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="35e81-114">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="35e81-115">Quando si usa questo esempio è necessario assicurarsi che il nome file faccia riferimento a un file audio con estensione wav presente nel computer.</span><span class="sxs-lookup"><span data-stu-id="35e81-115">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]  
  
 <span data-ttu-id="35e81-116">Nell'esempio seguente il metodo `My.Computer.Audio.Play` riproduce il file audio specificato in background quando è specificato `PlayMode.BackgroundLoop`.</span><span class="sxs-lookup"><span data-stu-id="35e81-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="35e81-117">Quando si usa questo esempio è necessario assicurarsi che le risorse dell'applicazione includano un file audio con estensione wav denominato Waterfall.</span><span class="sxs-lookup"><span data-stu-id="35e81-117">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]  
  
 <span data-ttu-id="35e81-118">L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="35e81-118">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="35e81-119">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e81-119">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="35e81-120">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="35e81-120">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="35e81-121">In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="35e81-121">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="35e81-122">Interruzione della riproduzione di suoni in background</span><span class="sxs-lookup"><span data-stu-id="35e81-122">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="35e81-123">Usare il metodo `My.Computer.Audio.Stop` per interrompere la riproduzione di file audio in background o a ciclo continuo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="35e81-123">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="35e81-124">In generale, quando un'applicazione riproduce un file audio a ciclo continuo, la riproduzione dovrà prima o poi essere interrotta.</span><span class="sxs-lookup"><span data-stu-id="35e81-124">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="35e81-125">L'esempio seguente interrompe la riproduzione di un file audio in background.</span><span class="sxs-lookup"><span data-stu-id="35e81-125">The following example stops a sound that is playing in the background.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]  
  
 <span data-ttu-id="35e81-126">L'esempio di codice precedente è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="35e81-126">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="35e81-127">Nello strumento di selezione dei frammenti di codice il frammento di codice si trova in **Applicazioni Windows Form > Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e81-127">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="35e81-128">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="35e81-128">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="35e81-129">Riproduzione di suoni di sistema</span><span class="sxs-lookup"><span data-stu-id="35e81-129">Playing System Sounds</span></span>  
 <span data-ttu-id="35e81-130">Usare il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre il suono di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="35e81-130">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="35e81-131">Il metodo `My.Computer.Audio.PlaySystemSound` accetta come parametro uno dei membri condivisi della classe <xref:System.Media.SystemSound>.</span><span class="sxs-lookup"><span data-stu-id="35e81-131">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="35e81-132">Il suono di sistema <xref:System.Media.SystemSounds.Asterisk%2A> indica in genere la presenza di errori.</span><span class="sxs-lookup"><span data-stu-id="35e81-132">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="35e81-133">L'esempio seguente usa il metodo `My.Computer.Audio.PlaySystemSound` per riprodurre un suono di sistema.</span><span class="sxs-lookup"><span data-stu-id="35e81-133">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="35e81-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35e81-134">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Audio>
- <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>
- <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>
- <xref:Microsoft.VisualBasic.AudioPlayMode>
