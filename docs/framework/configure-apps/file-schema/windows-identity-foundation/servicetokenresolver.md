---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347514"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="58051-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="58051-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="58051-103">Registra il resolver dei token di servizio che viene usato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="58051-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="58051-104">Il resolver dei token di servizio viene usato per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="58051-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="58051-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="58051-105">\<system.identityModel></span></span>  
<span data-ttu-id="58051-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="58051-106">\<identityConfiguration></span></span>  
<span data-ttu-id="58051-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="58051-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="58051-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="58051-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="58051-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="58051-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58051-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58051-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58051-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58051-111">Attributes and Elements</span></span>  
 <span data-ttu-id="58051-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58051-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58051-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="58051-113">Attributes</span></span>  
  
|<span data-ttu-id="58051-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="58051-114">Attribute</span></span>|<span data-ttu-id="58051-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58051-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58051-116">tipo</span><span class="sxs-lookup"><span data-stu-id="58051-116">type</span></span>|<span data-ttu-id="58051-117">Specifica il tipo di resolver di token del servizio.</span><span class="sxs-lookup"><span data-stu-id="58051-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="58051-118">Entrambi i <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="58051-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="58051-119">Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="58051-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="58051-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="58051-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58051-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58051-121">Child Elements</span></span>  
 <span data-ttu-id="58051-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="58051-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58051-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58051-123">Parent Elements</span></span>  
  
|<span data-ttu-id="58051-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="58051-124">Element</span></span>|<span data-ttu-id="58051-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58051-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58051-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="58051-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="58051-127">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="58051-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58051-128">Note</span><span class="sxs-lookup"><span data-stu-id="58051-128">Remarks</span></span>  
 <span data-ttu-id="58051-129">Il resolver dei token di servizio è utilizzabile per risolvere il token di crittografia token in arrivo e messaggi.</span><span class="sxs-lookup"><span data-stu-id="58051-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="58051-130">Utilizzato per recuperare la chiave da usare per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="58051-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="58051-131">È necessario specificare il `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="58051-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="58051-132">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva dal <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="58051-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="58051-133">Alcuni gestori di token consentono di specificare le impostazioni di resolver dei token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="58051-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="58051-134">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="58051-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58051-135">Specifica la `<serviceTokenResolver>` come elemento figlio dell'elemento di [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento è stato deprecato, ma è ancora supportata per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="58051-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="58051-136">Le impostazioni nel `<securityTokenHandlerConfiguration>` elemento sostituiscono quelle di `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="58051-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58051-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="58051-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
