---
title: '&lt;security&gt; di &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: a7bb6816c5b34e608b5010aba308ccd9d870d398
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145903"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="8c5d9-102">&lt;security&gt; di &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8c5d9-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="8c5d9-103">Rappresenta le impostazioni di sicurezza utilizzate con il [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="8c5d9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c5d9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8c5d9-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="8c5d9-105">\<bindings></span></span>  
<span data-ttu-id="8c5d9-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="8c5d9-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="8c5d9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c5d9-107">\<binding></span></span>  
<span data-ttu-id="8c5d9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8c5d9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5d9-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c5d9-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c5d9-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8c5d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c5d9-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c5d9-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8c5d9-112">Attributes</span></span>  
  
|<span data-ttu-id="8c5d9-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8c5d9-113">Attribute</span></span>|<span data-ttu-id="8c5d9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c5d9-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="8c5d9-115">-Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-115">-   Optional.</span></span> <span data-ttu-id="8c5d9-116">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="8c5d9-117">Il valore predefinito è `Message`.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="8c5d9-118">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="8c5d9-119">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="8c5d9-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="8c5d9-120">Valore</span><span class="sxs-lookup"><span data-stu-id="8c5d9-120">Value</span></span>|<span data-ttu-id="8c5d9-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c5d9-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="8c5d9-122">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="8c5d9-123">La sicurezza è fornita mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="8c5d9-124">Il servizio deve essere configurato con certificati Secure Sockets Layer (SSL).</span><span class="sxs-lookup"><span data-stu-id="8c5d9-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="8c5d9-125">Il messaggio è interamente protetto usando HTTPS e il servizio viene autenticato dal client usando il certificato SSL del servizio.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="8c5d9-126">L'autenticazione client è controllata tramite il `ClientCredentials` attributo del [ \<trasporto >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="8c5d9-127">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="8c5d9-128">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="8c5d9-129">Questa modalità offre varie funzionalità: è ad esempio possibile stabilire se le credenziali del servizio sono disponibili per i client fuori banda nonché specificare la suite di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio tramite la proprietà <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="8c5d9-130">L'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="8c5d9-131">In questa modalità, HTTPS fornisce l'integrità, la riservatezza e l'autenticazione server e client, mentre la sicurezza dei messaggi SOAP fornisce l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="8c5d9-132">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per ogni sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c5d9-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c5d9-133">Child Elements</span></span>  
  
|<span data-ttu-id="8c5d9-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c5d9-134">Element</span></span>|<span data-ttu-id="8c5d9-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c5d9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c5d9-136">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="8c5d9-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="8c5d9-137">Definisce le impostazioni di sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-137">Defines the transport security settings.</span></span> <span data-ttu-id="8c5d9-138">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="8c5d9-139">Queste impostazioni vengono applicate solo quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="8c5d9-140">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="8c5d9-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="8c5d9-141">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-141">Defines the security settings for the message.</span></span> <span data-ttu-id="8c5d9-142">Questo elemento corrisponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="8c5d9-143">Queste impostazioni non vengono applicate quando la modalità è impostata su Transport.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c5d9-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8c5d9-144">Parent Elements</span></span>  
  
|<span data-ttu-id="8c5d9-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c5d9-145">Element</span></span>|<span data-ttu-id="8c5d9-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c5d9-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c5d9-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="8c5d9-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="8c5d9-148">Associazione protetta per applicazioni di trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c5d9-149">Note</span><span class="sxs-lookup"><span data-stu-id="8c5d9-149">Remarks</span></span>  
 <span data-ttu-id="8c5d9-150">Questo elemento è progettato per essere interoperabile con i servizi che implementano le specifiche WS-\*.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="8c5d9-151">La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5d9-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c5d9-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="8c5d9-153">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="8c5d9-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8c5d9-154">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8c5d9-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8c5d9-155">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="8c5d9-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8c5d9-156">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="8c5d9-156">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="8c5d9-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="8c5d9-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
