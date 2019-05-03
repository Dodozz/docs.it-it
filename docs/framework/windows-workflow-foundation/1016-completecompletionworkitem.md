---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925086"
---
# <a name="1016---completecompletionworkitem"></a>1016 - CompleteCompletionWorkItem
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|1016|  
|Parole chiave|WFRuntime|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descrizione  
 Indica che CompletionWorkItem è completato.  
  
## <a name="message"></a>Messaggio  
 CompletionWorkItem completato per l'attività padre '%1', DisplayName: '%2', InstanceId: '%3'. Attività '%4', DisplayName: '%5', InstanceId: '%6' completata.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Nome tipo dell'attività padre.|  
|ParentDisplayName|xs:string|Nome visualizzato dell'attività padre.|  
|ParentInstanceId|xs:string|ID dell'istanza dell'attività padre.|  
|CompletedActivity|xs:string|Nome tipo dell'attività completata.|  
|CompletedActivityDisplayName|xs:string|Nome visualizzato dell'attività completata.|  
|CompletedActivityInstanceId|xs:string|L'ID dell'istanza dell'attività completata.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
