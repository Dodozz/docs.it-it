---
title: Interfaccia IReferenceAppId
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789682"
---
# <a name="ireferenceappid-interface"></a>Interfaccia IReferenceAppId
Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Imposta l'identificatore di codice per l'applicazione fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` istanza contenente il `IReferenceIdentity` istanze che rappresentano i membri di questo `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a questo `IReferenceAppId` sul valore di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Interfaccia IEnumReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [Interfaccia IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
