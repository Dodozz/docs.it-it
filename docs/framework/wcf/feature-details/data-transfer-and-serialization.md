---
title: Trasferimento dati e serializzazione
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 1eefd82a149d0bc215ca441e92c7d737a744b1e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088405"
---
# <a name="data-transfer-and-serialization"></a>Trasferimento dati e serializzazione
In un sistema collegato, per eseguire qualsiasi attività, servizi e client dipendono dallo scambio di dati. Gli sviluppatori di un servizio o client, è necessario comprendere come Windows Communication Foundation (WCF) gestisce i dati e la serializzazione dei dati per creare applicazioni che sono efficienti e facili da gestire.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Specifica del trasferimento di dati nei contratti di servizio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 Descrive i concetti di base del trasferimento dati nei servizi.  
  
 [Uso di contratti dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 Descrive i contratti dati, come crearli e utilizzarli.  
  
 [Serializzatore dei contratti dati](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 Descrive come eseguire la serializzazione di dati con la classe <xref:System.Runtime.Serialization.DataContractSerializer> o qualsiasi estensione della classe <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 [Utilizzo della classe XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 Descrive come e perché utilizzare la classe <xref:System.Xml.Serialization.XmlSerializer>, un'alternativa alla classe <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 [Utilizzo dei contratti di messaggio](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 Descrive in che modo i contratti di messaggio consentono il controllo accurato di messaggi SOAP.  
  
 [Utilizzo della classe Message](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 Descrive come utilizzare le funzionalità di una classe Message.  
  
 [Filtro](../../../../docs/framework/wcf/feature-details/filtering.md)  
 Descrive il filtraggio, che consente la pre-elaborazione di un messaggio basata su vari criteri.  
  
 [Dati di grandi dimensioni e flussi](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 Descrive come inviare un grande blocco di dati, ad esempio un file binario.  
  
 [Considerazioni sulla protezione per i dati](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 Descrive gli elementi da prendere in considerazione quando si programma il trasferimento dei dati e la serializzazione.  
  
 [Panoramica dell'architettura di trasferimento dei dati](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 Descrive una vista della progettazione complessiva del trasferimento dei dati in WCF.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Estensione di codificatori e serializzatori](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a>Vedere anche

- [Procedure consigliate: Controllo delle versioni dei contratti dati](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [Controllo delle versioni dei servizi](../../../../docs/framework/wcf/service-versioning.md)
