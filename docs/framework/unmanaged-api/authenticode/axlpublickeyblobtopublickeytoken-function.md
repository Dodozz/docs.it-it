---
title: Funzione _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37957931f9d1e2f8da44f70e5b99d3544bf0ae4f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497496"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>Funzione _AxlPublicKeyBlobToPublicKeyToken
Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pCspPublicKeyBlob`  
 [in] BLOB a chiave pubblica CSP.  
  
 `ppwszPublicKeyHash`  
 [out] Puntatore a WCHAR * per ricevere l'hash di chiave pubblica con codifica esadecimale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.  
  
## <a name="see-also"></a>Vedere anche
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
