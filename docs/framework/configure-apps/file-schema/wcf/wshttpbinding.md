---
title: '&lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 05eb8d43e137c8dfc78dc3d7c0b145ce7a4e95ef
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150942"
---
# <a name="ltwshttpbindinggt"></a><span data-ttu-id="cae2c-102">&lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="cae2c-102">&lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="cae2c-103">Definisce un'associazione protetta, affidabile, interoperabile adatta per contratti di servizio non duplex.</span><span class="sxs-lookup"><span data-stu-id="cae2c-103">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="cae2c-104">L'associazione implementa le specifiche seguenti: WS-ReliableMessaging per affidabilità e WS-Security per l'autenticazione e sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="cae2c-104">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="cae2c-105">Il trasporto è HTTP e la codifica dei messaggi è Text/XML.</span><span class="sxs-lookup"><span data-stu-id="cae2c-105">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="cae2c-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cae2c-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="cae2c-107">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="cae2c-107">\<bindings></span></span>  
<span data-ttu-id="cae2c-108">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="cae2c-108">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae2c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cae2c-109">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cae2c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cae2c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cae2c-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cae2c-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cae2c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="cae2c-112">Attributes</span></span>  
  
|<span data-ttu-id="cae2c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="cae2c-113">Attribute</span></span>|<span data-ttu-id="cae2c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae2c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cae2c-115">allowCookies</span><span class="sxs-lookup"><span data-stu-id="cae2c-115">allowCookies</span></span>|<span data-ttu-id="cae2c-116">Valore booleano che indica se il client accetta cookie e li propaga alle richieste future.</span><span class="sxs-lookup"><span data-stu-id="cae2c-116">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="cae2c-117">Il valore predefinito è false.</span><span class="sxs-lookup"><span data-stu-id="cae2c-117">The default is false.</span></span><br /><br /> <span data-ttu-id="cae2c-118">È possibile usare questa proprietà quando si interagisce con servizi Web ASMX che usano cookie.</span><span class="sxs-lookup"><span data-stu-id="cae2c-118">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="cae2c-119">In questo modo i cookie restituiti dal server vengono copiati automaticamente in tutte le richieste client future per quel servizio.</span><span class="sxs-lookup"><span data-stu-id="cae2c-119">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="cae2c-120">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="cae2c-120">bypassProxyOnLocal</span></span>|<span data-ttu-id="cae2c-121">Valore booleano che indica se ignorare il server proxy per indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="cae2c-121">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="cae2c-122">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cae2c-122">The default is `false`.</span></span>|  
|<span data-ttu-id="cae2c-123">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="cae2c-123">closeTimeout</span></span>|<span data-ttu-id="cae2c-124">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura.</span><span class="sxs-lookup"><span data-stu-id="cae2c-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="cae2c-125">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cae2c-126">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cae2c-126">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cae2c-127">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="cae2c-127">hostnameComparisonMode</span></span>|<span data-ttu-id="cae2c-128">Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI.</span><span class="sxs-lookup"><span data-stu-id="cae2c-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="cae2c-129">L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI.</span><span class="sxs-lookup"><span data-stu-id="cae2c-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="cae2c-130">Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="cae2c-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="cae2c-131">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="cae2c-131">maxBufferPoolSize</span></span>|<span data-ttu-id="cae2c-132">Numero intero che specifica la dimensione del pool di buffer massima per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-132">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="cae2c-133">Il valore predefinito è 524.288 byte (512 \* 1024).</span><span class="sxs-lookup"><span data-stu-id="cae2c-133">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="cae2c-134">Molte parti di Windows Communication Foundation (WCF) usano buffer.</span><span class="sxs-lookup"><span data-stu-id="cae2c-134">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="cae2c-135">La creazione e l'eliminazione dei buffer a ogni relativo uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer.</span><span class="sxs-lookup"><span data-stu-id="cae2c-135">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="cae2c-136">Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool.</span><span class="sxs-lookup"><span data-stu-id="cae2c-136">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="cae2c-137">In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione dei buffer.</span><span class="sxs-lookup"><span data-stu-id="cae2c-137">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="cae2c-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="cae2c-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="cae2c-139">Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="cae2c-140">Il mittente di un messaggio che supera questo limite riceverà un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="cae2c-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="cae2c-141">Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia.</span><span class="sxs-lookup"><span data-stu-id="cae2c-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="cae2c-142">Il valore predefinito è 65536.</span><span class="sxs-lookup"><span data-stu-id="cae2c-142">The default is 65536.</span></span>|  
|<span data-ttu-id="cae2c-143">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="cae2c-143">messageEncoding</span></span>|<span data-ttu-id="cae2c-144">Definisce il codificatore usato per codificare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cae2c-144">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="cae2c-145">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="cae2c-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cae2c-146">-Text: Usare un codificatore di messaggi di testo.</span><span class="sxs-lookup"><span data-stu-id="cae2c-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="cae2c-147">-Mtom: Usa un codificatore Message Transmission organizzazione Mechanism 1.0 (MTOM).</span><span class="sxs-lookup"><span data-stu-id="cae2c-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="cae2c-148">-Il valore predefinito è testo.</span><span class="sxs-lookup"><span data-stu-id="cae2c-148">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="cae2c-149">L'attributo è di tipo <xref:System.ServiceModel.WSMessageEncoding>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="cae2c-150">name</span><span class="sxs-lookup"><span data-stu-id="cae2c-150">name</span></span>|<span data-ttu-id="cae2c-151">Stringa che contiene il nome della configurazione dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-151">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="cae2c-152">Questo valore deve essere univoco perché viene usato per identificare l'associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-152">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="cae2c-153">A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome.</span><span class="sxs-lookup"><span data-stu-id="cae2c-153">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cae2c-154">Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="cae2c-154">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="cae2c-155">openTimeout</span><span class="sxs-lookup"><span data-stu-id="cae2c-155">openTimeout</span></span>|<span data-ttu-id="cae2c-156">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura.</span><span class="sxs-lookup"><span data-stu-id="cae2c-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="cae2c-157">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cae2c-158">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cae2c-158">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cae2c-159">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="cae2c-159">proxyAddress</span></span>|<span data-ttu-id="cae2c-160">URI che specifica l'indirizzo del proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="cae2c-160">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="cae2c-161">Se `useSystemWebProxy` è `true`, questa impostazione deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="cae2c-161">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="cae2c-162">Il valore predefinito è `null`.</span><span class="sxs-lookup"><span data-stu-id="cae2c-162">The default is `null`.</span></span>|  
|<span data-ttu-id="cae2c-163">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="cae2c-163">receiveTimeout</span></span>|<span data-ttu-id="cae2c-164">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="cae2c-165">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cae2c-166">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cae2c-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cae2c-167">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="cae2c-167">sendTimeout</span></span>|<span data-ttu-id="cae2c-168">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio.</span><span class="sxs-lookup"><span data-stu-id="cae2c-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="cae2c-169">Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="cae2c-170">L'impostazione predefinita è 00:01:00.</span><span class="sxs-lookup"><span data-stu-id="cae2c-170">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="cae2c-171">textEncoding</span><span class="sxs-lookup"><span data-stu-id="cae2c-171">textEncoding</span></span>|<span data-ttu-id="cae2c-172">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-172">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cae2c-173">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="cae2c-173">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cae2c-174">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian.</span><span class="sxs-lookup"><span data-stu-id="cae2c-174">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="cae2c-175">-Utf16TextEncoding: codifica a 16 bit.</span><span class="sxs-lookup"><span data-stu-id="cae2c-175">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="cae2c-176">-Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="cae2c-176">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="cae2c-177">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="cae2c-177">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="cae2c-178">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-178">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="cae2c-179">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="cae2c-179">transactionFlow</span></span>|<span data-ttu-id="cae2c-180">Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions.</span><span class="sxs-lookup"><span data-stu-id="cae2c-180">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="cae2c-181">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cae2c-181">The default is `false`.</span></span>|  
|<span data-ttu-id="cae2c-182">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="cae2c-182">useDefaultWebProxy</span></span>|<span data-ttu-id="cae2c-183">Valore booleano che specifica se viene usato il proxy HTTP di sistema configurato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cae2c-183">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="cae2c-184">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="cae2c-184">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cae2c-185">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cae2c-185">Child Elements</span></span>  
  
|<span data-ttu-id="cae2c-186">Elemento</span><span class="sxs-lookup"><span data-stu-id="cae2c-186">Element</span></span>|<span data-ttu-id="cae2c-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae2c-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cae2c-188">\<security></span><span class="sxs-lookup"><span data-stu-id="cae2c-188">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="cae2c-189">Definisce le impostazioni di sicurezza per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-189">Defines the security settings for the binding.</span></span> <span data-ttu-id="cae2c-190">L'elemento è di tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-190">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="cae2c-191">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="cae2c-191">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="cae2c-192">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="cae2c-192">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cae2c-193">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="cae2c-193">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="cae2c-194">reliableSession</span><span class="sxs-lookup"><span data-stu-id="cae2c-194">reliableSession</span></span>](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="cae2c-195">Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.</span><span class="sxs-lookup"><span data-stu-id="cae2c-195">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cae2c-196">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cae2c-196">Parent Elements</span></span>  
  
|<span data-ttu-id="cae2c-197">Elemento</span><span class="sxs-lookup"><span data-stu-id="cae2c-197">Element</span></span>|<span data-ttu-id="cae2c-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae2c-198">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cae2c-199">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cae2c-199">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="cae2c-200">Questo elemento contiene una raccolta di associazioni standard e personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cae2c-200">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae2c-201">Note</span><span class="sxs-lookup"><span data-stu-id="cae2c-201">Remarks</span></span>  
 <span data-ttu-id="cae2c-202">`WSHttpBinding` è simile a `BasicHttpBinding` ma fornisce più funzionalità del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="cae2c-202">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="cae2c-203">Usa il trasporto HTTP e fornisce sicurezza dei messaggi, in modo analogo a BasicHttpBinding, ma offre inoltre funzionalità per transazioni, messaggistica affidabile e WS-Addressing, attivate per impostazione predefinita o disponibili tramite l'impostazione di un singolo controllo.</span><span class="sxs-lookup"><span data-stu-id="cae2c-203">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae2c-204">Esempio</span><span class="sxs-lookup"><span data-stu-id="cae2c-204">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="cae2c-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cae2c-205">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement>  
 [<span data-ttu-id="cae2c-206">Associazioni</span><span class="sxs-lookup"><span data-stu-id="cae2c-206">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="cae2c-207">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="cae2c-207">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="cae2c-208">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="cae2c-208">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="cae2c-209">\<binding></span><span class="sxs-lookup"><span data-stu-id="cae2c-209">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
