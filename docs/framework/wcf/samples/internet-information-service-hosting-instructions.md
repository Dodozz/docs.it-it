---
title: Istruzioni per l'hosting su IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 92ee270426dbb7fdd166964c1b10e37f280e28f3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591874"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="8a83b-102">Istruzioni per l'hosting su IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="8a83b-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="8a83b-103">Per eseguire gli esempi ospitati su Internet Information Services (IIS) è necessario assicurarsi che IIS sia installato correttamente e sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8a83b-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="8a83b-104">Installazione di IIS versione 7.5 in Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8a83b-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="8a83b-105">Dal **Server Manager**, selezionare **ruoli.**</span><span class="sxs-lookup"><span data-stu-id="8a83b-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="8a83b-106">Sotto **Riepilogo ruoli**, fare clic su **Aggiungi ruoli**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="8a83b-107">Fare clic su **successivo** per visualizzare i **Selezione ruoli Server** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="8a83b-108">Selezionare **Server applicazioni** dal **ruoli** elenco e quindi fare clic su **Next** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il Ruolo Server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8a83b-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="8a83b-109">Selezionare il **Server Web (IIS)** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="8a83b-110">Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi funzionalità necessarie**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="8a83b-111">Fare clic su **successivo** due volte per visualizzare i **Selezione servizi ruolo** finestra di dialogo per il ruolo Server Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="8a83b-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="8a83b-112">Espandere **strumenti di gestione**, quindi espandere **compatibilità Gestione IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="8a83b-113">Selezionare **IIS strumenti di Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="8a83b-114">Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi servizi ruolo necessari**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="8a83b-115">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="8a83b-116">Se il riepilogo delle selezioni è corretto, fare clic su **installare**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="8a83b-117">Al termine dell'installazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="8a83b-118">Per installare IIS versione 7.5 in Windows 7</span><span class="sxs-lookup"><span data-stu-id="8a83b-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="8a83b-119">Fare clic su **avviare**, quindi fare clic su **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="8a83b-120">Aprire il **programmi** gruppo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="8a83b-121">Sotto **programmi e funzionalità**, fare clic su **attiva o disattiva Windows funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="8a83b-122">Il **User Account Control** viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="8a83b-123">Scegliere **Continua**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="8a83b-124">Il **funzionalità di Windows** viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="8a83b-125">Espandere l'elemento **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="8a83b-126">Espandere l'elemento **servizi World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="8a83b-127">Espandere l'elemento **funzionalità di sviluppo applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="8a83b-128">Verificare che gli elementi seguenti siano selezionati:</span><span class="sxs-lookup"><span data-stu-id="8a83b-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="8a83b-129">**Estendibilità .NET**</span><span class="sxs-lookup"><span data-stu-id="8a83b-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="8a83b-130">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="8a83b-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="8a83b-131">**Estensioni ISAPI**</span><span class="sxs-lookup"><span data-stu-id="8a83b-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="8a83b-132">**Filtri ISAPI**</span><span class="sxs-lookup"><span data-stu-id="8a83b-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="8a83b-133">Nell'elemento **servizi World Wide Web**, espandere **funzionalità Http comuni**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="8a83b-134">Assicurarsi che **contenuto statico** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a83b-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="8a83b-135">Nell'elemento **servizi World Wide Web**, espandere **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="8a83b-136">Verificare che l'opzione **Windows autenticazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a83b-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="8a83b-137">Sotto il **Internet Information Services** directory, espandere l'elemento **strumenti di gestione Web**, quindi selezionare **Console di gestione IIS**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="8a83b-138">Espandere l'elemento **compatibilità Gestione IIS 6**, quindi selezionare **strumenti di Scripting di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="8a83b-139">Sotto il **Internet Information Services** directory, espandere l'elemento **Microsoft .NET Framework 3.5.1**, quindi selezionare **attivazione Http Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="8a83b-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="8a83b-141">Installazione di IIS versione 7.0 in Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8a83b-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="8a83b-142">Dal **Server Manager**, selezionare **ruoli**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="8a83b-143">Sotto **Riepilogo ruoli**, fare clic su **Aggiungi ruoli**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="8a83b-144">Fare clic su **successivo** per visualizzare i **Selezione ruoli Server** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="8a83b-145">Selezionare **Server applicazioni** dal **ruoli** elenco e quindi fare clic su **Next** due volte per visualizzare il **Selezione servizi ruolo** finestra di dialogo per il Ruolo Server applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8a83b-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="8a83b-146">Selezionare **Server Web (IIS)** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="8a83b-147">Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi funzionalità necessarie**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="8a83b-148">Fare clic su **successivo** due volte per visualizzare i **Selezione servizi ruolo** finestra di dialogo per il ruolo Server Web (IIS).</span><span class="sxs-lookup"><span data-stu-id="8a83b-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="8a83b-149">Espandere **strumenti di gestione**, quindi espandere **compatibilità Gestione IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="8a83b-150">Selezionare **IIS strumenti di Scripting 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="8a83b-151">Se viene chiesto di installare ulteriori servizi ruolo e funzionalità, fare clic su **Aggiungi servizi ruolo necessari**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="8a83b-152">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="8a83b-153">Se il riepilogo delle selezioni è corretto, fare clic su **installare**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="8a83b-154">Al termine dell'installazione, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="8a83b-155">Per installare IIS sulla versione 7.0 in Windows Vista</span><span class="sxs-lookup"><span data-stu-id="8a83b-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="8a83b-156">Fare clic sul pulsante Start, quindi scegliere Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="8a83b-157">Selezionare il **programmi** gruppo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="8a83b-158">Sotto **programmi e funzionalità**, fare clic su **attiva o disattiva Windows funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="8a83b-159">Il **User Account Control** viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="8a83b-160">Scegliere **Continua**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="8a83b-161">Il **funzionalità di Windows** viene visualizzata una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a83b-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="8a83b-162">Espandere l'elemento **Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="8a83b-163">Espandere l'elemento **servizi World Wide Web**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="8a83b-164">Espandere l'elemento **funzionalità di sviluppo applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="8a83b-165">Verificare che gli elementi seguenti siano selezionati:</span><span class="sxs-lookup"><span data-stu-id="8a83b-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="8a83b-166">**Estendibilità .NET**</span><span class="sxs-lookup"><span data-stu-id="8a83b-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="8a83b-167">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="8a83b-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="8a83b-168">**Estensioni ISAPI**</span><span class="sxs-lookup"><span data-stu-id="8a83b-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="8a83b-169">**Filtri ISAPI**</span><span class="sxs-lookup"><span data-stu-id="8a83b-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="8a83b-170">Espandere l'elemento **strumenti di gestione Web**, quindi selezionare **Console di gestione IIS**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="8a83b-171">Nell'elemento **servizi World Wide Web**, espandere **funzionalità Http comuni**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="8a83b-172">Assicurarsi che **contenuto statico** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a83b-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="8a83b-173">Nell'elemento **servizi World Wide Web**, espandere **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="8a83b-174">Assicurarsi che **Windows autenticazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="8a83b-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="8a83b-175">Espandere l'elemento **compatibilità Gestione IIS 6**, quindi selezionare **strumenti di Scripting di IIS 6**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="8a83b-176">Espandere l'elemento **Microsoft .NET Framework 3.0**, quindi selezionare **attivazione Http Windows Communication Foundation**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="8a83b-177">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="8a83b-178">Per installare IIS versione 6.0 in Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="8a83b-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="8a83b-179">Dal **gestire il proprio Server**, fare clic su **Aggiungi o Rimuovi un ruolo**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="8a83b-180">Selezionare **Application server (IIS, ASP.NET)** dalle **ruolo del Server** elenco e quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="8a83b-181">Selezionare **Abilita ASP.NET** casella di controllo e quindi fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="8a83b-182">Se il riepilogo delle selezioni è corretto, fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="8a83b-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="8a83b-183">Per installare IIS versione 5.1 in Windows XP con Service Pack 2 e Service Pack 3 installati</span><span class="sxs-lookup"><span data-stu-id="8a83b-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="8a83b-184">Nel Pannello di controllo, fare clic su **Aggiungi / Rimuovi programmi**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="8a83b-185">Nel **Aggiungi / Rimuovi programmi** finestra di dialogo, fare clic su **Installazione componenti di Windows**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="8a83b-186">Nel **Aggiunta guidata componenti di Windows**, selezionare la **Internet Information Services (IIS)** casella di controllo e quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="8a83b-187">Se il **i file necessari** verrà visualizzata la finestra di dialogo, inserire il disco di installazione sistema operativo, selezionare la cartella i386 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="8a83b-188">Al termine dell'installazione, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="8a83b-189">Chiudere la **Aggiungi / Rimuovi programmi** finestra di dialogo e quindi chiudere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="8a83b-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="8a83b-190">Per verificare l'installazione di IIS e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8a83b-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="8a83b-191">Salvare il file HTML trovato alla fine di questo argomento nella directory radice \InetPub\wwwroot e rinominarlo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="8a83b-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="8a83b-192">Aprire una finestra di browser.</span><span class="sxs-lookup"><span data-stu-id="8a83b-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="8a83b-193">Tipo `http://localhost/Default.aspx` nella casella Indirizzo di e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8a83b-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="8a83b-194">Dovrebbe venire visualizzata una pagina Web contenente il testo "Hello World".</span><span class="sxs-lookup"><span data-stu-id="8a83b-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a83b-195">Ogni volta che si installa una nuova versione di .NET Framework, è necessario registrare nuovamente aspnet_isapi come estensione del servizio Web per IIS.</span><span class="sxs-lookup"><span data-stu-id="8a83b-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="8a83b-196">A tale scopo, eseguire il comando `aspnet_regiis –I –enable`.</span><span class="sxs-lookup"><span data-stu-id="8a83b-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="8a83b-197">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="8a83b-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
