---
title: Metodo ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a173c23ea33532f05e30d072677715e15d04018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939477"
---
# <a name="isymunmanagedreadergetdocument-method"></a>Metodo ISymUnmanagedReader::GetDocument
Trova un documento. Il linguaggio del documento, fornitore e tipo sono facoltative.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a>Parametri  
 `url`  
 [in] L'URL che identifica il documento.  
  
 `language`  
 [in] Linguaggio del documento. Questo parametro è facoltativo.  
  
 `languageVendor`  
 [in] L'identità del fornitore del linguaggio del documento. Questo parametro è facoltativo.  
  
 `documentType`  
 [in] Il tipo del documento. Questo parametro è facoltativo.  
  
 `pRetVal`  
 [out] Puntatore a interfaccia restituito.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
