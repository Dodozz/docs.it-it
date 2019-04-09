---
title: <security> di <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 8d79523db2a1567283b934abbd3de1adbbe6b0b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125788"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="b843c-102">\<sicurezza > di \<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="b843c-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="b843c-103">Definisce le impostazioni di sicurezza del trasporto per il canale di integrazione del servizio di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b843c-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="b843c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b843c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b843c-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="b843c-105">\<bindings></span></span>  
<span data-ttu-id="b843c-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="b843c-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="b843c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b843c-107">\<binding></span></span>  
<span data-ttu-id="b843c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="b843c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b843c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b843c-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b843c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b843c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b843c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b843c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b843c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b843c-112">Attributes</span></span>  
  
|<span data-ttu-id="b843c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b843c-113">Attribute</span></span>|<span data-ttu-id="b843c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b843c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b843c-115">modalità</span><span class="sxs-lookup"><span data-stu-id="b843c-115">mode</span></span>|<span data-ttu-id="b843c-116">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione con il canale di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="b843c-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="b843c-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="b843c-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b843c-118">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b843c-118">-   None: This disables security.</span></span><br /><span data-ttu-id="b843c-119">-Transport: Protezione e autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="b843c-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="b843c-120">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="b843c-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="b843c-121">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b843c-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="b843c-122">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b843c-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="b843c-123">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="b843c-123">The default value is `Transport`.</span></span> <span data-ttu-id="b843c-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b843c-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b843c-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b843c-125">Child Elements</span></span>  
  
|<span data-ttu-id="b843c-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b843c-126">Element</span></span>|<span data-ttu-id="b843c-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b843c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b843c-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="b843c-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="b843c-129">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="b843c-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="b843c-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b843c-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b843c-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b843c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b843c-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="b843c-132">Element</span></span>|<span data-ttu-id="b843c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b843c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b843c-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="b843c-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b843c-135">L'elemento di associazione del [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b843c-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b843c-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b843c-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="b843c-137">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="b843c-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="b843c-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="b843c-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b843c-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="b843c-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b843c-140">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="b843c-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b843c-141">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="b843c-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b843c-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="b843c-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="b843c-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="b843c-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
