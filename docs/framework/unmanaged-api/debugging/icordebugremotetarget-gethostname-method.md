---
title: Metodo ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca7aee79b5b8c3d58b4beb8f1ff886a7d55afab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782707"
---
# <a name="icordebugremotetargetgethostname-method"></a>Metodo ICorDebugRemoteTarget::GetHostName
Restituisce il nome di dominio completo o l'indirizzo IPv4 del computer di destinazione per il debug remoto. IPV6 non è attualmente supportato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Parametri  
 `cchHostName`  
 [in] Le dimensioni, in caratteri, del `szHostName` buffer. Se il parametro è 0 (zero), `szHostName` deve essere Null.  
  
 `pcchHostName`  
 [out] Numero di caratteri, incluso un terminatore Null, nel nome host o nell'indirizzo IP. Questo parametro può essere null.  
  
 `szHostName`  
 [out] Buffer contenente il nome host o l'indirizzo IP.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Il nome host o l'indirizzo IP è stato restituito correttamente.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile restituire il nome host o l'indirizzo IP.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene implementato dal writer del debugger. Deve seguire il paradigma di chiamate multiple: Alla prima chiamata, il chiamante passa null sia `cchHostName` e `szHostName`, e `pcchHostName` restituisce le dimensioni del buffer richiesto. Nella seconda chiamata, la dimensione che è stata restituita in precedenza viene passata a `cchHostName` e un buffer di dimensioni appropriate viene passato a `szHostName`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
