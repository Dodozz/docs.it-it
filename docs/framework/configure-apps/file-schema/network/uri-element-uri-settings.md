---
title: Elemento <Uri> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: f432be7594b1659dfcae0c6eee706358230f2cbb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269250"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="9e6b0-102">\<URI > (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="9e6b0-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="9e6b0-103">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="9e6b0-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="9e6b0-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="9e6b0-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="9e6b0-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="9e6b0-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="9e6b0-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="9e6b0-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="9e6b0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e6b0-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e6b0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e6b0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9e6b0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e6b0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e6b0-110">Attributes</span></span>  
 <span data-ttu-id="9e6b0-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9e6b0-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e6b0-112">Child Elements</span></span>  
  
|<span data-ttu-id="9e6b0-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9e6b0-113">**Element**</span></span>|<span data-ttu-id="9e6b0-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9e6b0-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9e6b0-115">idn</span><span class="sxs-lookup"><span data-stu-id="9e6b0-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="9e6b0-116">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="9e6b0-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="9e6b0-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="9e6b0-118">Specifica se l'analisi identificatore IRI (International Resource Identifier) viene applicata a <xref:System.Uri> e se devono essere applicati le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="9e6b0-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="9e6b0-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="9e6b0-120">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e6b0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e6b0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e6b0-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="9e6b0-122">**Element**</span></span>|<span data-ttu-id="9e6b0-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9e6b0-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9e6b0-124">configuration</span><span class="sxs-lookup"><span data-stu-id="9e6b0-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9e6b0-125">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e6b0-126">Note</span><span class="sxs-lookup"><span data-stu-id="9e6b0-126">Remarks</span></span>  
 <span data-ttu-id="9e6b0-127">Il `uri` elemento contiene le impostazioni per i membri del <xref:System.Uri> utilizzate dalle classi nella classe la <xref:System.Net> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="9e6b0-128">Le impostazioni di configurano il supporto per IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e6b0-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e6b0-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9e6b0-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e6b0-130">Description</span></span>  
 <span data-ttu-id="9e6b0-131">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe per supportare l'analisi IRI e IDN nomi.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="9e6b0-132">Nell'esempio cancella anche tutte le impostazioni di schema e quindi aggiunge il supporto per non eseguire l'escape delimitatori di percorso codificato in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="9e6b0-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9e6b0-133">Codice</span><span class="sxs-lookup"><span data-stu-id="9e6b0-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e6b0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e6b0-134">See also</span></span>
- [<span data-ttu-id="9e6b0-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9e6b0-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
