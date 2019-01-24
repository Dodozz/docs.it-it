---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 1115b598776ca7d28698815974e06f3de57be598
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600102"
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="45405-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="45405-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="45405-103">Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="45405-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="45405-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="45405-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45405-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="45405-105">\<behaviors></span></span>  
<span data-ttu-id="45405-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="45405-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="45405-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="45405-107">\<behavior></span></span>  
<span data-ttu-id="45405-108">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="45405-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45405-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45405-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45405-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="45405-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45405-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="45405-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45405-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="45405-112">Attributes</span></span>  
 <span data-ttu-id="45405-113">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="45405-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45405-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="45405-114">Child Elements</span></span>  
 <span data-ttu-id="45405-115">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="45405-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45405-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="45405-116">Parent Elements</span></span>  
  
|<span data-ttu-id="45405-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="45405-117">Element</span></span>|<span data-ttu-id="45405-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45405-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45405-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="45405-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="45405-120">Specifica l'insieme di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="45405-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45405-121">Note</span><span class="sxs-lookup"><span data-stu-id="45405-121">Remarks</span></span>  
 <span data-ttu-id="45405-122">Questo comportamento deve essere usato solo in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, o il [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="45405-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="45405-123">Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="45405-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45405-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45405-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="45405-125">Integrazione AJAX e supporto JSON</span><span class="sxs-lookup"><span data-stu-id="45405-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="45405-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="45405-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
