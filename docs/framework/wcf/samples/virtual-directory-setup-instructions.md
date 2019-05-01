---
title: Istruzioni per la configurazione di directory virtuali
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: fdff88026a49989870ee5c47f9a38a65ecad3c80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007552"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="7f17d-102">Istruzioni per la configurazione di directory virtuali</span><span class="sxs-lookup"><span data-stu-id="7f17d-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="7f17d-103">Gli esempi di Windows Communication Foundation (WCF) devono condividere una directory virtuale comune denominata servicemodelsamples associata viene eseguito il mapping alla cartella %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f17d-104">%SystemDrive% è in genere C: o D:, a seconda della posizione dell'unità dove è installato IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="7f17d-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="7f17d-105">È possibile eseguire i file setupvroot e cleanupvroot dal [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) per creare la directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="7f17d-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="7f17d-106">Se si preferisce creare la directory virtuale manualmente, utilizzare le procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="7f17d-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="7f17d-107">Procedure</span><span class="sxs-lookup"><span data-stu-id="7f17d-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="7f17d-108">Per creare una directory virtuale in IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7f17d-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="7f17d-109">Dal **avviare** menu, fare clic su **eseguito**, quindi digitare **inetmgr** per aprire lo snap-in MMC di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7f17d-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="7f17d-110">Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere la **siti** nodo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="7f17d-111">Fare doppio clic su **sito Web predefinito**, quindi selezionare **Aggiungi applicazione** per aprire il **finestra Aggiungi applicazione**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="7f17d-112">Nella finestra di, digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="7f17d-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="7f17d-113">Creare la directory seguente: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="7f17d-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="7f17d-114">Impostare il percorso fisico su %SystemDrive%\inetpub\wwwroot\\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="7f17d-115">Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.</span><span class="sxs-lookup"><span data-stu-id="7f17d-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="7f17d-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-116">Click **OK**.</span></span> <span data-ttu-id="7f17d-117">L'applicazione Web è stata creata per gli esempi WCF.</span><span class="sxs-lookup"><span data-stu-id="7f17d-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f17d-118">Questa attività deve essere eseguita una sola volta, poiché tutti gli esempi WCF utilizzano la stessa applicazione Web servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f17d-119">Ai fini di questa documentazione, il termine `virtual directory` è sinonimo di `Web application`.</span><span class="sxs-lookup"><span data-stu-id="7f17d-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="7f17d-120">Oltre a creare la directory virtuale, è necessario anche impostare le proprietà per abilitare i servizi WCF per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7f17d-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="7f17d-121">Di seguito sono riportate informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="7f17d-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="7f17d-122">Per creare una directory virtuale in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7f17d-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="7f17d-123">Aprire una finestra del prompt dei comandi e digitare `start inetmgr` per aprire lo snap-in MMC di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7f17d-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="7f17d-124">Nel riquadro sinistro, espandere il nodo con il nome del computer e quindi espandere la **siti Web** nodo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="7f17d-125">Fare doppio clic su **sito Web predefinito** e selezionare **New, Virtual Directory** per aprire la procedura guidata Creazione Directory virtuale.</span><span class="sxs-lookup"><span data-stu-id="7f17d-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="7f17d-126">Nella procedura guidata digitare `servicemodelsamples` come alias per la directory virtuale che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="7f17d-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="7f17d-127">Impostare il percorso su %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="7f17d-128">Molti degli esempi WCF copiano file eseguibili di servizi in questo percorso quando vengono generati.</span><span class="sxs-lookup"><span data-stu-id="7f17d-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="7f17d-129">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="7f17d-130">Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:</span><span class="sxs-lookup"><span data-stu-id="7f17d-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="7f17d-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="7f17d-131">**Read**</span></span>  
  
    - <span data-ttu-id="7f17d-132">**Eseguire gli script (ad esempio, ASP)**</span><span class="sxs-lookup"><span data-stu-id="7f17d-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="7f17d-133">Fare clic su **successivo**, quindi fare clic su **fine** per completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="7f17d-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f17d-134">Questa attività deve essere eseguita una sola volta poiché tutti gli esempi WCF usano la stessa directory virtuale servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="7f17d-135">Per impostare proprietà aggiuntive della directory virtuale in IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7f17d-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="7f17d-136">Fare clic sul nodo servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="7f17d-137">Lungo la parte inferiore della finestra sono elencate due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="7f17d-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="7f17d-138">Selezionare **visualizzazione funzionalità** se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="7f17d-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="7f17d-139">Fare doppio clic sulla voce relativa **esplorazione Directory**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="7f17d-140">Nel riquadro azioni, selezionare la **abilitare** opzione.</span><span class="sxs-lookup"><span data-stu-id="7f17d-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="7f17d-141">In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f17d-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="7f17d-142">Infine, è necessario impostare le proprietà di sicurezza della cartella servicemodelsamples per renderla accessibile ad altri.</span><span class="sxs-lookup"><span data-stu-id="7f17d-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="7f17d-143">Di seguito sono riportate informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="7f17d-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="7f17d-144">Per impostare proprietà aggiuntive della directory virtuale in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7f17d-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="7f17d-145">Fare clic sul nodo servicemodelsamples e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="7f17d-146">Per impostazione predefinita, le caselle di controllo seguenti sono selezionate:</span><span class="sxs-lookup"><span data-stu-id="7f17d-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="7f17d-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="7f17d-147">**Read**</span></span>  
  
    - <span data-ttu-id="7f17d-148">**Registrazione visite**</span><span class="sxs-lookup"><span data-stu-id="7f17d-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="7f17d-149">**Indicizza questa risorsa**</span><span class="sxs-lookup"><span data-stu-id="7f17d-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="7f17d-150">Selezionare il **esplorazione Directory** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="7f17d-151">In questo modo sarà possibile accedere alla directory della directory utilizzando Internet Explorer che facilita l’esecuzione del debug di un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f17d-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="7f17d-152">Per impostare le proprietà di sicurezza della cartella in IIS 7.0 o 7.5</span><span class="sxs-lookup"><span data-stu-id="7f17d-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="7f17d-153">Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="7f17d-154">Fare doppio clic sulla cartella servicemodelsamples e scegliere **Share** oppure **Condividi con**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="7f17d-155">Fare clic sulla freccia verso il basso a sinistra del **Add** pulsante.</span><span class="sxs-lookup"><span data-stu-id="7f17d-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="7f17d-156">Selezionare il **trovare** voce.</span><span class="sxs-lookup"><span data-stu-id="7f17d-156">Select the **Find** entry.</span></span> <span data-ttu-id="7f17d-157">Il **Seleziona utenti o gruppi** verrà visualizzata la finestra.</span><span class="sxs-lookup"><span data-stu-id="7f17d-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="7f17d-158">Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="7f17d-159">Fare clic su **posizioni**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-159">Click **Locations**.</span></span> <span data-ttu-id="7f17d-160">Il **posizioni** viene aperta la finestra.</span><span class="sxs-lookup"><span data-stu-id="7f17d-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="7f17d-161">Selezionare la voce per il computer utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7f17d-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="7f17d-162">È importante selezionare il computer locale e non una voce per qualsiasi dominio o reti elencati.</span><span class="sxs-lookup"><span data-stu-id="7f17d-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="7f17d-163">Dopo aver selezionato il computer, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="7f17d-164">Fare clic su **trova**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-164">Click **Find Now**.</span></span> <span data-ttu-id="7f17d-165">Nei risultati di ricerca vengono inseriti gli oggetti associati al computer locale.</span><span class="sxs-lookup"><span data-stu-id="7f17d-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="7f17d-166">Trovare il **IIS_IUSRS** voce il **Name (nome distinto relativo)** colonna.</span><span class="sxs-lookup"><span data-stu-id="7f17d-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="7f17d-167">Selezionare una voce e fare clic su **OK** per chiudere la ricerca i risultati della finestra.</span><span class="sxs-lookup"><span data-stu-id="7f17d-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="7f17d-168">Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** finestra.</span><span class="sxs-lookup"><span data-stu-id="7f17d-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="7f17d-169">Fare clic su **condivisione** per rendere permanenti le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7f17d-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="7f17d-170">Una volta completate le modifiche per abilitare la condivisione, fare clic su **Completato** per chiudere la finestra **Condivisione File**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="7f17d-171">Per impostare le proprietà di sicurezza della cartella in IIS 5.1 o 6.0</span><span class="sxs-lookup"><span data-stu-id="7f17d-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="7f17d-172">Passare a %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="7f17d-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="7f17d-173">Fare doppio clic il **servicemodelsamples** cartella e quindi fare clic su **condivisione e sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="7f17d-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="7f17d-174">Fare clic sulla scheda **Sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="7f17d-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="7f17d-175">Se si utilizza IIS 6.0, nella **nomi utente o gruppo** finestra di controllo se **Account Internet Guest** sia elencato.</span><span class="sxs-lookup"><span data-stu-id="7f17d-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="7f17d-176">Se non è elencato:</span><span class="sxs-lookup"><span data-stu-id="7f17d-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="7f17d-177">Fare clic sul pulsante **Start** e scegliere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="7f17d-178">Se non viene visualizzato il **gli account utente** icona, fare clic su **passare alla visualizzazione per categorie**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="7f17d-179">Scegliere il **gli account utente** icona.</span><span class="sxs-lookup"><span data-stu-id="7f17d-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="7f17d-180">In "o un'icona di Pannello di controllo di selezione" fare clic su **gli account utente**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="7f17d-181">Nel **gli account utente** finestra di dialogo, fare clic sul **avanzate** scheda.</span><span class="sxs-lookup"><span data-stu-id="7f17d-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="7f17d-182">Scegliere **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="7f17d-183">Nel **utenti e gruppi locali** finestra di dialogo, fare clic per espandere le **utenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="7f17d-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="7f17d-184">Nel riquadro di destra, fare doppio clic su **Account Internet Guest**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="7f17d-185">Nel **proprietà** nella finestra di dialogo, copiare il nome usato come account Internet guest.</span><span class="sxs-lookup"><span data-stu-id="7f17d-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="7f17d-186">Per impostazione predefinita, il nome inizia con “USR_” seguito dal nome del computer.</span><span class="sxs-lookup"><span data-stu-id="7f17d-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="7f17d-187">Chiudere la finestra di dialogo **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="7f17d-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="7f17d-188">Chiudi il **utenti e gruppi locali** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="7f17d-189">Chiudi il **gli account utente** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="7f17d-190">Chiudere l'altra **gli account utente** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="7f17d-191">Nel **proprietà-servicemodelsamples** finestra di dialogo il **Security** scheda, fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="7f17d-192">Digitare il nome del computer seguito da una barra rovesciata, quindi incollare il nome dell'account utente di Internet, ad esempio, myMachineName\\InternetGuestAccountName % %</span><span class="sxs-lookup"><span data-stu-id="7f17d-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="7f17d-193">Fare clic su **Controlla nomi** per verificare l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="7f17d-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="7f17d-194">Se è valido, il nome è composto di tutti caratteri maiuscoli ed è sottolineato.</span><span class="sxs-lookup"><span data-stu-id="7f17d-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="7f17d-195">Per IIS 6.0, controllare anche che servizio di rete sia elencato nel **nomi utente o gruppo** casella.</span><span class="sxs-lookup"><span data-stu-id="7f17d-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="7f17d-196">Se SERVIZIO DI RETE non è elencato:</span><span class="sxs-lookup"><span data-stu-id="7f17d-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="7f17d-197">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="7f17d-198">Nel **Seleziona utenti o gruppi** nella finestra di dialogo digitare il nome del computer seguito da una barra rovesciata.</span><span class="sxs-lookup"><span data-stu-id="7f17d-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="7f17d-199">Tipo di **servizio** dopo la barra rovesciata (senza spazi).</span><span class="sxs-lookup"><span data-stu-id="7f17d-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="7f17d-200">Fare clic su **Controlla nomi**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="7f17d-201">Se vengono trovati più nomi, selezionare **servizio di rete** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="7f17d-202">Fare clic su **OK** per chiudere la **Seleziona utenti o gruppi** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7f17d-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="7f17d-203">Se si utilizza Windows XP SP2 con IIS 5.1, controllare che sia Account Internet Guest e ASPNET siano elencati nel **nomi utente o gruppo** casella.</span><span class="sxs-lookup"><span data-stu-id="7f17d-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="7f17d-204">Si noti che l'utente ASPNET può essere un membro di incorporati **utenti** gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7f17d-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="7f17d-205">In questo caso, quindi, se il **utenti** gruppo è elencato nella finestra di dialogo, non è necessario aggiungerlo come elemento separato per l'elenco di utenti autorizzati.</span><span class="sxs-lookup"><span data-stu-id="7f17d-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="7f17d-206">Per controllare se ASPNET fa parte il **utenti** gruppo di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="7f17d-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="7f17d-207">Nel **avviare** menu, fare clic su **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="7f17d-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="7f17d-208">Scegliere il **gli account utente** icona.</span><span class="sxs-lookup"><span data-stu-id="7f17d-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="7f17d-209">Nel **gruppo** colonna, verificare che il valore per **ASPNET** è "Users".</span><span class="sxs-lookup"><span data-stu-id="7f17d-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f17d-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f17d-210">See also</span></span>

- [<span data-ttu-id="7f17d-211">Istruzioni per l'hosting su Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="7f17d-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
