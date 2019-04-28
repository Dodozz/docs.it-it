---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788726"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="2f542-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="2f542-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="2f542-102">Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="2f542-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="2f542-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2f542-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2f542-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2f542-104">\<behaviors></span></span>  
<span data-ttu-id="2f542-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2f542-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2f542-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2f542-106">\<behavior></span></span>  
<span data-ttu-id="2f542-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="2f542-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f542-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f542-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f542-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f542-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2f542-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f542-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f542-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f542-111">Attributes</span></span>  
 <span data-ttu-id="2f542-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2f542-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f542-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f542-113">Child Elements</span></span>  
  
|<span data-ttu-id="2f542-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f542-114">Element</span></span>|<span data-ttu-id="2f542-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f542-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f542-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="2f542-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="2f542-117">Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="2f542-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f542-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f542-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2f542-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f542-119">Element</span></span>|<span data-ttu-id="2f542-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f542-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f542-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2f542-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2f542-122">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="2f542-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2f542-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f542-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
