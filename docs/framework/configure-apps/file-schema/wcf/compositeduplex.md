---
title: '&lt;compositeDuplex&gt;'
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: e00cc6f3214dc9a040a9b6170271b1f4188d1631
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601623"
---
# <a name="ltcompositeduplexgt"></a>&lt;compositeDuplex&gt;
Definisce l'elemento di associazione usato quando il client deve esporre un endpoint affinché il servizio restituisca messaggi al client.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<compositeDuplex>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|clientBaseAddress|URI che imposta l'indirizzo del canale di supporto in modalità duplex. Il servizio usa questo indirizzo per creare un contatto e stabilire una connessione con il client.<br /><br /> Se questo attributo non è impostato, un indirizzo predefinito "`full qualified name+default port\TemporaryIndigoAddress\guid`" viene generato. Il valore predefinito è `null`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione viene usato con trasporti che non consentono comunicazioni duplex a livello nativo, ad esempio, HTTP. TCP, al contrario, consente comunicazioni duplex a livello nativo e non richiede l'uso di questo elemento di associazione affinché il servizio invii messaggi a un client.  
  
 Il client deve esporre un indirizzo affinché il servizio crei un contatto e stabilisca una connessione. Questo indirizzo client è fornito dall'attributo `clientBaseAddress`. Si noti che Windows Communication Foundation (WCF) genera automaticamente un ClientBaseAddress se l'utente non ne imposta uno in modo esplicito.  
  
## <a name="example"></a>Esempio  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
