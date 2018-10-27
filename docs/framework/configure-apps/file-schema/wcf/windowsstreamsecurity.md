---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: e117c30ba2583158ee21fd11ff4a38b094c18fd9
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/26/2018
ms.locfileid: "50045928"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="e2361-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="e2361-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="e2361-103">Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2361-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="e2361-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e2361-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e2361-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="e2361-105">\<bindings></span></span>  
<span data-ttu-id="e2361-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e2361-106">\<customBinding></span></span>  
<span data-ttu-id="e2361-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e2361-107">\<binding></span></span>  
<span data-ttu-id="e2361-108">\<windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="e2361-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2361-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2361-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2361-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2361-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2361-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2361-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2361-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="e2361-112">Attributes</span></span>  
  
|<span data-ttu-id="e2361-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2361-113">Attribute</span></span>|<span data-ttu-id="e2361-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2361-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2361-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="e2361-115">protectionLevel</span></span>|<span data-ttu-id="e2361-116">Definisce la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2361-116">Defines message-level security.</span></span> <span data-ttu-id="e2361-117">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="e2361-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="e2361-118">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="e2361-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="e2361-119">Di seguito vengono elencati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="e2361-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e2361-120">-None: Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="e2361-120">-   None: No protection.</span></span><br /><span data-ttu-id="e2361-121">-Sign: I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="e2361-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="e2361-122">-EncryptAndSign: I messaggi sono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="e2361-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="e2361-123">L'impostazione predefinita è EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="e2361-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="e2361-124">L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="e2361-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2361-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2361-125">Child Elements</span></span>  
 <span data-ttu-id="e2361-126">nessuno</span><span class="sxs-lookup"><span data-stu-id="e2361-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2361-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2361-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e2361-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2361-128">Element</span></span>|<span data-ttu-id="e2361-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2361-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2361-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="e2361-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e2361-131">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2361-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2361-132">Note</span><span class="sxs-lookup"><span data-stu-id="e2361-132">Remarks</span></span>  
 <span data-ttu-id="e2361-133">I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso.</span><span class="sxs-lookup"><span data-stu-id="e2361-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="e2361-134">In particolare, WCF fornisce aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e2361-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="e2361-135">La configurazione di questa sicurezza del trasporto viene incapsulata da questo elemento di configurazione e dalla [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), che possono essere configurate e aggiunte a un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="e2361-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2361-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2361-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="e2361-137">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e2361-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e2361-138">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="e2361-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e2361-139">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e2361-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e2361-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e2361-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
