---
title: '&lt;aggiungere&gt; (elemento) per schemeSettings (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 07bcaf470c68a4d400057b0fe19e96524b2859cb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205178"
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="e9776-102">&lt;aggiungere&gt; (elemento) per schemeSettings (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="e9776-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="e9776-103">Aggiunge un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="e9776-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="e9776-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9776-104">\<configuration></span></span>  
<span data-ttu-id="e9776-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="e9776-105">\<uri></span></span>  
<span data-ttu-id="e9776-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="e9776-106">\<schemeSettings></span></span>  
<span data-ttu-id="e9776-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e9776-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9776-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9776-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9776-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e9776-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9776-110">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e9776-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9776-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e9776-111">Attributes</span></span>  
  
|<span data-ttu-id="e9776-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e9776-112">Attribute</span></span>|<span data-ttu-id="e9776-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9776-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9776-114">name</span><span class="sxs-lookup"><span data-stu-id="e9776-114">name</span></span>|<span data-ttu-id="e9776-115">Il nome dello schema per il quale si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="e9776-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="e9776-116">Il solo valori supportati sono: nome = "http" e nome = "https".</span><span class="sxs-lookup"><span data-stu-id="e9776-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="e9776-117">{Nome dell'attributo} Attributo</span><span class="sxs-lookup"><span data-stu-id="e9776-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="e9776-118">Valore</span><span class="sxs-lookup"><span data-stu-id="e9776-118">Value</span></span>|<span data-ttu-id="e9776-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9776-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e9776-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="e9776-120">genericUriParserOptions</span></span>|<span data-ttu-id="e9776-121">Le opzioni del parser per questo schema.</span><span class="sxs-lookup"><span data-stu-id="e9776-121">The parser options for this scheme.</span></span> <span data-ttu-id="e9776-122">L'unico valore supportato è genericUriParserOptions = "DontUnescapePathDotsAndSlashes".</span><span class="sxs-lookup"><span data-stu-id="e9776-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9776-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e9776-123">Child Elements</span></span>  
 <span data-ttu-id="e9776-124">nessuno</span><span class="sxs-lookup"><span data-stu-id="e9776-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9776-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e9776-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e9776-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9776-126">Element</span></span>|<span data-ttu-id="e9776-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9776-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9776-128">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="e9776-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="e9776-129">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="e9776-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9776-130">Note</span><span class="sxs-lookup"><span data-stu-id="e9776-130">Remarks</span></span>  
 <span data-ttu-id="e9776-131">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="e9776-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="e9776-132">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e9776-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="e9776-133">Se viene passato questo URI lungo i moduli non gestiscono percento codificati in caratteri correttamente, potrebbero verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="e9776-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="e9776-134">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classi e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="e9776-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="e9776-135">Il risultato di passare l'URL dannoso a <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="e9776-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="e9776-136">Possibile è possibile modificare questo comportamento predefinito per non i delimitatori del percorso con codifica percentuale ONU-escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="e9776-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9776-137">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e9776-137">Configuration Files</span></span>  
 <span data-ttu-id="e9776-138">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e9776-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9776-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9776-139">Example</span></span>  
 <span data-ttu-id="e9776-140">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe per il supporto non escape delimitatori di percorso codificato in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="e9776-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9776-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9776-141">See Also</span></span>  
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
- <xref:System.Uri?displayProperty=nameWithType>  
- [<span data-ttu-id="e9776-142">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e9776-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
