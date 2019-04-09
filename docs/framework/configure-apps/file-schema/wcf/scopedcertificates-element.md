---
title: <scopedCertificates> Elemento
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 73e78a6ca27ed45e1eadc7121987b75f79bc6aa5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145200"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="4b001-102">\<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="4b001-102">\<scopedCertificates> Element</span></span>
<span data-ttu-id="4b001-103">Rappresenta una raccolta di certificati X.509 fornita da servizi specifici (con ambito) per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4b001-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="4b001-104">Questa raccolta è usata in genere per specificare i certificati di servizio per i servizi dei token di sicurezza in un scenario federato.</span><span class="sxs-lookup"><span data-stu-id="4b001-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
 <span data-ttu-id="4b001-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4b001-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b001-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4b001-106">\<behaviors></span></span>  
<span data-ttu-id="4b001-107">sezione endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="4b001-107">endpointBehaviors section</span></span>  
<span data-ttu-id="4b001-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4b001-108">\<behavior></span></span>  
<span data-ttu-id="4b001-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="4b001-109">\<clientCredentials></span></span>  
<span data-ttu-id="4b001-110">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4b001-110">\<serviceCertificate></span></span>  
<span data-ttu-id="4b001-111">\<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="4b001-111">\<scopedCertificates> Element</span></span>  
<span data-ttu-id="4b001-112">\<aggiungere > (elemento) per \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="4b001-112">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b001-113">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b001-113">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b001-114">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4b001-114">Attributes and Elements</span></span>  
 <span data-ttu-id="4b001-115">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4b001-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b001-116">Attributi</span><span class="sxs-lookup"><span data-stu-id="4b001-116">Attributes</span></span>  
 <span data-ttu-id="4b001-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4b001-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b001-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4b001-118">Child Elements</span></span>  
  
|<span data-ttu-id="4b001-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b001-119">Element</span></span>|<span data-ttu-id="4b001-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b001-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b001-121">\<add></span><span class="sxs-lookup"><span data-stu-id="4b001-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|<span data-ttu-id="4b001-122">Aggiunge un certificato X.509 alla raccolta di certificati con ambito.</span><span class="sxs-lookup"><span data-stu-id="4b001-122">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b001-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4b001-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4b001-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b001-124">Element</span></span>|<span data-ttu-id="4b001-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b001-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b001-126">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4b001-126">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="4b001-127">Specifica un certificato da usare per l'autenticazione di un servizio presso il client.</span><span class="sxs-lookup"><span data-stu-id="4b001-127">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b001-128">Note</span><span class="sxs-lookup"><span data-stu-id="4b001-128">Remarks</span></span>  
 <span data-ttu-id="4b001-129">Questa raccolta consente al client di configurare i certificati del servizio da usare in base all'URL del servizio con cui comunica.</span><span class="sxs-lookup"><span data-stu-id="4b001-129">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="4b001-130">Questa soluzione è particolarmente utile negli scenari di token pubblicati in cui un client comunica con più servizi (il servizio finale e i servizi token di sicurezza intermedi).</span><span class="sxs-lookup"><span data-stu-id="4b001-130">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="4b001-131">Per le associazioni che usano sistemi di sicurezza dei messaggi basati sui certificati, questo certificato viene usato per crittografare i messaggi inviati al servizio ed è previsto che venga usato dal servizio per firmare le risposte al client.</span><span class="sxs-lookup"><span data-stu-id="4b001-131">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="4b001-132">Se per un'associazione è necessario un certificato per il servizio e non vengono individuati certificati specifici per l'URL del servizio in ScopedCertificates, verrà usato il certificato predefinito.</span><span class="sxs-lookup"><span data-stu-id="4b001-132">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="4b001-133">Per altre informazioni, vedere la sezione "Scoped Certificates" di [come: Creare un Client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="4b001-133">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b001-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b001-134">Example</span></span>  
 <span data-ttu-id="4b001-135">L'esempio seguente specifica un certificato di servizio per il client da utilizzare per comunicare con endpoint il cui nome di dominio è `http://www.contoso.com` sul protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="4b001-135">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="4b001-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b001-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="4b001-137">Utilizzo dei certificati</span><span class="sxs-lookup"><span data-stu-id="4b001-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4b001-138">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="4b001-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="4b001-139">\<add></span><span class="sxs-lookup"><span data-stu-id="4b001-139">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)
- [<span data-ttu-id="4b001-140">Protezione di client</span><span class="sxs-lookup"><span data-stu-id="4b001-140">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="4b001-141">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="4b001-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
