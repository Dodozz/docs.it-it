---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 34100ce17e67e12574ec0cdd677991949d0b9214
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150799"
---
# <a name="ltenablewebscriptgt"></a>&lt;enableWebScript&gt;
Questo elemento attiva il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX.  
  
 \<system.ServiceModel>  
\<i comportamenti >  
\<endpointBehaviors >  
\<comportamento >  
\<enableWebScript >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica l'insieme di comportamenti dell'endpoint.|  
  
## <a name="remarks"></a>Note  
 Questo comportamento deve essere usato solo in combinazione con il [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) associazione standard, o il [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento di associazione.  Per altre informazioni su questo comportamento, vedere <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [Integrazione AJAX e supporto JSON](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
