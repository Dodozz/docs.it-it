---
title: Funzione StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636708"
---
# <a name="strongnamekeyinstall-function"></a>Funzione StrongNameKeyInstall

Importa una coppia di chiavi pubblica/privata in un contenitore.

Questa funzione è stata deprecata. Usare la [StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo invece.

## <a name="syntax"></a>Sintassi

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Parametri

`wszKeyContainer`\
[in] Il nome del contenitore di chiavi. `wszKeyContainer` deve essere una stringa non vuota.

`pbKeyBlob`\
[in] La coppia di chiavi binaria.

`cbKeyBlob`\
[in] Le dimensioni, in byte, di `pbKeyBlob`.

## <a name="return-value"></a>Valore restituito

`true` al termine dell'esecuzione; in caso contrario, `false`.

## <a name="remarks"></a>Note

Usare la [StrongNameKeyDelete](strongnamekeydelete-function.md) (funzione) per eliminare il contenitore di chiavi.

Se il `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** StrongName.h

**Libreria:** Inclusa come risorsa in Mscoree. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
