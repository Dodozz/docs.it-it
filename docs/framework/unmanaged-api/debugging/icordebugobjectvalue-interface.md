---
title: Interfaccia ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0ac91681313b60ebfcaf725dcc2e0d6547e3c1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987818"
---
# <a name="icordebugobjectvalue-interface"></a>Interfaccia ICorDebugObjectValue

Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|Ottiene un puntatore a interfaccia a common language runtime (CLR) <xref:System.Type> dell'oggetto da questo `ICorDebugObjectValue` riferimenti.|  
|[Metodo GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|Non implementato.|  
|[Metodo GetFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.|  
|[Metodo GetManagedCopy](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleta. Non chiamare questo metodo.|  
|[Metodo GetVirtualMethod](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|Non implementato.|  
|[Metodo IsValueClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|Ottiene un valore che indica se l'oggetto fa riferimento questo `ICorDebugObjectValue` è un tipo valore.|  
|[Metodo SetFromManagedCopy](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleta. Non chiamare questo metodo.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugObjectValue` rimane valido fino a quando non è continua il processo sottoposto a debug.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
