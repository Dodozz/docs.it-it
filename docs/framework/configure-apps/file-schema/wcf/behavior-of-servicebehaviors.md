---
title: <behavior> di <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 89ad23a801abce9b2fe409b7e7acb1f5e9c2ac55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701099"
---
# <a name="behavior-of-servicebehaviors"></a>\<comportamento > di \<serviceBehaviors >
L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un servizio. Ogni comportamento è indicizzato in base al relativo `name`. Servizi possono essere collegati a ciascun comportamento tramite tale nome usando il `behaviorConfiguration` attributo del [ \<endpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento. In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
>  Elementi di comportamento specifici per le attività del flusso di lavoro di Windows, ad esempio il [ \<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) elemento, sono documentati nel [ \<comportamento > di \< serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) pagina.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa univoca che contiene il nome di configurazione del comportamento. Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|Contiene i dati di configurazione per DataContractSerializer.|  
|[\<persistenceProvider>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.|  
|[\<serviceAuthenticationManager>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, di un messaggio o di un creatore.|  
|[\<serviceAuthorization>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|Specifica le impostazioni che autorizzano l'accesso alle operazioni del servizio.|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
|[\<serviceDebug>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|Specifica le funzionalità di informazioni di debug e della Guida per un servizio Windows Communication Foundation (WCF).|  
|[\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|Specifica l'individuabilità degli endpoint del servizio.|  
|[\<serviceMetadata>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|Specifica la pubblicazione dei metadati del servizio e delle informazioni associate.|  
|[\<serviceSecurityAudit>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.|  
|[\<serviceThrottling>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|Specifica il meccanismo di limitazione delle richieste di un servizio WCF.|  
|[\<serviceTimeouts>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|Specifica il timeout per un servizio.|  
|[\<workflowRuntime>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Specifica le impostazioni per un'istanza di WorkflowRuntime per l'hosting di servizi WCF basati sul flusso di lavoro.|  
|[\<useRequestHeadersForMetadataAddress>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Raccolta di elementi di comportamento del servizio.|
