---
title: 'Procedura: Abilitare il rilevamento della riproduzione del token'
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
ms.openlocfilehash: a357f153d61b6a8e1e105639bd68647dabdc26f8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336525"
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="d1dba-102">Procedura: Abilitare il rilevamento della riproduzione del token</span><span class="sxs-lookup"><span data-stu-id="d1dba-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="d1dba-103">Si applica a</span><span class="sxs-lookup"><span data-stu-id="d1dba-103">Applies To</span></span>  
  
-   <span data-ttu-id="d1dba-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="d1dba-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="d1dba-105">Web Form ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="d1dba-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d1dba-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d1dba-106">Summary</span></span>  
 <span data-ttu-id="d1dba-107">Questo argomento include le procedure dettagliate per abilitare il rilevamento riproduzione del token in un'applicazione ASP.NET che usa WIF.</span><span class="sxs-lookup"><span data-stu-id="d1dba-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="d1dba-108">Sono inoltre disponibili istruzioni su come testare l'applicazione per verificare che il rilevamento riproduzione del token sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="d1dba-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="d1dba-109">In questa guida procedurale non sono incluse le istruzioni dettagliate per la creazione di un servizio token di sicurezza (STS, Security Token Service); viene invece utilizzato il servizio token di sicurezza di sviluppo che viene fornito con lo strumento Identity and Access.</span><span class="sxs-lookup"><span data-stu-id="d1dba-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="d1dba-110">Il servizio token di sicurezza di sviluppo non esegue una reale autenticazione ed è finalizzato unicamente ai test.</span><span class="sxs-lookup"><span data-stu-id="d1dba-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="d1dba-111">Per completare questa guida procedurale sarà necessario installare Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="d1dba-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="d1dba-112">Può essere scaricato dal seguente percorso: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="d1dba-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="d1dba-113">Sommario</span><span class="sxs-lookup"><span data-stu-id="d1dba-113">Contents</span></span>  
  
-   <span data-ttu-id="d1dba-114">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="d1dba-114">Objectives</span></span>  
  
-   <span data-ttu-id="d1dba-115">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d1dba-115">Overview</span></span>  
  
-   <span data-ttu-id="d1dba-116">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="d1dba-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d1dba-117">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="d1dba-118">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="d1dba-119">Obiettivi</span><span class="sxs-lookup"><span data-stu-id="d1dba-119">Objectives</span></span>  
  
-   <span data-ttu-id="d1dba-120">Creare un'applicazione ASP.NET semplice che usa WIF e il servizio token di sicurezza per lo sviluppo locale dallo strumento Identity and Access</span><span class="sxs-lookup"><span data-stu-id="d1dba-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="d1dba-121">Abilitare il rilevamento riproduzione del token e verificare che funzioni</span><span class="sxs-lookup"><span data-stu-id="d1dba-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d1dba-122">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d1dba-122">Overview</span></span>  
 <span data-ttu-id="d1dba-123">Un attacco di tipo replay si verifica quando un client tenta di eseguire l'autenticazione per una relying party con un token del servizio token di sicurezza già usato dal client.</span><span class="sxs-lookup"><span data-stu-id="d1dba-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="d1dba-124">Per prevenire questo tipo di attacco, WIF contiene una cache di rilevamento riproduzione dei token del servizio token di sicurezza usati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d1dba-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="d1dba-125">Quando è abilitato, il rilevamento riproduzione controlla il token della richiesta in arrivo e verifica se il token è stato usato o meno in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d1dba-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="d1dba-126">Se il token è già stato usato, la richiesta viene rifiutata e viene generata un'eccezione <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>.</span><span class="sxs-lookup"><span data-stu-id="d1dba-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="d1dba-127">I passaggi seguenti illustrano le modifiche di configurazione necessarie per abilitare il rilevamento riproduzione.</span><span class="sxs-lookup"><span data-stu-id="d1dba-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="d1dba-128">Riepilogo dei passaggi</span><span class="sxs-lookup"><span data-stu-id="d1dba-128">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d1dba-129">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="d1dba-130">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="d1dba-131">Passaggio 1: creare una semplice applicazione Web Form ASP.NET e abilitare il rilevamento riproduzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="d1dba-132">In questo passaggio verrà creata una nuova applicazione Web Form ASP.NET e si modificherà il file *Web.config* per abilitare il rilevamento riproduzione.</span><span class="sxs-lookup"><span data-stu-id="d1dba-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="d1dba-133">Per creare un'applicazione ASP.NET semplice</span><span class="sxs-lookup"><span data-stu-id="d1dba-133">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="d1dba-134">Avviare Visual Studio e fare clic su **File**, **Nuovo** e **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="d1dba-135">Nella finestra **Nuovo progetto** fare clic su **Applicazione Web Form ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="d1dba-136">In **Nome** immettere `TestApp` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="d1dba-137">Fare clic con il pulsante destro del mouse sul progetto **TestApp** in **Esplora soluzioni** e quindi scegliere **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5. <span data-ttu-id="d1dba-138">Verrà visualizzata la finestra **Identity and Access**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="d1dba-139">In **Providers** (Provider) selezionare **Test your application with the Local Development STS** (Testare l'applicazione con il servizio token di sicurezza per lo sviluppo locale) e quindi fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6. <span data-ttu-id="d1dba-140">Aggiungere l'elemento **\<tokenReplayDetection>** seguente al file di configurazione *Web.config* subito dopo gli elementi **\<system.identityModel>** e **\<identityConfiguration>**, come illustrato:</span><span class="sxs-lookup"><span data-stu-id="d1dba-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="d1dba-141">Passaggio 2: eseguire i test sulla soluzione</span><span class="sxs-lookup"><span data-stu-id="d1dba-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="d1dba-142">In questo passaggio si testerà l'applicazione ASP.NET abilitata per WIF per verificare che il rilevamento riproduzione sia stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="d1dba-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="d1dba-143">Per testare il corretto funzionamento del rilevamento riproduzione per l'applicazione ASP.NET abilitata per WIF</span><span class="sxs-lookup"><span data-stu-id="d1dba-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1. <span data-ttu-id="d1dba-144">Eseguire la soluzione premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="d1dba-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="d1dba-145">Dovrebbe essere visualizzata la home page predefinita di ASP.NET e l'autenticazione dovrebbe avvenire automaticamente con il nome utente *Terry*, ovvero l'utente predefinito restituito dal servizio token di sicurezza per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="d1dba-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2. <span data-ttu-id="d1dba-146">Premere il pulsante **Indietro** del browser.</span><span class="sxs-lookup"><span data-stu-id="d1dba-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="d1dba-147">Dovrebbe essere visualizzata con un **errore Server nell'applicazione '/'** pagina con la descrizione seguente: *ID1062: Rilevata riproduzione per: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, seguita da un' *AssertionId* e un' *autorità di certificazione*.</span><span class="sxs-lookup"><span data-stu-id="d1dba-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="d1dba-148">Questa pagina di errore viene visualizzata perché è stata generata un'eccezione di tipo <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> al rilevamento della riproduzione token.</span><span class="sxs-lookup"><span data-stu-id="d1dba-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="d1dba-149">Questo errore si verifica perché si sta tentando di inviare nuovamente la richiesta POST iniziale della prima presentazione del token.</span><span class="sxs-lookup"><span data-stu-id="d1dba-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="d1dba-150">Il pulsante **Indietro** non causerà questo comportamento nelle richieste successive al server.</span><span class="sxs-lookup"><span data-stu-id="d1dba-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>
