---
title: Elemento <requestCaching> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: af290e4b9258a08425a15e297ff538502edea916
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674428"
---
# <a name="requestcaching-element-network-settings"></a>Elemento \<requestCaching> (impostazioni di rete)
Controlla il meccanismo di memorizzazione nella cache per le richieste di rete.  
  
 \<configuration>  
\<system.net>  
\<requestCaching>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`isPrivateCache`|Specifica se la cache fornisce l'isolamento tra le informazioni di utenti diversi. Il valore predefinito è `true`. Questo valore deve essere `false` per le applicazioni di livello intermedio.|  
|`disableAllCaching`|Specifica che la memorizzazione nella cache è disabilitata per tutte le risposte Web e non può essere sottoposto a override a livello di codice.|  
|`defaultPolicyLevel`|Uno dei valori dell'enumerazione <xref:System.Net.Cache.RequestCacheLevel>. Il valore predefinito è `BypassCache`.|  
|`unspecifiedMaximumAge`|Specifica il tempo predefinito dopo il quale contenuto viene contrassegnato come scaduto.|  
  
## <a name="policylevel-attribute"></a>Attributo policyLevel  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`Default`|Restituisce la risorsa memorizzata nella cache se la risorsa è aggiornata, la lunghezza del contenuto è precisa e la scadenza, modifica e gli attributi di lunghezza del contenuto sono presenti.|  
|`BypassCache`|Restituisce la risorsa dal server.|  
|`CacheOnly`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto è presente e corrisponde alla dimensione dell'elemento.|  
|`CacheIfAvailable`|Restituisce la risorsa memorizzata nella cache se la lunghezza del contenuto viene fornita e corrisponde alla dimensione dell'elemento; in caso contrario, la risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Restituisce la risorsa memorizzata nella cache se il timestamp della risorsa memorizzata nella cache è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server, memorizzato nella cache e viene restituita al chiamante.|  
|`Reload`|Scarica la risorsa dal server, viene memorizzato nella cache e la risorsa viene restituito al chiamante.|  
|`NoCacheNoStore`|Se esiste una risorsa memorizzata nella cache, viene eliminata. La risorsa viene scaricata dal server e viene restituita al chiamante.|  
|`Revalidate`|Soddisfa una richiesta mediante la copia memorizzata nella cache della risorsa se il timestamp è identico a quello della risorsa del server. in caso contrario, la risorsa viene scaricata dal server, presentato al chiamante e viene memorizzata nella cache,|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|Elemento facoltativo.<br /><br /> Indica se la memorizzazione nella cache HTTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.|  
|[\<defaultFtpCachePolicy > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|Elemento facoltativo.<br /><br /> Indica se la memorizzazione nella cache FTP è attivo e ne descrive l'impostazione predefinita dei criteri di memorizzazione nella cache.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come disattivare la cache.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
