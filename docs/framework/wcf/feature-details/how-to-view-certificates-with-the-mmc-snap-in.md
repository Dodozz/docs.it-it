---
title: 'Procedura: Visualizzare i certificati con lo Snap-in MMC'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 72fd6a1be2f33e1bfeb08fd43f3436627ee842e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521582"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="675e4-102">Procedura: Visualizzare i certificati con lo Snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="675e4-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="675e4-103">Un tipo comune di credenziale è il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="675e4-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="675e4-104">Al momento di creare servizi o client protetti, è possibile specificare il certificato che deve essere utilizzato come credenziale client o del servizio tramite metodi come, ad esempio, <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="675e4-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="675e4-105">Il metodo richiede vari parametri, ad esempio l'archivio in cui il certificato è memorizzato e un valore da utilizzare quando si cerca il certificato.</span><span class="sxs-lookup"><span data-stu-id="675e4-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="675e4-106">Nella procedura seguente viene illustrato come esaminare gli archivi in un computer per trovare un certificato adatto.</span><span class="sxs-lookup"><span data-stu-id="675e4-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="675e4-107">Per un esempio di ricerca l'identificazione personale del certificato, vedere [come: Recuperare l'identificazione personale di un certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="675e4-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="675e4-108">Per visualizzare certificati nello snap-in MMC</span><span class="sxs-lookup"><span data-stu-id="675e4-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="675e4-109">Aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="675e4-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="675e4-110">Tipo `mmc` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="675e4-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="675e4-111">Si noti che per visualizzare certificati nell'archivio del computer locale, è necessario avere il ruolo di Amministratore.</span><span class="sxs-lookup"><span data-stu-id="675e4-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="675e4-112">Nel **File** menu, fare clic su **Aggiungi/Rimuovi snap-In**.</span><span class="sxs-lookup"><span data-stu-id="675e4-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="675e4-113">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="675e4-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="675e4-114">Nel **Aggiungi Snap-in Standalone** finestra di dialogo **certificati**.</span><span class="sxs-lookup"><span data-stu-id="675e4-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="675e4-115">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="675e4-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="675e4-116">Nel **snap-in certificati** finestra di dialogo **account Computer** e fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="675e4-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="675e4-117">Facoltativamente, è possibile selezionare **account dell'utente** oppure **account del servizio**.</span><span class="sxs-lookup"><span data-stu-id="675e4-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="675e4-118">Se non si è un amministratore del computer, è possibile gestire i certificati solo per il proprio account utente.</span><span class="sxs-lookup"><span data-stu-id="675e4-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="675e4-119">Nel **seleziona Computer** finestra di dialogo, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="675e4-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="675e4-120">Nel **Aggiungi Snap-in Standalone** finestra di dialogo, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="675e4-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="675e4-121">Nel **Aggiungi/Rimuovi Snap-in** finestra di dialogo, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="675e4-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="675e4-122">Nel **radice Console** finestra, fare clic su **certificati (Computer locale)** per visualizzare i certificati vengono archiviati per il computer.</span><span class="sxs-lookup"><span data-stu-id="675e4-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="675e4-123">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="675e4-123">Optional.</span></span> <span data-ttu-id="675e4-124">Per visualizzare i certificati per il proprio account, ripetere i passaggi da 3 a 6.</span><span class="sxs-lookup"><span data-stu-id="675e4-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="675e4-125">Nel passaggio 7, anziché selezionare **account Computer**, fare clic su **account dell'utente** e ripetere i passaggi da 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="675e4-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="675e4-126">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="675e4-126">Optional.</span></span> <span data-ttu-id="675e4-127">Nel **File** menu, fare clic su **salvare** oppure **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="675e4-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="675e4-128">Salvare il file di console per riutilizzarlo in seguito.</span><span class="sxs-lookup"><span data-stu-id="675e4-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="675e4-129">Visualizzazione di certificati con Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="675e4-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="675e4-130">È anche possibile visualizzare, esportare, importare ed eliminare certificati utilizzando Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="675e4-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="675e4-131">Per visualizzare certificati con Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="675e4-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="675e4-132">In Internet Explorer, fare clic su **degli strumenti**, quindi fare clic su **Opzioni Internet** per visualizzare il **Opzioni Internet** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="675e4-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="675e4-133">Scegliere il **contenuto** scheda.</span><span class="sxs-lookup"><span data-stu-id="675e4-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="675e4-134">Sotto **certificati**, fare clic su **certificati**.</span><span class="sxs-lookup"><span data-stu-id="675e4-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="675e4-135">Per visualizzare i dettagli di qualsiasi certificato, selezionare il certificato e fare clic su **vista**.</span><span class="sxs-lookup"><span data-stu-id="675e4-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675e4-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="675e4-136">See also</span></span>
- [<span data-ttu-id="675e4-137">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="675e4-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="675e4-138">Procedura: Creare certificati temporanei da usare durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="675e4-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="675e4-139">Procedura: Recuperare l'identificazione personale di un certificato</span><span class="sxs-lookup"><span data-stu-id="675e4-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
