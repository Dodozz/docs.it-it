---
title: Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ff178cc9ab798593848e56fc7bba8ac82ae295
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699695"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a>Metodo IDebuggerThreadControl::ThreadIsBlockingForDebugger
Notifica all'host che riguarda il thread che sta inviando il callback al blocco all'interno di servizi di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a>Note  
 Il `ThreadIsBlockingForDebugger` metodo sarà sempre chiamato su un thread di runtime.  
  
 Il `ThreadIsBlockingForDebugger` metodo consente all'host di un'opportunità per eseguire un'altra azione mentre il thread si blocca.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
