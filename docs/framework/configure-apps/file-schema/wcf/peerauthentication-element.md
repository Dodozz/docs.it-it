---
title: <peerAuthentication> Elemento
ms.date: 03/30/2017
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
ms.openlocfilehash: 1e99f6d117604f9ba2672972a4b09e7fe9f96792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092968"
---
# <a name="peerauthentication-element"></a><span data-ttu-id="44bbb-102">\<peerAuthentication > elemento</span><span class="sxs-lookup"><span data-stu-id="44bbb-102">\<peerAuthentication> Element</span></span>
<span data-ttu-id="44bbb-103">Specifica le opzioni di autenticazione dei client peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="44bbb-103">Specifies authentication options for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="44bbb-104">Per altre informazioni sulla programmazione peer-to-peer, vedere [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="44bbb-104">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
 <span data-ttu-id="44bbb-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="44bbb-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="44bbb-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="44bbb-106">\<behaviors></span></span>  
<span data-ttu-id="44bbb-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="44bbb-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="44bbb-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="44bbb-108">\<behavior></span></span>  
<span data-ttu-id="44bbb-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="44bbb-109">\<clientCredentials></span></span>  
<span data-ttu-id="44bbb-110">\<peer></span><span class="sxs-lookup"><span data-stu-id="44bbb-110">\<peer></span></span>  
<span data-ttu-id="44bbb-111">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="44bbb-111">\<PeerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44bbb-112">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44bbb-112">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44bbb-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="44bbb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="44bbb-114">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="44bbb-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44bbb-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="44bbb-115">Attributes</span></span>  
  
|<span data-ttu-id="44bbb-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="44bbb-116">Attribute</span></span>|<span data-ttu-id="44bbb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-117">Description</span></span>|  
|---------------|-----------------|  
|`customCertificateValidatorType`|<span data-ttu-id="44bbb-118">Stringa facoltativa.</span><span class="sxs-lookup"><span data-stu-id="44bbb-118">Optional string.</span></span> <span data-ttu-id="44bbb-119">Un tipo e un assembly usati per convalidare un tipo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="44bbb-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="44bbb-120">Questo attributo deve essere impostato quando `certificateValidationMode` è impostato su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`certifcateValidationMode`|<span data-ttu-id="44bbb-121">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="44bbb-121">Optional enumeration.</span></span> <span data-ttu-id="44bbb-122">Specifica una delle tre modalità usate per convalidare credenziali.</span><span class="sxs-lookup"><span data-stu-id="44bbb-122">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="44bbb-123">Se impostato su `Custom`, è necessario fornire anche un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-123">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="44bbb-124">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-124">The default is `ChainTrust`.</span></span>|  
|`revocationMode`|<span data-ttu-id="44bbb-125">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="44bbb-125">Optional enumeration.</span></span> <span data-ttu-id="44bbb-126">Una delle modalità usate per verificare un elenco dei certificati revocati.</span><span class="sxs-lookup"><span data-stu-id="44bbb-126">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="44bbb-127">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-127">The default is `Online`.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="44bbb-128">Enumerazione facoltativa.</span><span class="sxs-lookup"><span data-stu-id="44bbb-128">Optional enumeration.</span></span> <span data-ttu-id="44bbb-129">Uno di due percorsi dell'archivio di sistema: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-129">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="44bbb-130">Questo valore viene usato quando viene negoziato un certificato del servizio con il client.</span><span class="sxs-lookup"><span data-stu-id="44bbb-130">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="44bbb-131">La convalida viene eseguita sul **persone attendibili** archiviare nel percorso dell'archivio specificato.</span><span class="sxs-lookup"><span data-stu-id="44bbb-131">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="44bbb-132">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-132">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="44bbb-133">Attributo customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="44bbb-133">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="44bbb-134">Value</span><span class="sxs-lookup"><span data-stu-id="44bbb-134">Value</span></span>|<span data-ttu-id="44bbb-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44bbb-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="44bbb-136">String</span></span>|<span data-ttu-id="44bbb-137">Specifica il nome e l'assembly del tipo e altri dati usati per trovare il tipo.</span><span class="sxs-lookup"><span data-stu-id="44bbb-137">Specifies the type name and assembly and other data used to find the type.</span></span> <span data-ttu-id="44bbb-138">Come minimo, sono necessari uno spazio dei nomi e un nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="44bbb-138">At minimum, a namespace and type name are required.</span></span> <span data-ttu-id="44bbb-139">Le informazioni facoltative comprendono il nome dell'assembly, il numero di versione, impostazioni cultura e token della chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="44bbb-139">Optional information includes: assembly name, version number, culture, and public key token.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="44bbb-140">Attributo certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="44bbb-140">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="44bbb-141">Value</span><span class="sxs-lookup"><span data-stu-id="44bbb-141">Value</span></span>|<span data-ttu-id="44bbb-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44bbb-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="44bbb-143">Enumeration</span></span>|<span data-ttu-id="44bbb-144">Uno dei valori seguenti: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-144">One of the following values: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.</span></span> <span data-ttu-id="44bbb-145">Il valore predefinito è `ChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-145">The default is `ChainTrust`.</span></span><br /><br /> <span data-ttu-id="44bbb-146">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="44bbb-146">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="44bbb-147">Attributo revocationMode</span><span class="sxs-lookup"><span data-stu-id="44bbb-147">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="44bbb-148">Value</span><span class="sxs-lookup"><span data-stu-id="44bbb-148">Value</span></span>|<span data-ttu-id="44bbb-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44bbb-150">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="44bbb-150">Enumeration</span></span>|<span data-ttu-id="44bbb-151">Uno dei valori seguenti: `NoCheck`, `Online`, `Offline`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-151">One of the following values: `NoCheck`, `Online`, `Offline`.</span></span> <span data-ttu-id="44bbb-152">Il valore predefinito è `Online`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-152">The default is `Online`.</span></span><br /><br /> <span data-ttu-id="44bbb-153">Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="44bbb-153">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="44bbb-154">Attributo trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="44bbb-154">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="44bbb-155">Value</span><span class="sxs-lookup"><span data-stu-id="44bbb-155">Value</span></span>|<span data-ttu-id="44bbb-156">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-156">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44bbb-157">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="44bbb-157">Enumeration</span></span>|<span data-ttu-id="44bbb-158">Uno dei valori seguenti: `LocalMachine` o `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-158">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="44bbb-159">Il valore predefinito è `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-159">The default is `CurrentUser`.</span></span> <span data-ttu-id="44bbb-160">Se l'applicazione client viene eseguita con un account di sistema, il certificato è generalmente situato in `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-160">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="44bbb-161">Se l'applicazione client viene eseguita con un account utente, il certificato è generalmente situato in `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-161">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44bbb-162">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="44bbb-162">Child Elements</span></span>  
 <span data-ttu-id="44bbb-163">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="44bbb-163">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44bbb-164">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="44bbb-164">Parent Elements</span></span>  
  
|<span data-ttu-id="44bbb-165">Elemento</span><span class="sxs-lookup"><span data-stu-id="44bbb-165">Element</span></span>|<span data-ttu-id="44bbb-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44bbb-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44bbb-167">\<peer></span><span class="sxs-lookup"><span data-stu-id="44bbb-167">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="44bbb-168">Specifica una credenziale usata per l'autenticazione del client con un servizio peer.</span><span class="sxs-lookup"><span data-stu-id="44bbb-168">Specifies a credential used for authenticating the client to a peer service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44bbb-169">Note</span><span class="sxs-lookup"><span data-stu-id="44bbb-169">Remarks</span></span>  
 <span data-ttu-id="44bbb-170">L'elemento `<authentication>` corrisponde alla classe <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="44bbb-170">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="44bbb-171">Questo elemento specifica una convalida, che viene richiamata durante l'autenticazione tra peer adiacenti nella rete.</span><span class="sxs-lookup"><span data-stu-id="44bbb-171">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="44bbb-172">Quando un nuovo peer tenta di stabilire una connessione con un peer adiacente, passa la propria credenziale al peer che risponde.</span><span class="sxs-lookup"><span data-stu-id="44bbb-172">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="44bbb-173">Viene richiamata la convalida del risponditore per verificare la credenziale della parte remota.</span><span class="sxs-lookup"><span data-stu-id="44bbb-173">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="44bbb-174">Ogni volta che viene stabilita una connessione peer nella rete, entrambi i peer vengono reciprocamente autenticati, indicando che vengono richiamati validator su entrambe le parti.</span><span class="sxs-lookup"><span data-stu-id="44bbb-174">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44bbb-175">Esempio</span><span class="sxs-lookup"><span data-stu-id="44bbb-175">Example</span></span>  
 <span data-ttu-id="44bbb-176">Il codice seguente imposta la modalità di convalida del certificato su `PeerOrChainTrust`.</span><span class="sxs-lookup"><span data-stu-id="44bbb-176">The following code sets the certificate validation mode to `PeerOrChainTrust`.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <peerAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="44bbb-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44bbb-177">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="44bbb-178">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="44bbb-178">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="44bbb-179">Rete peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="44bbb-179">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="44bbb-180">Autenticazione dei messaggi del canale peer</span><span class="sxs-lookup"><span data-stu-id="44bbb-180">Peer Channel Message Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [<span data-ttu-id="44bbb-181">Autenticazione personalizzata dei messaggi del canale</span><span class="sxs-lookup"><span data-stu-id="44bbb-181">Peer Channel Custom Authentication</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [<span data-ttu-id="44bbb-182">Protezione di applicazioni del canale peer</span><span class="sxs-lookup"><span data-stu-id="44bbb-182">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
