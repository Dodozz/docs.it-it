---
title: Funzione CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487863"
---
# <a name="createcordbobject-function"></a>Funzione CreateCordbObject
Crea un'interfaccia del debugger ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `iDebuggerVersion`  
 [in] Versione del debugger del processo di destinazione. Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.  
  
 `ppCordb`  
 [out] Puntatore a un puntatore a un oggetto che sarà possibile eseguire il cast a un [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia e restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.  
  
 E_INVALIDARG  
 `ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Non è possibile allocare memoria sufficiente per `ppCordb`.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="remarks"></a>Note  
 Il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia restituita in `ppCordb` è l'interfaccia di debug di livello superiore per tutti i servizi di debug gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Library:** mscordbi_macx86.dll  
  
 **Versioni di .NET framework:** 3.5 SP1
