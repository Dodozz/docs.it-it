---
title: <add> di <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673615"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<aggiungere > di \<issuerChannelBehaviors >

Aggiunge un comportamento di endpoint da usare durante le comunicazioni con un servizio STS.

> [!NOTE]
> Se qualsiasi comportamento dell'endpoint contiene un [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento, verrà generata un'eccezione.

\<system.ServiceModel>\
\<behaviors>\
sezione endpointBehaviors \<comportamento > \
\<clientCredentials>\
\<issuedToken>\
\<issuerChannelBehaviors > Element\
\<add>

## <a name="syntax"></a>Sintassi

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|issuerAddress|URI dell'emittente del token di sicurezza con cui comunicare.|
|behaviorConfiguration|Nome di un comportamento di endpoint definito nello stesso file di configurazione.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|Contiene una raccolta di comportamenti dell'endpoint client di Windows Communication Foundation (WCF) da utilizzare durante la comunicazione con i servizi STS specificati.|

## <a name="remarks"></a>Note

`issuerAddress` contiene l'URI del servizio token di sicurezza con cui il client desidera comunicare. `behaviorConfiguration` punta a un comportamento dell'endpoint utilizzati dall'applicazione nei canali creati da Windows Communication Foundation (WCF) per ottenere i token rilasciati dal servizio Token di sicurezza.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [Identità del servizio e autenticazione](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Protezione di client](../../../../../docs/framework/wcf/securing-clients.md)
- [Procedura: Creare un Client federato](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Procedura: Configurare un emittente locale](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Federazione e token rilasciati](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
