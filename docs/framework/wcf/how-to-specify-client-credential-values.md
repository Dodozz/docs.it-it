---
title: 'Procedura: Specificare valori di credenziali client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: ecb8f7ef74f1f0625454eb2d6cebf9d282a5ece3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327100"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="d0020-102">Procedura: Specificare valori di credenziali client</span><span class="sxs-lookup"><span data-stu-id="d0020-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="d0020-103">Utilizza Windows Communication Foundation (WCF), il servizio può specificare come un client viene autenticato nel servizio.</span><span class="sxs-lookup"><span data-stu-id="d0020-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="d0020-104">Ad esempio, un servizio può stabilire che il client venga autenticato con un certificato.</span><span class="sxs-lookup"><span data-stu-id="d0020-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="d0020-105">Per determinare il tipo di credenziale client</span><span class="sxs-lookup"><span data-stu-id="d0020-105">To determine the client credential type</span></span>  
  
1. <span data-ttu-id="d0020-106">Recuperare i metadati dall'endpoint dei metadati di servizio.</span><span class="sxs-lookup"><span data-stu-id="d0020-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="d0020-107">I metadati sono in genere costituiti da due file: il codice client del linguaggio di programmazione selezionato (l'impostazione predefinita è Visual C#) e un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="d0020-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="d0020-108">Un modo per recuperare i metadati consiste nell'utilizzare lo strumento Svcutil.exe per restituire il codice e la configurazione client.</span><span class="sxs-lookup"><span data-stu-id="d0020-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="d0020-109">Per altre informazioni, vedere [recupero di metadati](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) e [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d0020-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2. <span data-ttu-id="d0020-110">Aprire il file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="d0020-110">Open the XML configuration file.</span></span> <span data-ttu-id="d0020-111">Se si utilizza lo strumento Svcutil.exe, il nome predefinito del file è Output.config.</span><span class="sxs-lookup"><span data-stu-id="d0020-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3. <span data-ttu-id="d0020-112">Trovare il  **\<sicurezza >** elemento con il **modalità** attributo (**< modalità di sicurezza =** `MessageOrTransport` **>** in cui `MessageOrTransport` è impostato su una delle modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d0020-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4. <span data-ttu-id="d0020-113">Trovare l'elemento figlio che corrisponda al valore della modalità.</span><span class="sxs-lookup"><span data-stu-id="d0020-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="d0020-114">Ad esempio, se la modalità è impostata su **messaggi**, trovare il  **\<messaggio >** elemento contenuto nel  **\<sicurezza >** elemento.</span><span class="sxs-lookup"><span data-stu-id="d0020-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5. <span data-ttu-id="d0020-115">Si noti il valore assegnato per il **clientCredentialType** attributo.</span><span class="sxs-lookup"><span data-stu-id="d0020-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="d0020-116">Il valore effettivo dipende dalla modalità utilizzata, trasporto o messaggio.</span><span class="sxs-lookup"><span data-stu-id="d0020-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="d0020-117">Nel codice XML seguente viene mostrata la configurazione di un client per cui viene utilizzata la sicurezza dei messaggi e viene richiesto un certificato per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d0020-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="d0020-118">Esempio: Modalità di trasporto TCP con certificato come credenziale Client</span><span class="sxs-lookup"><span data-stu-id="d0020-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="d0020-119">In questo esempio la modalità di sicurezza viene impostata sulla modalità Trasporto e il valore delle credenziali client su un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="d0020-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="d0020-120">Nelle procedure seguenti viene descritto come impostare il valore delle credenziali client sul client nel codice e nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0020-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="d0020-121">Ciò presuppone che sia stato usato il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per restituire i metadati (codice e configurazione) dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d0020-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="d0020-122">Per altre informazioni, vedere [Procedura: Creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="d0020-122">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="d0020-123">Per specificare il valore delle credenziali client nel client nel codice</span><span class="sxs-lookup"><span data-stu-id="d0020-123">To specify the client credential value on the client in code</span></span>  
  
1. <span data-ttu-id="d0020-124">Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il codice e la configurazione dal servizio.</span><span class="sxs-lookup"><span data-stu-id="d0020-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2. <span data-ttu-id="d0020-125">Creare un'istanza del client WCF usando il codice generato.</span><span class="sxs-lookup"><span data-stu-id="d0020-125">Create an instance of the WCF client using the generated code.</span></span>  
  
3. <span data-ttu-id="d0020-126">Nella classe del client impostare la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d0020-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="d0020-127">In questo esempio la proprietà viene impostata su un certificato X.509 utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="d0020-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="d0020-128">È possibile utilizzare qualsiasi enumerazione della classe <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="d0020-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="d0020-129">Il nome del soggetto viene qui utilizzato nel caso in cui il certificato venga modificato (a causa di una data di scadenza).</span><span class="sxs-lookup"><span data-stu-id="d0020-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="d0020-130">L'utilizzo del nome del soggetto consente all'infrastruttura di cercare nuovamente il certificato.</span><span class="sxs-lookup"><span data-stu-id="d0020-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="d0020-131">Per specificare il valore delle credenziali client nel client nella configurazione</span><span class="sxs-lookup"><span data-stu-id="d0020-131">To specify the client credential value on the client in configuration</span></span>  
  
1. <span data-ttu-id="d0020-132">Aggiungere un [ \<comportamento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d0020-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2. <span data-ttu-id="d0020-133">Aggiungere un [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d0020-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="d0020-134">Avere cura di impostare l'attributo `name` obbligatorio su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d0020-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="d0020-135">Aggiungere un [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento per il [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d0020-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4. <span data-ttu-id="d0020-136">Impostare gli attributi seguenti sui valori appropriati: `storeLocation`, `storeName`, `x509FindType` e `findValue`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d0020-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="d0020-137">Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d0020-137">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5. <span data-ttu-id="d0020-138">Quando si configura il client, specificare il comportamento impostando l'attributo `behaviorConfiguration` dell'elemento `<endpoint>`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d0020-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="d0020-139">L'elemento endpoint è figlio di [ \<client >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d0020-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="d0020-140">Specificare inoltre il nome della configurazione dell'associazione impostando l'attributo `bindingConfiguration` sull'associazione per il client.</span><span class="sxs-lookup"><span data-stu-id="d0020-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="d0020-141">Se si utilizza un file di configurazione generato, il nome dell'associazione viene generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d0020-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="d0020-142">In questo esempio il nome è `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="d0020-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d0020-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0020-143">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="d0020-144">Programmazione delle funzionalità di sicurezza di WCF</span><span class="sxs-lookup"><span data-stu-id="d0020-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [<span data-ttu-id="d0020-145">Selezione di un tipo di credenziale</span><span class="sxs-lookup"><span data-stu-id="d0020-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="d0020-146">Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="d0020-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="d0020-147">Uso di certificati</span><span class="sxs-lookup"><span data-stu-id="d0020-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d0020-148">Procedura: Creare un Client</span><span class="sxs-lookup"><span data-stu-id="d0020-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="d0020-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="d0020-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)
- [<span data-ttu-id="d0020-150">\<security></span><span class="sxs-lookup"><span data-stu-id="d0020-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [<span data-ttu-id="d0020-151">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="d0020-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [<span data-ttu-id="d0020-152">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d0020-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [<span data-ttu-id="d0020-153">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="d0020-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
- [<span data-ttu-id="d0020-154">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="d0020-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [<span data-ttu-id="d0020-155">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d0020-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
