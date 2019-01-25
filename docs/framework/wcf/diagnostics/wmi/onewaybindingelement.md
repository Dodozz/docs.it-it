---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: d84184febd6db3f233aae6fe558b8e0f50a9cb82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608836"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe OneWayBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe OneWayBindingElement dispone delle proprietà seguenti:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Tipo di dati: ChannelPoolSettings  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni del pool di canali.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di canali accettati.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che indica se il pacchetto è instradabile.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
