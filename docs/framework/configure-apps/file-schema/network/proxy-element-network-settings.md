---
title: Elemento <proxy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 8df9bbf2615776c2e023f03401785da95b2226eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674499"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="4ab23-102">\<proxy > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="4ab23-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="4ab23-103">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="4ab23-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="4ab23-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ab23-104">\<configuration></span></span>  
<span data-ttu-id="4ab23-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4ab23-105">\<system.net></span></span>  
<span data-ttu-id="4ab23-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="4ab23-106">\<defaultProxy></span></span>  
<span data-ttu-id="4ab23-107">\<proxy></span><span class="sxs-lookup"><span data-stu-id="4ab23-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab23-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ab23-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ab23-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ab23-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ab23-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ab23-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ab23-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ab23-111">Attributes</span></span>  
  
|<span data-ttu-id="4ab23-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="4ab23-112">**Attribute**</span></span>|<span data-ttu-id="4ab23-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ab23-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="4ab23-114">Specifica se il proxy viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4ab23-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="4ab23-115">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4ab23-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="4ab23-116">Specifica se il proxy viene ignorato per le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="4ab23-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="4ab23-117">Le risorse locali includono il server locale (`http://localhost`, `http://loopback`, o `http://127.0.0.1`) e un URI senza un punto (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="4ab23-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="4ab23-118">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4ab23-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="4ab23-119">Specifica l'URI del proxy da usare.</span><span class="sxs-lookup"><span data-stu-id="4ab23-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="4ab23-120">Specifica il percorso dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ab23-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="4ab23-121">Non usare il `bypassonlocal` attributo con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="4ab23-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="4ab23-122">Specifica se utilizzare le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ab23-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="4ab23-123">Se impostato su `true`, gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ab23-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="4ab23-124">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4ab23-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ab23-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ab23-125">Child Elements</span></span>  
 <span data-ttu-id="4ab23-126">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4ab23-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ab23-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ab23-127">Parent Elements</span></span>  
  
|<span data-ttu-id="4ab23-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4ab23-128">**Element**</span></span>|<span data-ttu-id="4ab23-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ab23-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ab23-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4ab23-130">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="4ab23-131">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="4ab23-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="4ab23-132">Valore di testo</span><span class="sxs-lookup"><span data-stu-id="4ab23-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ab23-133">Note</span><span class="sxs-lookup"><span data-stu-id="4ab23-133">Remarks</span></span>  
 <span data-ttu-id="4ab23-134">Il `proxy` elemento definisce un server proxy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ab23-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="4ab23-135">Se questo elemento è mancano dal file di configurazione, .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ab23-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="4ab23-136">Il valore per il `proxyaddress` attributo deve essere un formato corretto indicatore URI (Uniform Resource).</span><span class="sxs-lookup"><span data-stu-id="4ab23-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="4ab23-137">Il `scriptLocation` attributo fa riferimento per il rilevamento automatico proxy degli script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ab23-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="4ab23-138">Il <xref:System.Net.WebProxy> classe tenterà di individuare uno script di configurazione (in genere denominato Wpad. dat) quando il **usare script di configurazione automatica** opzione è selezionata in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4ab23-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="4ab23-139">Se `bypassonlocal` è impostata su qualsiasi valore, `scriptLocation` viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="4ab23-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="4ab23-140">Usare il `usesystemdefault` attributo per applicazioni .NET Framework versione 1.1 che sta eseguendo la migrazione alla versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="4ab23-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="4ab23-141">Viene generata un'eccezione se il `proxyaddress` attributo specifica un proxy predefinito non è valido.</span><span class="sxs-lookup"><span data-stu-id="4ab23-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="4ab23-142">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="4ab23-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4ab23-143">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ab23-143">Configuration Files</span></span>  
 <span data-ttu-id="4ab23-144">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4ab23-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ab23-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ab23-145">Example</span></span>  
 <span data-ttu-id="4ab23-146">Nell'esempio seguente usa le impostazioni predefinite del proxy di Internet Explorer, specifica l'indirizzo del proxy e ignora il proxy per l'accesso locale.</span><span class="sxs-lookup"><span data-stu-id="4ab23-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ab23-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ab23-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4ab23-148">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4ab23-148">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
