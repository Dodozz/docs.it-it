---
title: Get (riferimenti alle API non gestite) (funzione)
description: La funzione Get recupera il valore della proprietà specificata.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8a1942f903b1c7c15e58077e35b6a72a86a9419
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636534"
---
# <a name="get-function"></a>Funzione Get

Recupera il valore della proprietà specificata, se presente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro è inutilizzato.

`ptr`\
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszName`\
[in] Il nome della proprietà.

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`pVal`\
[out] Se la funzione termina correttamente, contiene il valore della `wszName` proprietà. Il `pval` argomento è assegnato il tipo corretto e il valore del qualificatore.

`pvtType`\
[out] Se la funzione termina correttamente, contiene un [costante di tipo CIM](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) che indica il tipo di proprietà. Il valore può anche essere `null`. 

`plFlavor`\
[out] Se la funzione termina correttamente, riceve informazioni sull'origine della proprietà. Il valore può essere `null`, o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel *WbemCli.h* file di intestazione: 

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La proprietà è una proprietà di sistema standard. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Per una classe: La proprietà viene ereditata dalla classe padre. <br> Per un'istanza: La proprietà, mentre ereditata dalla classe padre, non modificata dall'istanza.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Per una classe: La proprietà appartiene alla classe derivata. <br> Per un'istanza: La proprietà viene modificata tramite l'istanza. vale a dire, è stato fornito un valore o un qualificatore è stato aggiunto o modificato. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non vengono. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non è stata trovata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) (metodo).

Il `Get` funzione può restituire anche le proprietà di sistema.

Il `pVal` argomento è assegnato il tipo corretto e il valore per il qualificatore e il modello COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) (funzione)

## <a name="requirements"></a>Requisiti

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils.idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
