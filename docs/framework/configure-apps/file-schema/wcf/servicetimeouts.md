---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758093"
---
# <a name="servicetimeouts"></a>\<serviceTimeouts>
Specifica il timeout per un servizio.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceTimeouts>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`transactionTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale una transazione deve essere propagata dal client al server. Il valore predefinito è "00: 00:00".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
