---
title: '&lt;transport&gt; di &lt;netMsmqBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 678f3fd34f368abae11404fcbb1546b2135a75d2
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147031"
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a>&lt;transport&gt; di &lt;netMsmqBinding&gt;
Definisce le impostazioni di sicurezza del trasporto.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netMsmqBinding>  
\<binding>  
\<security>  
\<trasporto >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|msmqAuthenticationMode|Specifica come deve essere autenticato il messaggio dal trasporto MSMQ. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna autenticazione.<br />-WindowsDomain: Il meccanismo di autenticazione Usa Active Directory per recuperare il certificato X.509 per l'ID di sicurezza associata al messaggio. Questo viene quindi utilizzo per controllare l'ACL della coda in modo da garantire che l'utente disponga dell'autorizzazione per scrivere sulla coda.<br />-Certificato: Il canale recupera il certificato dall'archivio certificati.<br /><br /> Il valore predefinito è `WindowsDomain`.<br /><br /> Se questo attributo viene impostato su `None`, anche l'attributo dell'attributo `msmqProtectionLevel` deve essere impostato su `None`. L'attributo è di tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Specifica l'algoritmo da usare per la crittografia del messaggio in transito durante il trasferimento dei messaggi tra i gestori della coda dei messaggi. Di seguito vengono elencati i valori validi:<br /><br /> -RC4Stream<br />-   AES<br />-Il valore predefinito è `RC4Stream`. L'attributo è di tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Specifica il metodo di sicurezza dei messaggi al livello del trasporto MSMQ. La crittografia assicura l'integrità del messaggio, mentre la firma e la crittografa assicurano l'integrità del messaggio e il non ripudio. Ciò significa che il messaggio proviene effettivamente dal mittente e il mittente è quello indicato. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna protezione.<br />-Accesso: I messaggi vengono firmati.<br />-EncryptAndSign: I messaggi vengono crittografati e firmati.<br />-Il valore predefinito è `Sign`.|  
|msmqSecureHashAlgorithm|Specifica l'algoritmo hash da usare per il calcolo del digest del messaggio. Di seguito vengono elencati i valori validi:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-SHA512<br /><br /> Il valore predefinito è `SHA1`. L'attributo è di tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza del trasporto per i trasporti in coda.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [Code in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
