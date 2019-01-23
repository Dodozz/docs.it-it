---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 92ae3dc10e0ae734a3113e22f175f4d010ca55b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541859"
---
# <a name="ltbytestreammessageencodinggt"></a>&lt;byteStreamMessageEncoding&gt;
Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<binaryMessageEncoding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|messageVersion|Specifica la versione SOAP dei messaggi inviati usando l'associazione. È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>. Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.<br /><br /> L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [Codifica dei messaggi](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [Scelta di un codificatore di messaggi](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
