---
title: Funzione CloneEnumWbemClassObject (riferimenti alle API non gestite)
description: La funzione CloneEnumWbemClassObject crea una copia logica di un enumeratore.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52edc72e3714ceaf8cc92f272da6a374eb324dad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661646"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject (funzione)
Crea una copia logica di un enumeratore mantenendone la posizione corrente in un'enumerazione.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a>Parametri

`ppEnum`  
[out] Riceve un puntatore a una nuova [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`  
[in] Il livello di autorizzazione.

`impLevel` [in] Il livello di rappresentazione.

`pCurrentEnumWbemClassObject`  
[out] Un puntatore per il [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) istanza da duplicare.

`strUser`   
[in] Il nome utente. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

`strPassword`   
[in] La password. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

`strAuthority`   
[in] Il nome di dominio dell'utente. Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | È disponibile insufficiente memoria completare l'operazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento di remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) (metodo).

Questo metodo esegue solo una copia "best effort". A causa della natura dinamica del numero di oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti l'enumeratore di origine.  

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="example"></a>Esempio

Per un esempio, vedere la [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) (metodo).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
