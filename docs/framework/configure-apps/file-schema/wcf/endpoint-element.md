---
title: Elemento <endpoint>
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 667086cda010daf51cb92116d636b9b526b4b34b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673031"
---
# <a name="endpoint-element"></a>\<endpoint > elemento
Specifica le proprietà di associazione, contratto e indirizzo di endpoint del servizio usato per esporre servizi.  
  
 \<system.ServiceModel>  
\<service>  
\<endpoint>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|indirizzo|Stringa che contiene l'indirizzo dell'endpoint. L'indirizzo può essere specificato come indirizzo assoluto o relativo. Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto usato nell'associazione. Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.<br /><br /> Il valore predefinito è una stringa vuota.|  
|behaviorConfiguration|Stringa che contiene il nome del comportamento da usare nell'endpoint.|  
|binding|Attributo stringa obbligatorio che specifica il tipo di associazione da usare. Il tipo deve avere una sezione di configurazione registrata perché sia possibile farvi riferimento. Il tipo viene registrato dal nome di sezione, anziché dal nome del tipo di associazione.|  
|bindingConfiguration|Stringa che specifica il nome dell'associazione da usare quando viene creata l'istanza dell'endpoint. Il nome dell'associazione deve essere nell'ambito del punto in cui l'endpoint viene definito. Il valore predefinito è una stringa vuota.<br /><br /> Questo attributo viene usato in combinazione con `binding` per fare riferimento a una configurazione di associazione specifica nel file di configurazione. Impostare questo attributo se si sta tentando di usare un'associazione personalizzata. In caso contrario, può venire generata un'eccezione.|  
|bindingName|Stringa che specifica il nome completo e univoco dell'associazione per l'esportazione delle definizioni tramite WSDL. Il valore predefinito è una stringa vuota.|  
|bindingNamespace|Stringa che specifica il nome completo e univoco dello spazio dei nomi dell'associazione per l'esportazione delle definizioni tramite WSDL. Il valore predefinito è una stringa vuota.|  
|contratto|Stringa che indica quale contratto viene esposto da questo endpoint. L'assembly deve implementare il tipo di contratto. Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa. Il valore predefinito è una stringa vuota.|  
|endpointConfiguration|Stringa che specifica il nome dell'endpoint standard impostato dall'attributo `kind` che fa riferimento alle informazioni di configurazione aggiuntive di questo endpoint standard. Lo stesso nome deve essere definito nella sezione `<standardEndpoints>`.|  
|isSystemEndpoint|Valore booleano che specifica se un endpoint è un endpoint di infrastruttura.|  
|kind|Stringa che specifica il tipo di endpoint standard applicato. Il tipo deve essere registrato nella sezione `<extensions>` o in machine.config. Se non specificato, viene creato un endpoint del servizio comune.|  
|listenUriMode|Specifica il modo in cui il trasporto considera l'elemento `ListenUri` fornito sul quale è in ascolto il servizio. I valori validi sono:<br /><br /> -   Explicit<br />-Univoco<br /><br /> Il valore predefinito è Explicit.|  
|listenUri|Stringa che specifica l'URI sul quale è in ascolto l'endpoint del servizio. Il valore predefinito è una stringa vuota.|  
|name|Attributo facoltativo. Stringa che specifica il nome dell'endpoint del servizio. Il valore predefinito è costituito dalla concatenazione del nome dell'associazione e del nome della descrizione del contratto. È possibile che i servizi siano dotati di più endpoint, quindi l'attributo `name` dell'endpoint si differenzia dal nome del servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Raccolte di intestazioni di indirizzo.|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Identità che consente l'autenticazione di un endpoint da altri endpoint con i quali vengono scambiati messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<service>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Sezione di configurazione che definisce un elenco di endpoint ai quali può connettersi un client.|  
  
## <a name="example"></a>Esempio  
 Di seguito è riportato un esempio di configurazione dell'endpoint di un servizio.  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [Endpoint: Gli indirizzi, associazioni e contratti](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Procedura: Creare un Endpoint del servizio nella configurazione](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
