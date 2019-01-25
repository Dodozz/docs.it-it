---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: b9fe4a9eb0176c97920c0dde5cb003c8ca1ae989
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697439"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="1cb6b-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="1cb6b-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="1cb6b-103">Specifica le impostazioni di codifica e controllo di versione dei messaggi SOAP basati sul meccanismo Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="1cb6b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1cb6b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1cb6b-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1cb6b-105">\<bindings></span></span>  
<span data-ttu-id="1cb6b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1cb6b-106">\<customBinding></span></span>  
<span data-ttu-id="1cb6b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1cb6b-107">\<binding></span></span>  
<span data-ttu-id="1cb6b-108">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="1cb6b-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb6b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cb6b-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cb6b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1cb6b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1cb6b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cb6b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1cb6b-112">Attributes</span></span>  
  
|<span data-ttu-id="1cb6b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1cb6b-113">Attribute</span></span>|<span data-ttu-id="1cb6b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb6b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1cb6b-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="1cb6b-115">maxBufferSize</span></span>|<span data-ttu-id="1cb6b-116">Numero intero che specifica la dimensione massima del buffer che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="1cb6b-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1cb6b-117">maxReadPoolSize</span></span>|<span data-ttu-id="1cb6b-118">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1cb6b-119">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1cb6b-120">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-120">The default is 64.</span></span>|  
|<span data-ttu-id="1cb6b-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1cb6b-121">maxWritePoolSize</span></span>|<span data-ttu-id="1cb6b-122">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1cb6b-123">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1cb6b-124">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-124">The default is 16.</span></span>|  
|<span data-ttu-id="1cb6b-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1cb6b-125">messageVersion</span></span>|<span data-ttu-id="1cb6b-126">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="1cb6b-127">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1cb6b-127">Valid values are</span></span><br /><br /> <span data-ttu-id="1cb6b-128">-   Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="1cb6b-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="1cb6b-129">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="1cb6b-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="1cb6b-130">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="1cb6b-131">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="1cb6b-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="1cb6b-132">writeEncoding</span></span>|<span data-ttu-id="1cb6b-133">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="1cb6b-134">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1cb6b-134">Valid values are</span></span><br /><br /> <span data-ttu-id="1cb6b-135">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="1cb6b-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="1cb6b-136">-   Utf16TextEncoding: Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="1cb6b-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="1cb6b-137">-   Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="1cb6b-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="1cb6b-138">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="1cb6b-139">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1cb6b-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1cb6b-140">Child Elements</span></span>  
  
|<span data-ttu-id="1cb6b-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cb6b-141">Element</span></span>|<span data-ttu-id="1cb6b-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb6b-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cb6b-143">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="1cb6b-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="1cb6b-144">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1cb6b-145">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cb6b-146">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1cb6b-146">Parent Elements</span></span>  
  
|<span data-ttu-id="1cb6b-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cb6b-147">Element</span></span>|<span data-ttu-id="1cb6b-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1cb6b-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cb6b-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="1cb6b-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1cb6b-150">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cb6b-151">Note</span><span class="sxs-lookup"><span data-stu-id="1cb6b-151">Remarks</span></span>  
 <span data-ttu-id="1cb6b-152">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1cb6b-153">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-153">Decoding is the reverse process.</span></span> <span data-ttu-id="1cb6b-154">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1cb6b-155">L'elemento `MtomMessageEncoding` specifica la codifica dei caratteri, la versione dei messaggi e altre impostazioni usate per i messaggi che usano la codifica MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="1cb6b-156">MTOM è una tecnologia efficiente per la trasmissione di dati binari nei messaggi di WCF.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="1cb6b-157">Il codificatore MTOM cerca di creare un equilibrio tra efficienza e interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="1cb6b-158">La codifica MTOM trasmette la maggior parte del codice XML in formato testo, ma ottimizza grandi blocchi di dati binari trasmettendoli senza introdurre modifiche e senza convertirli nel formato codificato Base64.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cb6b-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="1cb6b-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1cb6b-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cb6b-160">See also</span></span>
- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="1cb6b-161">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1cb6b-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="1cb6b-162">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="1cb6b-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1cb6b-163">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1cb6b-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1cb6b-164">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1cb6b-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1cb6b-165">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1cb6b-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1cb6b-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1cb6b-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
