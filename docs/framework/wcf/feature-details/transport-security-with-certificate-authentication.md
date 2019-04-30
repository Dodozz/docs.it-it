---
title: Sicurezza del trasporto con autenticazione del certificato
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: a348fb7989a83ec9ee7903bd38896bedcf86ce3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050740"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="96fda-102">Sicurezza del trasporto con autenticazione del certificato</span><span class="sxs-lookup"><span data-stu-id="96fda-102">Transport Security with Certificate Authentication</span></span>
<span data-ttu-id="96fda-103">In questo argomento viene illustrato l'utilizzo dei certificati X.509 per l'autenticazione del server e del client con la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="96fda-103">This topic discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="96fda-104">Per altre informazioni sui certificati X.509, vedere [Certificati di chiave pubblica X.509](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span><span class="sxs-lookup"><span data-stu-id="96fda-104">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="96fda-105">I certificati devono essere emesso da un'autorità di certificazione, che spesso è un'emittente di certificati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="96fda-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="96fda-106">Nei domini Windows Server è possibile utilizzare Servizi certificati Active Directory per rilasciare certificati ai computer client del dominio.</span><span class="sxs-lookup"><span data-stu-id="96fda-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="96fda-107">Per altre informazioni, vedere [Servizi certificati di Windows 2008 R2](https://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="96fda-107">For more information see [Windows 2008 R2 Certificate Services](https://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span></span> <span data-ttu-id="96fda-108">In questo scenario, il servizio è ospitato in Internet Information Services (IIS) configurato con Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="96fda-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="96fda-109">Il servizio è configurato con un certificato SSL (X.509) per consentire ai client di verificare l'identità del server.</span><span class="sxs-lookup"><span data-stu-id="96fda-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="96fda-110">Anche il client è configurato con un certificato X.509 per consentire al servizio di verificare l'identità del client.</span><span class="sxs-lookup"><span data-stu-id="96fda-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="96fda-111">Il certificato del server deve essere ritenuto attendibile dal client e il certificato del client deve essere ritenuto attendibile dal server.</span><span class="sxs-lookup"><span data-stu-id="96fda-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="96fda-112">Il meccanismo per cui effettivamente il servizio e il client verificano le reciproche identità non rientra nell'ambito di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="96fda-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this topic.</span></span> <span data-ttu-id="96fda-113">Per altre informazioni, vedere [firma digitale in Wikipedia](https://go.microsoft.com/fwlink/?LinkId=253157).</span><span class="sxs-lookup"><span data-stu-id="96fda-113">For more information see [Digital Signature on Wikipedia](https://go.microsoft.com/fwlink/?LinkId=253157).</span></span>  
  
 <span data-ttu-id="96fda-114">Questo scenario implementa un modello di messaggio di richiesta/risposta come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="96fda-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="96fda-115">![Protezione di trasferimento basata su certificati](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="96fda-115">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="96fda-116">Per altre informazioni sull'uso di un certificato con un servizio, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) e [come: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="96fda-116">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="96fda-117">Nella tabella riportata di seguito vengono descritte le diverse caratteristiche dello scenario.</span><span class="sxs-lookup"><span data-stu-id="96fda-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="96fda-118">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="96fda-118">Characteristic</span></span>|<span data-ttu-id="96fda-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96fda-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="96fda-120">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="96fda-120">Security Mode</span></span>|<span data-ttu-id="96fda-121">Trasporto</span><span class="sxs-lookup"><span data-stu-id="96fda-121">Transport</span></span>|  
|<span data-ttu-id="96fda-122">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="96fda-122">Interoperability</span></span>|<span data-ttu-id="96fda-123">Con servizi e client di servizi Web esistenti.</span><span class="sxs-lookup"><span data-stu-id="96fda-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="96fda-124">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="96fda-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="96fda-125">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="96fda-125">Authentication (Client)</span></span>|<span data-ttu-id="96fda-126">Sì (utilizzando un certificato SSL)</span><span class="sxs-lookup"><span data-stu-id="96fda-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="96fda-127">sì (utilizzando un certificato X.509)</span><span class="sxs-lookup"><span data-stu-id="96fda-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="96fda-128">Integrità dei dati</span><span class="sxs-lookup"><span data-stu-id="96fda-128">Data Integrity</span></span>|<span data-ttu-id="96fda-129">Yes</span><span class="sxs-lookup"><span data-stu-id="96fda-129">Yes</span></span>|  
|<span data-ttu-id="96fda-130">Riservatezza dei dati</span><span class="sxs-lookup"><span data-stu-id="96fda-130">Data Confidentiality</span></span>|<span data-ttu-id="96fda-131">Yes</span><span class="sxs-lookup"><span data-stu-id="96fda-131">Yes</span></span>|  
|<span data-ttu-id="96fda-132">Trasporto</span><span class="sxs-lookup"><span data-stu-id="96fda-132">Transport</span></span>|<span data-ttu-id="96fda-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="96fda-133">HTTPS</span></span>|  
|<span data-ttu-id="96fda-134">Binding</span><span class="sxs-lookup"><span data-stu-id="96fda-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="96fda-135">Configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="96fda-135">Configure the Service</span></span>  
 <span data-ttu-id="96fda-136">Poiché il servizio in questo scenario è ospitato in IIS, viene configurato con un file web.config.</span><span class="sxs-lookup"><span data-stu-id="96fda-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="96fda-137">Nel seguente web.config viene illustrato come configurare <xref:System.ServiceModel.WSHttpBinding> per utilizzare la sicurezza del trasporto e le credenziali client X.509.</span><span class="sxs-lookup"><span data-stu-id="96fda-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>              
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>            
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="96fda-138">Configurazione del client</span><span class="sxs-lookup"><span data-stu-id="96fda-138">Configure the Client</span></span>  
 <span data-ttu-id="96fda-139">È possibile configurare il client nel codice o in un file app.config.</span><span class="sxs-lookup"><span data-stu-id="96fda-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="96fda-140">Nell'esempio riportato di seguito viene illustrato come si configura il client nel codice.</span><span class="sxs-lookup"><span data-stu-id="96fda-140">The following example shows how to configure the client in code.</span></span>  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="96fda-141">In alternativa è possibile configurare il client in un file App.config, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="96fda-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "   
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="Binding1"   
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96fda-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96fda-142">See also</span></span>

- [<span data-ttu-id="96fda-143">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="96fda-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="96fda-144">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="96fda-144">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
