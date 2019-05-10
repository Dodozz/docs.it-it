---
title: Protezione dei messaggi con un client Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 36193090349f5b8ddb07ee7c3c6c663621cc6d06
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637844"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="15c39-102">Protezione dei messaggi con un client Windows</span><span class="sxs-lookup"><span data-stu-id="15c39-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="15c39-103">Questo scenario viene illustrato un client Windows Communication Foundation (WCF) e un server protetto dalla modalità di sicurezza messaggio.</span><span class="sxs-lookup"><span data-stu-id="15c39-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="15c39-104">Il client e il servizio vengono autenticati utilizzando le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="15c39-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="15c39-105">![Sicurezza con un client di Windows del messaggio](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="15c39-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="15c39-106">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="15c39-106">Characteristic</span></span>|<span data-ttu-id="15c39-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15c39-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="15c39-108">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="15c39-108">Security Mode</span></span>|<span data-ttu-id="15c39-109">Messaggio</span><span class="sxs-lookup"><span data-stu-id="15c39-109">Message</span></span>|  
|<span data-ttu-id="15c39-110">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="15c39-110">Interoperability</span></span>|<span data-ttu-id="15c39-111">Solo WCF</span><span class="sxs-lookup"><span data-stu-id="15c39-111">WCF Only</span></span>|  
|<span data-ttu-id="15c39-112">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="15c39-112">Authentication (Server)</span></span>|<span data-ttu-id="15c39-113">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="15c39-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="15c39-114">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="15c39-114">Authentication (Client)</span></span>|<span data-ttu-id="15c39-115">Autenticazione reciproca del server e del client</span><span class="sxs-lookup"><span data-stu-id="15c39-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="15c39-116">Integrità</span><span class="sxs-lookup"><span data-stu-id="15c39-116">Integrity</span></span>|<span data-ttu-id="15c39-117">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="15c39-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="15c39-118">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="15c39-118">Confidentiality</span></span>|<span data-ttu-id="15c39-119">Sì, usando un contesto di sicurezza condiviso</span><span class="sxs-lookup"><span data-stu-id="15c39-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="15c39-120">Trasporto</span><span class="sxs-lookup"><span data-stu-id="15c39-120">Transport</span></span>|<span data-ttu-id="15c39-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="15c39-121">NET.TCP</span></span>|  
|<span data-ttu-id="15c39-122">Binding</span><span class="sxs-lookup"><span data-stu-id="15c39-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="15c39-123">Service</span><span class="sxs-lookup"><span data-stu-id="15c39-123">Service</span></span>  
 <span data-ttu-id="15c39-124">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="15c39-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="15c39-125">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15c39-125">Do one of the following:</span></span>  
  
- <span data-ttu-id="15c39-126">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="15c39-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="15c39-127">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="15c39-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="15c39-128">Codice</span><span class="sxs-lookup"><span data-stu-id="15c39-128">Code</span></span>  
 <span data-ttu-id="15c39-129">Nel codice seguente viene illustrato come creare un endpoint del servizio che utilizza la protezione dei messaggi per stabilire un contesto protetto con un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="15c39-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="15c39-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="15c39-130">Configuration</span></span>  
 <span data-ttu-id="15c39-131">Per configurare il servizio, è possibile utilizzare la configurazione seguente anziché il codice:</span><span class="sxs-lookup"><span data-stu-id="15c39-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="15c39-132">Client</span><span class="sxs-lookup"><span data-stu-id="15c39-132">Client</span></span>  
 <span data-ttu-id="15c39-133">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="15c39-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="15c39-134">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15c39-134">Do one of the following:</span></span>  
  
- <span data-ttu-id="15c39-135">Creare un client autonomo usando il codice (e il codice client).</span><span class="sxs-lookup"><span data-stu-id="15c39-135">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="15c39-136">Creare un client che non definisce alcun indirizzo di endpoint.</span><span class="sxs-lookup"><span data-stu-id="15c39-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="15c39-137">Usare invece il costruttore client che accetta il nome della configurazione come argomento.</span><span class="sxs-lookup"><span data-stu-id="15c39-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="15c39-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="15c39-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="15c39-139">Codice</span><span class="sxs-lookup"><span data-stu-id="15c39-139">Code</span></span>  
 <span data-ttu-id="15c39-140">Il codice seguente crea un client.</span><span class="sxs-lookup"><span data-stu-id="15c39-140">The following code creates a client.</span></span> <span data-ttu-id="15c39-141">L'associazione riguarda la protezione della modalità messaggio e il tipo di credenziale client è impostato su `Windows`.</span><span class="sxs-lookup"><span data-stu-id="15c39-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="15c39-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="15c39-142">Configuration</span></span>  
 <span data-ttu-id="15c39-143">Per impostare le proprietà client viene utilizzata la configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="15c39-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15c39-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c39-144">See also</span></span>

- [<span data-ttu-id="15c39-145">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="15c39-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="15c39-146">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="15c39-146">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
