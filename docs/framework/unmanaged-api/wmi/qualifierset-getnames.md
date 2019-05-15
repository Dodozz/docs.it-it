---
title: Funzione QualifierSet_GetNames (riferimenti alle API non gestite)
description: La funzione QualifierSet_GetNames recupera i nomi dei qualificatori da un oggetto o una proprietà.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 402d56b44c2b6f53f901e35c6d7b965811a40344
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636594"
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames (funzione)

Recupera i nomi di tutti i qualificatori o di determinati qualificatori disponibili dall'oggetto corrente o la proprietà.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.

`lFlags`\
[in] Uno dei seguenti flag o valori che specifica i nomi da includere nell'enumerazione.

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituire i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto. <br/> Per una proprietà: Restituire solo gli e i qualificatori specifici per la proprietà (incluse le sostituzioni), non tali propagata dalla definizione della classe. <br/> Per un'istanza: Restituire solo i nomi di qualificatore specifici dell'istanza. <br/> Per una classe: Restituire solo i qualificatori specifici per la classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituisce solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: Restituisce solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli dalla proprietà stessa. <br/> Per un'istanza: Restituzione solo tali qualificatori propagati dalla definizione della classe. <br/> Per una classe: Restituisce solo i nomi di qualificatore ereditati dalle classi padre. |

`pstrNames`\
[out] Un nuovo `SAFEARRAY` che contiene i nomi richiesti. La matrice può contenere 0 elementi. Se si verifica un errore, un nuovo `SAFEARRAY` non viene restituita.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) (metodo).

Dopo aver recuperato i nomi di qualificatore, è possibile accedere in base al nome ogni qualificatore chiamando il [QualifierSet_Get](qualifierset-get.md) (funzione).

Non è un errore per un determinato oggetto di avere zero qualificatori, pertanto il numero di stringhe nelle `pstrNames` nell'output restituito può essere 0, anche se la funzione restituisce `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** WMINet_Utils.idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
