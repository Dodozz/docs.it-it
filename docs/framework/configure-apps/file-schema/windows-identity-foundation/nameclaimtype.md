---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: bd4033b2edea7450b66c25f446669b3ded65e9af
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123163"
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="76b79-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="76b79-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="76b79-103">Imposta il tipo di attestazione che specifica il <xref:System.Security.Principal.IIdentity.Name%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="76b79-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="76b79-104">Il tipo di attestazione viene usato per cercare un <xref:System.Security.Claims.Claim> nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> gli oggetti restituiti dai <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo di questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="76b79-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="76b79-105">Il valore dell'attestazione corrisponda viene impostato come il nome del <xref:System.Security.Principal.IIdentity> generati da questo gestore di token.</span><span class="sxs-lookup"><span data-stu-id="76b79-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="76b79-106">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="76b79-106">\<system.identityModel></span></span>  
<span data-ttu-id="76b79-107">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="76b79-107">\<identityConfiguration></span></span>  
<span data-ttu-id="76b79-108">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="76b79-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="76b79-109">\<add></span><span class="sxs-lookup"><span data-stu-id="76b79-109">\<add></span></span>  
<span data-ttu-id="76b79-110">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="76b79-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="76b79-111">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="76b79-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76b79-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76b79-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76b79-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="76b79-113">Attributes and Elements</span></span>  
 <span data-ttu-id="76b79-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="76b79-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76b79-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="76b79-115">Attributes</span></span>  
  
|<span data-ttu-id="76b79-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="76b79-116">Attribute</span></span>|<span data-ttu-id="76b79-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76b79-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76b79-118">predefinito</span><span class="sxs-lookup"><span data-stu-id="76b79-118">value</span></span>|<span data-ttu-id="76b79-119">Stringa che specifica l'URI che rappresenta il tipo di attestazione dell'attestazione da utilizzare per il <xref:System.Security.Principal.IIdentity.Name%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="76b79-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="76b79-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="76b79-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76b79-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="76b79-121">Child Elements</span></span>  
 <span data-ttu-id="76b79-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="76b79-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76b79-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="76b79-123">Parent Elements</span></span>  
  
|<span data-ttu-id="76b79-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="76b79-124">Element</span></span>|<span data-ttu-id="76b79-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="76b79-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76b79-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="76b79-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="76b79-127">Fornisce la configurazione per il <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (classe), il <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="76b79-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76b79-128">Note</span><span class="sxs-lookup"><span data-stu-id="76b79-128">Remarks</span></span>  
 <span data-ttu-id="76b79-129">Il `<nameClaimType>` set di elementi che il <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> proprietà quando un <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> oggetto viene inizializzato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="76b79-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76b79-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="76b79-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76b79-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76b79-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
