---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113633"
---
# <a name="windowsstreamsecurity"></a>\<windowsStreamSecurity>
Specificare le impostazioni per la sicurezza del flusso di Windows dell'associazione personalizzata.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<windowsStreamSecurity>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|protectionLevel|Definisce la sicurezza a livello di messaggio. La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento. La crittografia fornisce riservatezza a livello di dati durante il trasporto. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna protezione.<br />-Accesso: I messaggi vengono firmati.<br />-   EncryptAndSign: I messaggi sono firmati e crittografati.<br /><br /> L'impostazione predefinita è EncryptAndSign.<br /><br /> L'attributo è di tipo <xref:System.Net.Security.ProtectionLevel>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 I trasporti che usano un protocollo orientato al flusso, ad esempio TCP e named pipe, supportano aggiornamenti del trasporto basati sul flusso. In particolare, WCF fornisce aggiornamenti della sicurezza. La configurazione di questa sicurezza del trasporto viene incapsulata da questo elemento di configurazione e dalla [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), che possono essere configurate e aggiunte a un'associazione personalizzata  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
