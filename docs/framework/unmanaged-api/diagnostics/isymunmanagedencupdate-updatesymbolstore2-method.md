---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5a7d678d03435aa483ae4a4102672df504199d6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550617"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a>Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, purché le informazioni sulla riga soddisfa i requisiti. Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pIStream`  
 [in] Un puntatore a un [IStream](/windows/desktop/api/objidl/nn-objidl-istream) che contiene le informazioni sulla riga.  
  
 `pDeltaLines`  
 [in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.  
  
 `cDeltaLines`  
 [in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ISymUnmanagedENCUpdate](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
