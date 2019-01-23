---
title: '&lt;issuedToken&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: ca2e1db2c9894163c113541ac4366c638d0e1df0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501533"
---
# <a name="ltissuedtokengt"></a><span data-ttu-id="7d017-102">&lt;issuedToken&gt;</span><span class="sxs-lookup"><span data-stu-id="7d017-102">&lt;issuedToken&gt;</span></span>
<span data-ttu-id="7d017-103">Specifica un token personalizzato usato per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7d017-103">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="7d017-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7d017-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d017-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7d017-105">\<behaviors></span></span>  
<span data-ttu-id="7d017-106">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="7d017-106">endpointBehaviors section</span></span>  
<span data-ttu-id="7d017-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7d017-107">\<behavior></span></span>  
<span data-ttu-id="7d017-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7d017-108">\<clientCredentials></span></span>  
<span data-ttu-id="7d017-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="7d017-109">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d017-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d017-110">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d017-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d017-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7d017-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d017-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d017-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d017-113">Attributes</span></span>  
  
|<span data-ttu-id="7d017-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d017-114">Attribute</span></span>|<span data-ttu-id="7d017-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d017-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="7d017-116">Attributo booleano facoltativo che specifica se i token vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="7d017-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="7d017-117">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="7d017-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="7d017-118">Attributo stringa facoltativo che specifica quali valori casuali (entropie) sono usati per le operazioni di handshake.</span><span class="sxs-lookup"><span data-stu-id="7d017-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="7d017-119">I valori comprendono `ClientEntropy`, `ServerEntropy` e `CombinedEntropy`. Il valore predefinito `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="7d017-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="7d017-120">L'attributo è di tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="7d017-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="7d017-121">Attributo intero facoltativo che specifica la percentuale di un intervallo di tempo valido (fornito dall'emittente del token) che può trascorrere prima che un token venga rinnovato.</span><span class="sxs-lookup"><span data-stu-id="7d017-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="7d017-122">I valori sono compresi tra 0 e 100.</span><span class="sxs-lookup"><span data-stu-id="7d017-122">Values are from 0 to 100.</span></span> <span data-ttu-id="7d017-123">Il valore predefinito è 60 e indica che una volta trascorso il 60% dell'intervallo di tempo il sistema esegue un tentativo di rinnovo.</span><span class="sxs-lookup"><span data-stu-id="7d017-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="7d017-124">Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente.</span><span class="sxs-lookup"><span data-stu-id="7d017-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="7d017-125">Attributo facoltativo che specifica i comportamenti di canale da usare quando si comunica con l'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7d017-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="7d017-126">Attributo Timespan facoltativo che, quando l'emittente del token (un servizio token di sicurezza) non specifica alcun intervallo, definisce la durata di memorizzazione nella cache dei token emessi.</span><span class="sxs-lookup"><span data-stu-id="7d017-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="7d017-127">Il valore predefinito è "10675199.02:48:05.4775807."</span><span class="sxs-lookup"><span data-stu-id="7d017-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d017-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d017-128">Child Elements</span></span>  
  
|<span data-ttu-id="7d017-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d017-129">Element</span></span>|<span data-ttu-id="7d017-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d017-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d017-131">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="7d017-131">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="7d017-132">Specifica l'indirizzo dell'emittente locale del token e l'associazione usata per comunicare con l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7d017-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="7d017-133">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="7d017-133">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="7d017-134">Specifica i comportamenti di endpoint da usare quando si contatta un'emittente locale.</span><span class="sxs-lookup"><span data-stu-id="7d017-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d017-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d017-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7d017-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d017-136">Element</span></span>|<span data-ttu-id="7d017-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d017-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d017-138">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="7d017-138">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="7d017-139">Specifica le credenziali usate per autenticare un client presso un servizio.</span><span class="sxs-lookup"><span data-stu-id="7d017-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d017-140">Note</span><span class="sxs-lookup"><span data-stu-id="7d017-140">Remarks</span></span>  
 <span data-ttu-id="7d017-141">Un token emesso è un tipo di credenziale personalizzato usato, ad esempio, quando si esegue l'autenticazione con un servizio token di sicurezza in uno scenario federato.</span><span class="sxs-lookup"><span data-stu-id="7d017-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="7d017-142">Per impostazione predefinita, il token è un token SAML.</span><span class="sxs-lookup"><span data-stu-id="7d017-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="7d017-143">Per altre informazioni, vedere [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="7d017-143">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="7d017-144">e [federazione e token emessi](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="7d017-144">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="7d017-145">Questa sezione contiene gli elementi usati per configurare un'autorità emittente locale di token oppure i comportamenti usati in un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7d017-145">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="7d017-146">Per istruzioni su come configurare un client di utilizzare un emittente locale, vedere [come: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="7d017-146">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d017-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d017-147">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="7d017-148">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7d017-148">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7d017-149">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="7d017-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7d017-150">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7d017-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="7d017-151">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="7d017-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="7d017-152">Procedura: Creare un Client federato</span><span class="sxs-lookup"><span data-stu-id="7d017-152">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="7d017-153">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="7d017-153">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="7d017-154">Federazione e token rilasciati</span><span class="sxs-lookup"><span data-stu-id="7d017-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
