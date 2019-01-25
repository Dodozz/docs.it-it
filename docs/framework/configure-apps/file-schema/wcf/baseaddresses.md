---
title: '&lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 34d400e74b24e9eb4140d1b43597b0217b23d80c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730126"
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="f2fc3-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="f2fc3-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="f2fc3-103">Rappresenta una raccolta di elementi `baseAddress` costituiti da indirizzi di base per un host del servizio in un ambiente indipendente.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="f2fc3-104">Se è presente un indirizzo di base, gli endpoint possono essere configurati con indirizzi relativi all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="f2fc3-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f2fc3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f2fc3-106">\<client></span><span class="sxs-lookup"><span data-stu-id="f2fc3-106">\<client></span></span>  
<span data-ttu-id="f2fc3-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="f2fc3-107">\<endpoint></span></span>  
<span data-ttu-id="f2fc3-108">\<host></span><span class="sxs-lookup"><span data-stu-id="f2fc3-108">\<host></span></span>  
<span data-ttu-id="f2fc3-109">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="f2fc3-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2fc3-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2fc3-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="f2fc3-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f2fc3-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2fc3-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f2fc3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f2fc3-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2fc3-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="f2fc3-114">Attributes</span></span>  
 <span data-ttu-id="f2fc3-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f2fc3-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f2fc3-116">Child Elements</span></span>  
  
|<span data-ttu-id="f2fc3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2fc3-117">Element</span></span>|<span data-ttu-id="f2fc3-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2fc3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2fc3-119">\<add></span><span class="sxs-lookup"><span data-stu-id="f2fc3-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="f2fc3-120">Elemento di configurazione che specifica gli indirizzi di base usati dall'host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f2fc3-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f2fc3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f2fc3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2fc3-122">Element</span></span>|<span data-ttu-id="f2fc3-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2fc3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2fc3-124">\<host></span><span class="sxs-lookup"><span data-stu-id="f2fc3-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="f2fc3-125">Elemento di configurazione che specifica le impostazioni per un host del servizio.</span><span class="sxs-lookup"><span data-stu-id="f2fc3-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2fc3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2fc3-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="f2fc3-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="f2fc3-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
