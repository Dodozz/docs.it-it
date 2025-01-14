---
title: Enumerazione WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984152"
---
# <a name="waitoption-enumeration"></a>Enumerazione WAIT_OPTION
Contiene valori che indicano che l'azione di un host debba eseguire se l'operazione richiesta da common language runtime (CLR) Blocca.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Notifica all'host che l'attività deve essere riattivata se Common Language Runtime chiama il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) (metodo).|  
|`WAIT_MSGPUMP`|Notifica all'host che è necessario che distribuisca i messaggi sul thread del sistema operativo corrente se il thread si blocca. Il runtime specifica questo valore solo su un <xref:System.Threading.ApartmentState.STA> thread.|  
|`WAIT_NOTINDEADLOCK`|Notifica all'host che la richiesta di sincronizzazione specificato non può essere interrotta da un host. Vale a dire, l'host non può restituire `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Note  
 Il [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) entrambi i metodi accettano un parametro di questo tipo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
