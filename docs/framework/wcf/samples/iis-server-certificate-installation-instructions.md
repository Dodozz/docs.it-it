---
title: Istruzioni di installazione certificato server IIS (Internet Information Services)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 728232c4e1d6309ae0cfacb407417173ece145da
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648355"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="2bb79-102">Istruzioni di installazione certificato server IIS (Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="2bb79-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="2bb79-103">Per eseguire gli esempi che comunicano in modo sicuro con IIS (Internet Information Services) è necessario creare e installare un certificato server.</span><span class="sxs-lookup"><span data-stu-id="2bb79-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="2bb79-104">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="2bb79-104">Step 1.</span></span> <span data-ttu-id="2bb79-105">Creazione di certificati</span><span class="sxs-lookup"><span data-stu-id="2bb79-105">Creating Certificates</span></span>  
 <span data-ttu-id="2bb79-106">Per creare un certificato per il computer locale, aprire un prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire Setup. bat incluso in ognuno degli esempi che utilizzano una comunicazione protetta con IIS.</span><span class="sxs-lookup"><span data-stu-id="2bb79-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="2bb79-107">Assicurarsi che il percorso includa la cartella contenente Makecert.exe prima di eseguire questo file batch.</span><span class="sxs-lookup"><span data-stu-id="2bb79-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="2bb79-108">Il comando seguente viene utilizzato per creare il certificato nel file Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="2bb79-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="2bb79-109">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="2bb79-109">Step 2.</span></span> <span data-ttu-id="2bb79-110">Installazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="2bb79-110">Installing Certificates</span></span>  
 <span data-ttu-id="2bb79-111">I passaggi necessari per installare i certificati appena creati dipendono dalla versione di IIS che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="2bb79-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="2bb79-112">Installazione di IIS su IIS 5.1 (Windows XP) e IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="2bb79-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1. <span data-ttu-id="2bb79-113">Aprire lo snap-in MMC della Gestione Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="2bb79-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2. <span data-ttu-id="2bb79-114">Il sito Web predefinito e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2bb79-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3. <span data-ttu-id="2bb79-115">Selezionare il **sicurezza Directory** scheda.</span><span class="sxs-lookup"><span data-stu-id="2bb79-115">Select the **Directory Security** tab.</span></span>  
  
4. <span data-ttu-id="2bb79-116">Scegliere il **certificato del Server** pulsante.</span><span class="sxs-lookup"><span data-stu-id="2bb79-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="2bb79-117">Verrà avviata la Procedura guidata certificati server Web.</span><span class="sxs-lookup"><span data-stu-id="2bb79-117">The Web Server Certificate Wizard starts.</span></span>  
  
5. <span data-ttu-id="2bb79-118">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="2bb79-118">Complete the wizard.</span></span> <span data-ttu-id="2bb79-119">Selezionare l'opzione per assegnare un certificato.</span><span class="sxs-lookup"><span data-stu-id="2bb79-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="2bb79-120">Selezionare il certificato server HTTPS ServiceModelSamples nell'elenco di certificati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="2bb79-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="2bb79-121">![IIS Gestione guidata certificati](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="2bb79-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6. <span data-ttu-id="2bb79-122">Testare l'accesso al servizio in un browser usando l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="2bb79-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="2bb79-123">Se SSL è stato precedentemente configurato utilizzando Httpcfg.exe</span><span class="sxs-lookup"><span data-stu-id="2bb79-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1. <span data-ttu-id="2bb79-124">Utilizzare Makecert.exe (o eseguire Setup.bat) per creare il certificato server.</span><span class="sxs-lookup"><span data-stu-id="2bb79-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2. <span data-ttu-id="2bb79-125">Eseguire la gestione IIS e installare il certificato secondo i passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2bb79-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3. <span data-ttu-id="2bb79-126">Aggiungere le righe di codice seguenti al programma client.</span><span class="sxs-lookup"><span data-stu-id="2bb79-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2bb79-127">Questo codice è necessario solo per certificati di prova come ad esempio quelli creati da Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="2bb79-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="2bb79-128">Non è una pratica consigliabile per il codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="2bb79-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="2bb79-129">Per installare IIS su IIS 7.0 (Windows Vista e Windows Server 2008)</span><span class="sxs-lookup"><span data-stu-id="2bb79-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1. <span data-ttu-id="2bb79-130">Dal **avviare** menu, fare clic su **eseguito**, quindi digitare **inetmgr** per aprire lo snap-in MMC di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="2bb79-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="2bb79-131">Fare doppio clic il **sito Web predefinito** e selezionare **Modifica binding...**</span><span class="sxs-lookup"><span data-stu-id="2bb79-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3. <span data-ttu-id="2bb79-132">Fare clic sui **Add** pulsante del **binding sito** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2bb79-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4. <span data-ttu-id="2bb79-133">Selezionare **HTTPS** dalle **tipo** elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2bb79-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5. <span data-ttu-id="2bb79-134">Selezionare il **ServiceModelSamples-HTTPS-Server** dalle **certificato SSL** elenco a discesa e fare clic **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb79-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6. <span data-ttu-id="2bb79-135">Testare l'accesso al servizio in un browser usando l'indirizzo HTTPS `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="2bb79-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2bb79-136">Dato che il certificato di prova appena installato non è un certificato attendibile, possono essere visualizzati avvisi di sicurezza di Internet Explorer aggiuntivi quando si visitano indirizzi Web locali protetti da questo certificato.</span><span class="sxs-lookup"><span data-stu-id="2bb79-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="2bb79-137">Rimozione dei certificati</span><span class="sxs-lookup"><span data-stu-id="2bb79-137">Removing Certificates</span></span>  
  
- <span data-ttu-id="2bb79-138">Utilizzare Gestione Internet Information Services come illustrato in precedenza, ma rimuovere il certificato o l'associazione anziché aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="2bb79-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
- <span data-ttu-id="2bb79-139">Rimuovere il certificato del computer utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2bb79-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
