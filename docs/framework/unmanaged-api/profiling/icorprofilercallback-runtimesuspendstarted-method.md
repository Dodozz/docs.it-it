---
title: Metodo ICorProfilerCallback::RuntimeSuspendStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f07cd585ab800394569b97d103e292a5d8f36f20
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466753"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>Metodo ICorProfilerCallback::RuntimeSuspendStarted
Notifica al profiler che il runtime sta per sospendere tutti i thread di runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>Parametri  
 `suspendReason`  
 [in] Valore di [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumerazione che indica il motivo della sospensione.  
  
## <a name="remarks"></a>Note  
 Sono consentiti tutti i thread di runtime in codice non gestito per continuare l'esecuzione fino a quando non tentano di immettere nuovamente la fase di esecuzione. A questo punto si verranno inoltre sospese fino a quando il runtime riprende. Questo vale anche per nuovi thread che accedono al runtime. Tutti i thread nel runtime vengono che sospesi immediatamente se sono già nel codice che possono essere interrotte, o gli viene chiesto sospese quando raggiungono codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [Metodo RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
