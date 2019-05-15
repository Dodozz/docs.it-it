---
title: Funzione QualifierSet_BeginEnumeration (riferimenti alle API non gestite)
description: La funzione QualifierSet_BeginEnumeration Reimposta l'enumeratore dei qualificatori di un oggetto.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f3987705486727a591dce1670cd369d909a0d4a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636236"
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration (funzione)

Reimposta un enumeratore dei qualificatori di un oggetto all'inizio dell'enumerazione.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.

`lFlags`\
[in] Una combinazione bit per bit del flag o i valori descritti nel [osservazioni](#remarks) sezione che specifica i qualificatori da includere nell'enumerazione.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Il parametro `lFlags` non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una seconda chiamata a `QualifierSet_BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per iniziare una nuova enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) (metodo).

Per enumerare tutti i qualificatori su un oggetto, questo metodo deve essere chiamato prima della prima chiamata a [QualifierSet_Next](qualifierset-next.md). L'ordine in cui vengono enumerati i qualificatori è garantito a essere invariante per un'enumerazione specificata.

I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|  | 0 | Restituire i nomi di tutti i qualificatori. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Restituire solo i nomi dei qualificatori specifici per la proprietà corrente o l'oggetto. <br/> Per una proprietà: Restituire solo gli e i qualificatori specifici per la proprietà (incluse le sostituzioni), non tali propagata dalla definizione della classe. <br/> Per un'istanza: Restituire solo i nomi di qualificatore specifici dell'istanza. <br/> Per una classe: Restituire solo i qualificatori specifici per la classe derivata.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | Restituisce solo i nomi dei qualificatori propagati da un altro oggetto. <br/> Per una proprietà: Restituisce solo i qualificatori propagati a questa proprietà dalla definizione della classe e non quelli dalla proprietà stessa. <br/> Per un'istanza: Restituzione solo tali qualificatori propagati dalla definizione della classe. <br/> Per una classe: Restituisce solo i nomi di qualificatore ereditati dalle classi padre. |

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** WMINet_Utils.idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
