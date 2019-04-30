---
title: Metodo ICorProfilerFunctionEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041536"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a>Metodo ICorProfilerFunctionEnum::GetCount
Ottiene il numero di funzioni che sono state caricate dall'applicazione o caricate forzatamente dal profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 [out] Il numero di funzioni che sono stati caricati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
