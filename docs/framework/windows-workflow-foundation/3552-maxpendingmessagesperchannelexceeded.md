---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945938"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 - MaxPendingMessagesPerChannelExceeded
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|3552|  
|Parole chiave|Quota, WFServices|  
|Livello|Avviso|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che è stato raggiunto il limite per la velocità 'MaxPendingMessagesPerChannel'.  
  
## <a name="message"></a>Messaggio  
 Per la velocità 'MaxPendingMessagesPerChannel' limite di '%1' è stato raggiunto. Per aumentare questo limite, modificare la proprietà MaxPendingMessagesPerChannel in BufferedReceiveServiceBehavior.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Limit|xs:string|È stato raggiunto il limite per la velocità MaxPendingMessagesPerChannel.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
