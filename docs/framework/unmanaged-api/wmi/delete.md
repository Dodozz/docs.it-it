---
title: Eliminare la funzione (riferimenti alle API non gestite)
description: La funzione di eliminazione Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0590c639e7cc6622c2283bfa609ccb31d7ce7e2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720574"
---
# <a name="delete-function"></a>Elimina funzione
Elimina la proprietà specificata e tutti i relativi i qualificatori da una definizione di classe CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`  
[in] Il nome della proprietà da eliminare. `wszName` deve essere un puntatore a un valore valido `LPCWSTR`.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore non specificato. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | La proprietà non può essere eliminata. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszzName` non è valido. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non esiste. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Non è disponibile memoria sufficiente per completare l'operazione. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | La proprietà viene ereditata da una classe base. |
| `WBEM_E_SYSTEM_PROPERTY` | | La proprietà è una proprietà di sistema. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | La funzione eliminato un valore sostitutivo predefinito per la classe corrente. Il valore predefinito per questa proprietà nella classe padre è stata reactiviated. | 

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) (metodo).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
