---
title: Istruzioni del firewall
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 06e5ba64ab0ec3558e4c773c9cb21f961384e0c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650047"
---
# <a name="firewall-instructions"></a><span data-ttu-id="ce4f7-102">Istruzioni del firewall</span><span class="sxs-lookup"><span data-stu-id="ce4f7-102">Firewall Instructions</span></span>
<span data-ttu-id="ce4f7-103">È necessario abilitare più porte o programmi nel firewall in modo che possono funzionare gli esempi di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ce4f7-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="ce4f7-104">In molti degli esempi la comunicano avviene tramite le porte comprese nell'intervallo 8000-8003 e la porta 9000.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="ce4f7-105">Il firewall viene attivato per impostazione predefinita e impedisce l'accesso a queste porte.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="ce4f7-106">Per abilitare il firewall per gli esempi, completare una delle procedure descritte di seguito, a seconda dei requisiti e dell’ambiente di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="ce4f7-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
- <span data-ttu-id="ce4f7-107">Opzione 1: Abilitare in modo interattivo gli esempi durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="ce4f7-108">Non apportare nessuna modifica alla configurazione del firewall in anticipo e procedere con l’avvio e l’esecuzione degli esempi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="ce4f7-109">Quando si esegue un esempio, un **avviso di sicurezza di Windows** verrà visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="ce4f7-110">Il programma di esempio in questione può essere quindi aggiunto, in modo interattivo, a un elenco sbloccato.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="ce4f7-111">Questa procedura può richiedere il riavvio dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-111">With this procedure, you may have to then restart the sample.</span></span>  
  
- <span data-ttu-id="ce4f7-112">Opzione 2: Abilitare i programmi di esempio in anticipo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="ce4f7-113">Avviare il **Pannello di controllo di Windows Firewall** applet e abilitare i programmi di esempio si intende eseguire.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="ce4f7-114">Per creare file eseguibili, è necessario prima compilare i programmi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="ce4f7-115">Informazioni più dettagliate sono descritte nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-115">You can find more detailed instructions in the following procedure.</span></span>  
  
- <span data-ttu-id="ce4f7-116">Opzione 3: Abilitare un intervallo di porte in anticipo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="ce4f7-117">Avviare il **Windows Firewall** **Pannello di controllo** applet e abilitare le porte 80, 443, 8000-8003 e 9000, utilizzate dagli esempi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="ce4f7-118">Informazioni più dettagliate sono descritte nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="ce4f7-119">Questa opzione è meno sicura rispetto alle altre in quanto consente a qualsiasi programma di utilizzare queste porte, non solo agli esempi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="ce4f7-120">In caso di dubbi su quale procedura utilizzare, scegliere la prima opzione.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="ce4f7-121">Se si sta eseguendo un firewall di un altro fornitore, potrebbe essere necessario apportare modifiche simili.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ce4f7-122">La modifica della configurazione del firewall influisce sulla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="ce4f7-123">È consigliabile registrare le modifiche apportate e rimuoverle una volta completate le operazioni con gli esempi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="ce4f7-124">Abilitazione dei programmi di esempio in anticipo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="ce4f7-125">Compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="ce4f7-126">Fare clic su **avviare**, fare clic su **eseguito**e il tipo `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="ce4f7-127">Verrà visualizzata la **Pannello di controllo di Windows Firewall** applet.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce4f7-128">Per modificare le impostazioni del firewall ed eseguire gli esempi che richiedono la possibilità di comunicare con Windows Firewall, è necessario disporre delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="ce4f7-129">Se alcune impostazioni del firewall non sono disponibili e il computer è connesso a un dominio, è possibile che queste impostazioni vengano controllate dall'amministratore di sistema tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="ce4f7-130">Completare uno dei passaggi operativi specifici seguente per consentire a un programma l'accesso con Windows Firewall:</span><span class="sxs-lookup"><span data-stu-id="ce4f7-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    - <span data-ttu-id="ce4f7-131">In Windows 7 o Windows Server 2008 r2, fare clic su **consentono a un programma o funzionalità attraverso Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="ce4f7-132">Fare clic su **modificare le impostazioni**, consentire **un altro programma...** .</span><span class="sxs-lookup"><span data-stu-id="ce4f7-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    - <span data-ttu-id="ce4f7-133">Sul [!INCLUDE[wv](../../../../includes/wv-md.md)] oppure [!INCLUDE[lserver](../../../../includes/lserver-md.md)], fare clic su **consentire a un programma attraverso Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="ce4f7-134">Nel **eccezioni** scheda, fare clic su **Aggiungi programma**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="ce4f7-135">Scegliere il **esplorare** e selezionare il file eseguibile dell'esempio si prevede di eseguire.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="ce4f7-136">Ripetere i passaggi 4 e 5 finché vengono aggiunti i file eseguibili di tutti gli esempi che si intende eseguire.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="ce4f7-137">Fare clic su **OK** per chiudere l'applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="ce4f7-138">Abilitazione di un intervallo delle porte in anticipo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="ce4f7-139">Fare clic su **avviare**, fare clic su **eseguito**e il tipo `firewall.cpl`.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="ce4f7-140">Verrà visualizzata la **Pannello di controllo di Windows Firewall** applet.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="ce4f7-141">In Windows 7 o Windows Server 2008 R2 attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ce4f7-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1. <span data-ttu-id="ce4f7-142">Fare clic su **impostazioni avanzate** nella colonna sinistra della finestra di Windows Firewall.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2. <span data-ttu-id="ce4f7-143">Fare clic su **regole connessioni in entrata** nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3. <span data-ttu-id="ce4f7-144">Fare clic su **nuove regole** nella colonna destra.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-144">Click **New Rules** in the right column.</span></span>  
  
    4. <span data-ttu-id="ce4f7-145">Selezionare **porta** e fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-145">Select **Port** and click **next**.</span></span>  
  
    5. <span data-ttu-id="ce4f7-146">Selezionare **TCP** e immettere `8000, 8001, 8002, 8003, 9000, 80, 443` nel **porte locali specifiche** campo.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6. <span data-ttu-id="ce4f7-147">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-147">Click **Next**.</span></span>  
  
    7. <span data-ttu-id="ce4f7-148">Selezionare **Consenti solo connessioni**, fare clic su **successivo** .</span><span class="sxs-lookup"><span data-stu-id="ce4f7-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8. <span data-ttu-id="ce4f7-149">Selezionare **Domain** e **privato**, fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="ce4f7-150">Denominare la regola `WCF-WF 4.0 Samples`, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="ce4f7-151">Fare clic su **regole in uscita** e ripetere i passaggi da c a h.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="ce4f7-152">In [!INCLUDE[wv](../../../../includes/wv-md.md)] o [!INCLUDE[lserver](../../../../includes/lserver-md.md)] attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ce4f7-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1. <span data-ttu-id="ce4f7-153">Fare clic su **consentire a un programma attraverso Windows Firewall**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2. <span data-ttu-id="ce4f7-154">Nel **eccezioni** scheda, fare clic su **Aggiungi porta**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3. <span data-ttu-id="ce4f7-155">Immettere un nome, immettere 8000 come numero di porta e selezionare il **TCP** opzione.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4. <span data-ttu-id="ce4f7-156">Fare clic sui **Cambia ambito** pulsante, seleziona la **rete personale** unica opzione disponibile (subnet) e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5. <span data-ttu-id="ce4f7-157">Ripetere i passaggi da B a D per le porte 8001, 8002, 8003, 9000, 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="ce4f7-158">Fare clic su **OK** per chiudere l'applet del firewall.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce4f7-159">Rimuovere qualsiasi eccezione del firewall una volta completate le operazioni con gli esempi.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="ce4f7-160">A tale scopo, aprire il **Pannello di controllo di Windows Firewall** applet e rimuovere eventuali programmi o trasferire le voci che sono state aggiunte alle procedure precedenti.</span><span class="sxs-lookup"><span data-stu-id="ce4f7-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
