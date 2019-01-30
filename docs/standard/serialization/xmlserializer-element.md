---
title: <xmlSerializer> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 2919e8d4c1af858973ff3d2b58b4d3bc4f925527
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258253"
---
# <a name="xmlserializer-element"></a>\<xmlSerializer > elemento
Specifica se effettuare un controllo aggiuntivo dello stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|**checkDeserializeAdvances**|Specifica se controllare lo stato di avanzamento di <xref:System.Xml.Serialization.XmlSerializer>. Impostare l'attributo su "true" o "false". Il valore predefinito è "true".|  
|**useLegacySerializationGeneration**|Specifica se <xref:System.Xml.Serialization.XmlSerializer> usa la generazione legacy di serializzazione che genera assembly scrivendo un codice C# in un file e quindi compilandola in un assembly. Il valore predefinito è **false**.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)|Contiene le impostazioni di configurazione per le classi <xref:System.Xml.Serialization.XmlSerializer> e <xref:System.Xml.Serialization.XmlSchemaImporter>.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, <xref:System.Xml.Serialization.XmlSerializer> fornisce un livello aggiuntivo di sicurezza contro potenziali attacchi di tipo Denial of Service durante la deserializzazione di dati non attendibili. Per ottenere questo risultato, tenta di rilevare cicli infiniti durante la deserializzazione. Se viene rilevata questa condizione, viene generata un'eccezione con messaggio analogo al seguente: "Errore interno: la deserializzazione non può passare al flusso sottostante."  
  
 Se si riceve questo messaggio, non significa che è necessariamente in corso un attacco di tipo Denial of Service. In rare circostanze, il meccanismo di rilevamento di ciclo infinito produce un falso positivo e l'eccezione viene generata pur trattandosi di un messaggio in arrivo valido. Nel caso in cui i messaggi validi della propria applicazione vengano rifiutati da tale livello aggiuntivo di protezione, impostare l'attributo **checkDeserializeAdvances** su "false".  
  
## <a name="example"></a>Esempio  
 L'esempio seguente imposta l'attributo **checkDeserializeAdvances** su "false".  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.Serialization.XmlSerializer>
- [Elemento \<system.xml.serialization>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)
