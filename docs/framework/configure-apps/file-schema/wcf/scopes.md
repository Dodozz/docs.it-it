---
title: '&lt;Ambiti&gt;'
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 7afab700c2d9eb91ffe57bfefaf5864782a0af5f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145328"
---
# <a name="ltscopesgt"></a><span data-ttu-id="5199a-102">&lt;Ambiti&gt;</span><span class="sxs-lookup"><span data-stu-id="5199a-102">&lt;scopes&gt;</span></span>
<span data-ttu-id="5199a-103">Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="5199a-103">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="5199a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5199a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5199a-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="5199a-105">\<behaviors></span></span>  
<span data-ttu-id="5199a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5199a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5199a-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="5199a-107">\<behavior></span></span>  
<span data-ttu-id="5199a-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="5199a-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="5199a-109">\<gli ambiti ></span><span class="sxs-lookup"><span data-stu-id="5199a-109">\<scopes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5199a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5199a-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5199a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5199a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5199a-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5199a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5199a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="5199a-113">Attributes</span></span>  
 <span data-ttu-id="5199a-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5199a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5199a-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5199a-115">Child Elements</span></span>  
  
|<span data-ttu-id="5199a-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="5199a-116">Attribute</span></span>|<span data-ttu-id="5199a-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5199a-117">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5199a-118">\<add></span><span class="sxs-lookup"><span data-stu-id="5199a-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|<span data-ttu-id="5199a-119">Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.</span><span class="sxs-lookup"><span data-stu-id="5199a-119">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5199a-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5199a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5199a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5199a-121">Element</span></span>|<span data-ttu-id="5199a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5199a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5199a-123">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="5199a-123">\<endpointDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|<span data-ttu-id="5199a-124">Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.</span><span class="sxs-lookup"><span data-stu-id="5199a-124">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5199a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5199a-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
