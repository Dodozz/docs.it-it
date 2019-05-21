---
title: 'Procedura: Installare e configurare componenti di attivazione WCF'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 953df285d1a439cd8a1a95358915a7a50e98552a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960099"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="fa254-102">Procedura: Installare e configurare componenti di attivazione WCF</span><span class="sxs-lookup"><span data-stu-id="fa254-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="fa254-103">In questo argomento vengono descritti i passaggi necessari per configurare il servizio Attivazione processo Windows (noto anche come WAS) in [!INCLUDE[wv](../../../../includes/wv-md.md)] per Windows Communication Foundation (WCF) di ospitare servizi che non comunicano su HTTP i protocolli di rete.</span><span class="sxs-lookup"><span data-stu-id="fa254-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="fa254-104">Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:</span><span class="sxs-lookup"><span data-stu-id="fa254-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="fa254-105">Installare (o confermare l'installazione di) i componenti di attivazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="fa254-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
- <span data-ttu-id="fa254-106">Configurare WAS per supportare un protocollo non HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa254-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="fa254-107">Nella procedura seguente viene illustrato come configurare [!INCLUDE[wv](../../../../includes/wv-md.md)] per l'attivazione TCP.</span><span class="sxs-lookup"><span data-stu-id="fa254-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="fa254-108">Dopo aver installato e configurato WAS, vedere [come: Ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) per le procedure creare un servizio WCF che espone un endpoint non HTTP che utilizza WAS.</span><span class="sxs-lookup"><span data-stu-id="fa254-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="fa254-109">Per installare i componenti di attivazione WCF non HTTP</span><span class="sxs-lookup"><span data-stu-id="fa254-109">To install the WCF non-HTTP activation components</span></span>  
  
1. <span data-ttu-id="fa254-110">Scegliere il **avviare** pulsante e quindi fare clic su **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="fa254-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="fa254-111">Fare clic su **i programmi**, quindi fare clic su **programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="fa254-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3. <span data-ttu-id="fa254-112">Nel **attività** menu, fare clic su **o disattivazione delle funzionalità Windows attivare**.</span><span class="sxs-lookup"><span data-stu-id="fa254-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4. <span data-ttu-id="fa254-113">Trovare il nodo WinFX, select e quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="fa254-113">Find the WinFX node, select and then expand it.</span></span>  
  
5. <span data-ttu-id="fa254-114">Selezionare il **componenti di attivazione Non Http di WCF** casella e salvare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="fa254-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="fa254-115">Per configurare WAS per supportare l'attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="fa254-115">To configure the WAS to support TCP activation</span></span>  
  
1. <span data-ttu-id="fa254-116">Per supportare l'attivazione net.tcp, è prima necessario associare il sito Web predefinito a una porta net.tcp.</span><span class="sxs-lookup"><span data-stu-id="fa254-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="fa254-117">A tale fine, utilizzare Appcmd.exe, installato con il set di strumenti di gestione di [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa254-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="fa254-118">In una finestra del prompt dei comandi a livello di amministratore, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="fa254-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa254-119">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-119">This command is a single line of text.</span></span> <span data-ttu-id="fa254-120">Il comando aggiunge un'associazione del sito net.tcp al sito Web predefinito in ascolto sulla porta TCP 808 con qualsiasi nome host.</span><span class="sxs-lookup"><span data-stu-id="fa254-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2. <span data-ttu-id="fa254-121">Anche se tutte le applicazioni all'interno di un sito condividono un'associazione net.tcp comune, ognuna di esse può attivare il supporto net.tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="fa254-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="fa254-122">Per attivare net.tcp per l'applicazione, eseguire il comando seguente da un prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa254-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa254-123">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-123">This command is a single line of text.</span></span> <span data-ttu-id="fa254-124">Questo comando abilita il /\<*applicazione WCF*> applicazione a cui accedere con entrambi `http://localhost/<WCF Application>` e `net.tcp://localhost/<WCF Application>`.</span><span class="sxs-lookup"><span data-stu-id="fa254-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="fa254-125">Rimuovere l'associazione del sito net.tcp aggiunta per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="fa254-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="fa254-126">Per comodità, i due passaggi seguenti vengono implementati in un file batch chiamato RemoveNetTcpSiteBinding.cmd situato nella directory di esempio.</span><span class="sxs-lookup"><span data-stu-id="fa254-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1. <span data-ttu-id="fa254-127">Rimuovere net.tcp dall'elenco dei protocolli attivati tramite il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa254-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="fa254-128">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-128">This command is a single line of text.</span></span>  
  
    2. <span data-ttu-id="fa254-129">Rimuovere l'associazione del sito net.tcp tramite il comando seguente in una finestra del prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="fa254-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="fa254-130">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="fa254-131">Per rimuovere net.tcp dall'elenco dei protocolli attivati</span><span class="sxs-lookup"><span data-stu-id="fa254-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1. <span data-ttu-id="fa254-132">Per rimuovere net.tcp dall'elenco dei protocolli attivati, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa254-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa254-133">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="fa254-134">Per rimuovere l'associazione del sito net.tcp</span><span class="sxs-lookup"><span data-stu-id="fa254-134">To remove the net.tcp site binding</span></span>  
  
1. <span data-ttu-id="fa254-135">Per rimuovere l'associazione del sito net.tcp, eseguire il comando seguente in una finestra del prompt dei comandi a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="fa254-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa254-136">Questo comando è una singola riga di testo.</span><span class="sxs-lookup"><span data-stu-id="fa254-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa254-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa254-137">See also</span></span>

- [<span data-ttu-id="fa254-138">Attivazione TCP</span><span class="sxs-lookup"><span data-stu-id="fa254-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="fa254-139">Attivazione MSMQ</span><span class="sxs-lookup"><span data-stu-id="fa254-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="fa254-140">Attivazione di NamedPipe</span><span class="sxs-lookup"><span data-stu-id="fa254-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="fa254-141">Funzionalità di hosting di Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="fa254-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
