---
title: <security> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: dc41f6f7-cabc-4a64-9fa0-ceabf861b348
ms.openlocfilehash: f2750036aa4d3fbe41062ad041e50ff3a4be32b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670571"
---
# <a name="security-of-nethttpbinding"></a>\<sicurezza > di \<netHttpBinding >

Definisce le funzionalità di sicurezza del [ \<basicHttpBinding >](basichttpbinding.md).

\<system.ServiceModel>\
\<bindings>\
\<netHttpBinding>\
\<binding>\
\<security>

## <a name="syntax"></a>Sintassi

```xml
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|Attributo|Descrizione|
|---------------|-----------------|
|modalità|Facoltativo. Specifica il tipo di sicurezza usata. Il valore predefinito è `None`. L'attributo è di tipo <xref:System.ServiceModel.BasicHttpSecurityMode>.|

## <a name="mode-attribute"></a>attributo mode

|Value|Descrizione|
|-----------|-----------------|
|nessuno|-I messaggi non vengono protetti durante il trasferimento.|
|Trasporto|La sicurezza è fornita mediante il trasporto HTTPS. I messaggi SOAP sono protetti mediante HTTPS. Il servizio viene autenticato sul client mediante il certificato X.509 del servizio. Il client viene autenticato mediante il ClientCredentialType  fornito.|
|Messaggio|La sicurezza è fornita mediante la sicurezza dei messaggi SOAP. Per impostazione predefinita, il corpo viene crittografato e firmato. Per questa associazione, il sistema richiede che il certificato server sia fornito al client fuori banda. L'unico valore `ClientCredentialType` valido per questa associazione è `Certificate`.|
|TransportWithMessageCredential|Integrità, riservatezza e autenticazione server sono fornite dalla sicurezza del trasporto. L'autenticazione del client è fornita per mezzo della sicurezza del messaggio SOAP. Questa modalità è appropriata quando l'utente esegue l'autenticazione usando nome utente/password in presenza di una distribuzione HTTP esistente per la sicurezza del trasferimento dei messaggi.|
|TransportCredentialOnly|Questa modalità non fornisce l'integrità e la riservatezza dei messaggi, Fornisce autenticazione client basata su HTTP. Tale modalità deve essere usata con cautela. Deve essere utilizzata nei ambienti in cui la sicurezza del trasporto viene fornita tramite altri mezzi (ad esempio IPSec) e solo l'autenticazione client viene fornito dall'infrastruttura WCF.|

### <a name="child-elements"></a>Elementi figlio

|Elemento|Descrizione|
|-------------|-----------------|
|[\<transport>](transport-of-nethttpbinding.md)|Definisce le impostazioni di sicurezza del trasporto per un servizio HTTP di base. L'elemento corrisponde a <xref:System.ServiceModel.HttpTransportSecurity>.|
|[\<messaggio >](message-of-nethttpbinding.md)|Definisce le impostazioni di sicurezza del messaggio per un servizio HTTP di base. L'elemento corrisponde a <xref:System.ServiceModel.BasicHttpMessageSecurity>.|

### <a name="parent-elements"></a>Elementi padre

|Elemento|Descrizione|
|-------------|-----------------|
|binding|L'elemento di associazione del [ \<basicHttpBinding >](basichttpbinding.md).|

## <a name="remarks"></a>Note

 Per impostazione predefinita, il messaggio SOAP non è protetto e il client non viene autenticato. Questo elemento consente di configurare impostazioni di sicurezza aggiuntive per l'elemento `netHttpBinding`.

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetHttpBindingElement.Security%2A>  
- [Protezione di servizi e client](../../../wcf/feature-details/securing-services-and-clients.md)
- [Selezione di un tipo di credenziale](../../../wcf/feature-details/selecting-a-credential-type.md)
- [Associazioni](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
