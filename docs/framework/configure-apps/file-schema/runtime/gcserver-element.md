---
title: <gcServer> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5df7ab070cc0a40f4e2f3d0545c5bc40ccb07f4d
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378030"
---
# <a name="gcserver-element"></a>\<gcServer> Element
Specifica se Common Language Runtime esegue Garbage Collection per server.  
  
 \<configuration>  
\<runtime>  
\<gcServer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime esegue Garbage Collection per server.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`false`|Non esegue Garbage Collection per server. Questa è l'impostazione predefinita.|  
|`true`|Esegue Garbage Collection per server.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sull'associazione degli assembly e sull'operazione di Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 Common Language Runtime (CLR) supporta due tipi di Garbage Collection: Garbage Collection per workstation, disponibile in tutti i sistemi, e Garbage Collection per server, disponibile nei sistemi con più processori. Si usa l'elemento `<gcServer>` per controllare il tipo di Garbage Collection eseguito da CLR. Usare la proprietà <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> per determinare se l'operazione Garbage Collection per server è abilitata.  
  
 Per i computer con un solo processore, l'operazione di Garbage Collection per workstation predefinita dovrebbe essere l'opzione più rapida. Per i computer con due processori, si può usare quella per workstation o quella per server. L'operazione di Garbage Collection per server dovrebbe essere l'opzione più rapida per più di due processori.  
  
 Questo elemento può essere usato solo nel file di configurazione dell'applicazione. Se è nel file di configurazione del computer, viene ignorato.  
  
> [!NOTE]
>  In .NET Framework 4 e versioni precedenti, la modalità di Garbage Collection simultanea non è disponibile quando l'operazione di Garbage Collection per server è abilitata. A partire da .NET Framework 4.5, l'operazione di Garbage Collection per server è simultanea. Per usare garbage collection del server non simultanea, impostare il `<gcServer>` elemento `true` e il [ \<gcConcurrent > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) a `false`.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente abilita l'operazione di Garbage Collection per server.  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Per disabilitare la garbage collection simultanea](gcconcurrent-element.md#to-disable-background-garbage-collection)
