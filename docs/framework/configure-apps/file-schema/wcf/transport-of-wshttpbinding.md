---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: ea025751020d6d98292f6bc3ecfe9421af0cb793
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788219"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="d54b9-102">\<Transport > di \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d54b9-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="d54b9-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="d54b9-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="d54b9-104">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="d54b9-104">\<system.serviceModel>\\</span></span>
<span data-ttu-id="d54b9-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="d54b9-105">\<bindings>\\</span></span>
<span data-ttu-id="d54b9-106">\<wsHttpBinding>\\</span><span class="sxs-lookup"><span data-stu-id="d54b9-106">\<wsHttpBinding>\\</span></span>
<span data-ttu-id="d54b9-107">\<binding>\\</span><span class="sxs-lookup"><span data-stu-id="d54b9-107">\<binding>\\</span></span>
<span data-ttu-id="d54b9-108">\<sicurezza > \\</span><span class="sxs-lookup"><span data-stu-id="d54b9-108">\<security>\\</span></span>
<span data-ttu-id="d54b9-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="d54b9-109">\<transport></span></span>

## <a name="syntax"></a><span data-ttu-id="d54b9-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d54b9-110">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="d54b9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d54b9-111">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="d54b9-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d54b9-112">Attributes and Elements</span></span>

<span data-ttu-id="d54b9-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d54b9-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d54b9-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d54b9-114">Attributes</span></span>

|<span data-ttu-id="d54b9-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="d54b9-115">Attribute</span></span>|<span data-ttu-id="d54b9-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d54b9-116">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="d54b9-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="d54b9-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="d54b9-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d54b9-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="d54b9-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="d54b9-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="d54b9-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d54b9-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="d54b9-121">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="d54b9-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="d54b9-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d54b9-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d54b9-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d54b9-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="d54b9-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="d54b9-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="d54b9-125">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="d54b9-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="d54b9-126">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="d54b9-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="d54b9-127">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d54b9-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="d54b9-128">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="d54b9-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="d54b9-129">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="d54b9-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="d54b9-130">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d54b9-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d54b9-131">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d54b9-131">clientCredentialType Attribute</span></span>

|<span data-ttu-id="d54b9-132">Value</span><span class="sxs-lookup"><span data-stu-id="d54b9-132">Value</span></span>|<span data-ttu-id="d54b9-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d54b9-133">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="d54b9-134">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d54b9-134">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="d54b9-135">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d54b9-135">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="d54b9-136">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d54b9-136">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="d54b9-137">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d54b9-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="d54b9-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d54b9-138">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="d54b9-139">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d54b9-139">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="d54b9-140">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="d54b9-140">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="d54b9-141">Value</span><span class="sxs-lookup"><span data-stu-id="d54b9-141">Value</span></span>|<span data-ttu-id="d54b9-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d54b9-142">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="d54b9-143">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d54b9-143">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="d54b9-144">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d54b9-144">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="d54b9-145">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d54b9-145">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="d54b9-146">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d54b9-146">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="d54b9-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d54b9-147">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="d54b9-148">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d54b9-148">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d54b9-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d54b9-149">Child Elements</span></span>

<span data-ttu-id="d54b9-150">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d54b9-150">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d54b9-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d54b9-151">Parent Elements</span></span>

|<span data-ttu-id="d54b9-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="d54b9-152">Element</span></span>|<span data-ttu-id="d54b9-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d54b9-153">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d54b9-154">\<security></span><span class="sxs-lookup"><span data-stu-id="d54b9-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="d54b9-155">Rappresenta le funzionalità di protezione del [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d54b9-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="d54b9-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d54b9-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="d54b9-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="d54b9-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d54b9-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d54b9-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d54b9-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d54b9-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d54b9-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d54b9-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d54b9-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="d54b9-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
