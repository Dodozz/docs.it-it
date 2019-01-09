---
title: '&lt;security&gt; di &lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: a0c6e016980b5a40d74b9bd94dab96a0aa9fb243
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145276"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="990be-102">&lt;security&gt; di &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="990be-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="990be-103">Definisce le impostazioni di sicurezza del trasporto per il canale di integrazione del servizio di accodamento messaggi (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="990be-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="990be-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="990be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="990be-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="990be-105">\<bindings></span></span>  
<span data-ttu-id="990be-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="990be-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="990be-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="990be-107">\<binding></span></span>  
<span data-ttu-id="990be-108">\<security></span><span class="sxs-lookup"><span data-stu-id="990be-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="990be-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="990be-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="990be-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="990be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="990be-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="990be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="990be-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="990be-112">Attributes</span></span>  
  
|<span data-ttu-id="990be-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="990be-113">Attribute</span></span>|<span data-ttu-id="990be-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="990be-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="990be-115">modalità</span><span class="sxs-lookup"><span data-stu-id="990be-115">mode</span></span>|<span data-ttu-id="990be-116">Specifica il tipo di sicurezza che controlla integrità, riservatezza e autenticazione con il canale di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="990be-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="990be-117">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="990be-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="990be-118">-None: Disabilita la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="990be-118">-   None: This disables security.</span></span><br /><span data-ttu-id="990be-119">-Transport: Protezione e autenticazione sono offerte dal trasporto.</span><span class="sxs-lookup"><span data-stu-id="990be-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="990be-120">Si applica alla sicurezza del messaggio tra i due gestori delle code.</span><span class="sxs-lookup"><span data-stu-id="990be-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="990be-121">Tra l'applicazione e il gestore della coda non viene offerta alcuna sicurezza.</span><span class="sxs-lookup"><span data-stu-id="990be-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="990be-122">Le applicazioni Msmq esistenti sono funzionalmente equivalenti con questo tipo di modalità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="990be-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="990be-123">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="990be-123">The default value is `Transport`.</span></span> <span data-ttu-id="990be-124">L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="990be-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="990be-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="990be-125">Child Elements</span></span>  
  
|<span data-ttu-id="990be-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="990be-126">Element</span></span>|<span data-ttu-id="990be-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="990be-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="990be-128">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="990be-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="990be-129">Definisce le impostazioni di sicurezza per il trasporto di integrazione di Accodamento messaggi.</span><span class="sxs-lookup"><span data-stu-id="990be-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="990be-130">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="990be-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="990be-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="990be-131">Parent Elements</span></span>  
  
|<span data-ttu-id="990be-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="990be-132">Element</span></span>|<span data-ttu-id="990be-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="990be-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="990be-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="990be-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="990be-135">L'elemento di associazione del [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="990be-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="990be-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="990be-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="990be-137">Code in WCF</span><span class="sxs-lookup"><span data-stu-id="990be-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="990be-138">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="990be-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="990be-139">Associazioni</span><span class="sxs-lookup"><span data-stu-id="990be-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="990be-140">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="990be-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="990be-141">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="990be-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="990be-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="990be-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="990be-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="990be-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)
