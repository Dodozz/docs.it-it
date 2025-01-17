---
title: Interfaccia ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdc889dd6b2854654bfe43b24afbe4cc19863c80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993693"
---
# <a name="icordebugvalue-interface"></a>Interfaccia ICorDebugValue
Rappresenta un valore nel processo sottoposto a debug. Il valore può essere un'operazione di lettura o di scrittura.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CreateBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Questo metodo non è attualmente implementato.|  
|[Metodo GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Ottiene l'indirizzo di questo `ICorDebugValue` oggetto, che è in corso in fase di debug.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Ottiene la dimensione, espressa in byte, di questo `ICorDebugValue` oggetto.|  
|[Metodo GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Ottiene il tipo primitivo di questo `ICorDebugValue` oggetto.|  
  
## <a name="remarks"></a>Note  
 In generale, la proprietà di un oggetto valore viene passata quando viene restituita. Il destinatario è responsabile della rimozione di un riferimento dall'oggetto quando viene terminato con l'oggetto.  
  
 A seconda di dove il valore è stato recuperato da, il valore non restino valido dopo il processo viene ripreso. Pertanto, in generale, il valore non deve essere mantenuto in una chiamata del [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) (metodo).  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
