---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: c9856dae971691baf9dabe845bdecae90cbc8aa5
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2018
ms.locfileid: "49314853"
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="4b309-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="4b309-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="4b309-103">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="4b309-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="4b309-104">Rappresentato dal <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe.</span><span class="sxs-lookup"><span data-stu-id="4b309-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="4b309-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4b309-105">\<system.identityModel></span></span>  
<span data-ttu-id="4b309-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4b309-106">\<identityConfiguration></span></span>  
<span data-ttu-id="4b309-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4b309-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4b309-108">\<add></span><span class="sxs-lookup"><span data-stu-id="4b309-108">\<add></span></span>  
<span data-ttu-id="4b309-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="4b309-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b309-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b309-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b309-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b309-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4b309-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b309-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b309-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b309-113">Attributes</span></span>  
  
|<span data-ttu-id="4b309-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="4b309-114">Attribute</span></span>|<span data-ttu-id="4b309-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b309-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b309-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="4b309-116">mapToWindows</span></span>|<span data-ttu-id="4b309-117">Specifica se il gestore di token deve mappare il token di convalida a un account di Windows usando l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4b309-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="4b309-118">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="4b309-118">The default is "false".</span></span>|  
|<span data-ttu-id="4b309-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="4b309-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="4b309-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="4b309-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="4b309-121">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="4b309-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="4b309-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="4b309-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="4b309-123">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="4b309-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="4b309-124">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="4b309-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="4b309-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="4b309-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="4b309-126">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="4b309-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="4b309-127">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="4b309-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="4b309-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="4b309-128">issuerCertificateValidator</span></span>|<span data-ttu-id="4b309-129">Un tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="4b309-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="4b309-130">Se il `issuerCertificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene usata per la convalida del certificato dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="4b309-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b309-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b309-131">Child Elements</span></span>  
  
|<span data-ttu-id="4b309-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b309-132">Element</span></span>|<span data-ttu-id="4b309-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b309-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b309-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="4b309-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="4b309-135">Imposta il tipo di attestazione che specifica il <xref:System.Security.Principal.IIdentity.Name%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b309-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="4b309-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="4b309-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="4b309-137">Specifica il tipo di attestazione che definisce le attestazioni di tipo ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dai <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="4b309-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b309-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b309-138">Parent Elements</span></span>  
  
|<span data-ttu-id="4b309-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b309-139">Element</span></span>|<span data-ttu-id="4b309-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b309-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b309-141">\<add></span><span class="sxs-lookup"><span data-stu-id="4b309-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="4b309-142">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="4b309-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b309-143">Note</span><span class="sxs-lookup"><span data-stu-id="4b309-143">Remarks</span></span>  
 <span data-ttu-id="4b309-144">Il `<samlSecurityTokenRequirement>` elemento è rappresentato dal <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe nel modello a oggetti e viene usato per configurare il `SamlSecurityTokenRequirement` proprietà in un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o un <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="4b309-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b309-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b309-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
