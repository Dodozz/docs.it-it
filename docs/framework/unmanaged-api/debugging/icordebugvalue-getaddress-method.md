---
title: Metodo ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986856"
---
# <a name="icordebugvaluegetaddress-method"></a>Metodo ICorDebugValue::GetAddress
Ottiene l'indirizzo dell'oggetto "ICorDebugValue", che è in corso il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 [out] Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo di questo oggetto di valore.  
  
## <a name="remarks"></a>Note  
 Se il valore non è disponibile, viene restituito 0 (zero). Questo problema può verificarsi se il valore è almeno in parte nei registri o archiviato in un handle del garbage collector (`GCHandle`).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
