---
title: Funzione _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 448712561f1531a055ac141db9825581525c779c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106704"
---
# <a name="axlgetissuerpublickeyhash-function"></a><span data-ttu-id="635f1-102">Funzione _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="635f1-102">_AxlGetIssuerPublicKeyHash Function</span></span>
<span data-ttu-id="635f1-103">Recupera l'hash SHA-1 della chiave pubblica associata alla chiave privata usata per firmare il certificato specificato.</span><span class="sxs-lookup"><span data-stu-id="635f1-103">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="635f1-104">Syntax</span></span>  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="635f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="635f1-105">Parameters</span></span>  
 `pChainContext`  
 <span data-ttu-id="635f1-106">[in] BLOB a chiave pubblica CSP.</span><span class="sxs-lookup"><span data-stu-id="635f1-106">[in] The CSP public key blob.</span></span> <span data-ttu-id="635f1-107">Vedere le [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) struttura.</span><span class="sxs-lookup"><span data-stu-id="635f1-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="635f1-108">[out] Puntatore a WCHAR \* per ricevere il token di chiave pubblica con codifica esadecimale.</span><span class="sxs-lookup"><span data-stu-id="635f1-108">[out] A pointer to WCHAR \* to receive the hex-encoded public key token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="635f1-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="635f1-109">Return Value</span></span>  
 <span data-ttu-id="635f1-110">`S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.</span><span class="sxs-lookup"><span data-stu-id="635f1-110">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635f1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="635f1-111">See also</span></span>

- [<span data-ttu-id="635f1-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="635f1-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
