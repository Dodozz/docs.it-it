---
title: '&lt;add&gt; di &lt;allowedAudienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: 2e3939f670bcb2424cfb1dfaa2b5e036bbf2888b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569007"
---
# <a name="ltaddgt-of-ltallowedaudienceurisgt"></a><span data-ttu-id="9b587-102">&lt;add&gt; di &lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="9b587-102">&lt;add&gt; of &lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="9b587-103">Aggiunge un URI di destinazione al quale il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="9b587-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="9b587-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9b587-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9b587-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9b587-105">\<behaviors></span></span>  
<span data-ttu-id="9b587-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9b587-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9b587-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9b587-107">\<behavior></span></span>  
<span data-ttu-id="9b587-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9b587-108">\<serviceCredentials></span></span>  
<span data-ttu-id="9b587-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9b587-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="9b587-110">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="9b587-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="9b587-111">\<aggiungere > (elemento) per \<allowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="9b587-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b587-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b587-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b587-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9b587-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9b587-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9b587-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b587-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="9b587-115">Attributes</span></span>  
  
|<span data-ttu-id="9b587-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="9b587-116">Attribute</span></span>|<span data-ttu-id="9b587-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b587-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b587-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="9b587-118">allowedAudienceUri</span></span>|<span data-ttu-id="9b587-119">Stringa che contiene un URI di destinazione a cui il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="9b587-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b587-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9b587-120">Child Elements</span></span>  
 <span data-ttu-id="9b587-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9b587-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b587-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9b587-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9b587-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b587-123">Element</span></span>|<span data-ttu-id="9b587-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9b587-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b587-125">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="9b587-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="9b587-126">Rappresenta una raccolta di URI di destinazione ai quali può essere destinato il token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken> può essere destinato affinché venga considerato valido da un'istanza di <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="9b587-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b587-127">Note</span><span class="sxs-lookup"><span data-stu-id="9b587-127">Remarks</span></span>  
 <span data-ttu-id="9b587-128">Usare questa raccolta in un'applicazione federata che usa un servizio token di sicurezza (STS, Security Token Service) che emette token di sicurezza <xref:System.IdentityModel.Tokens.SamlSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="9b587-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="9b587-129">Quando emette il token di sicurezza, il servizio STS può specificare l'URI dei servizi Web per cui si desidera usare il token di sicurezza tramite l'aggiunta di una condizione <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9b587-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="9b587-130">Ciò consente all'autenticatore <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> del servizio Web di destinazione di verificare che il token di sicurezza emesso sia associato a questo servizio Web specificando che questo controllo deve essere svolto mediante l'esecuzione delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b587-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="9b587-131">Impostare l'attributo `audienceUriMode` di `<issuedTokenAuthentication>` su <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> o <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span><span class="sxs-lookup"><span data-stu-id="9b587-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="9b587-132">Specificare il set di URI validi, aggiungendo gli URI a questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="9b587-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="9b587-133">Per altre informazioni, vedere <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="9b587-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="9b587-134">Per altre informazioni sull'uso di questo elemento di configurazione, vedere [come: Configurare le credenziali in un servizio federativo](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="9b587-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b587-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b587-135">See also</span></span>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="9b587-136">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="9b587-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)
- [<span data-ttu-id="9b587-137">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="9b587-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="9b587-138">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9b587-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="9b587-139">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9b587-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9b587-140">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="9b587-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
