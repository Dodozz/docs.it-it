---
title: Funzione GetHashFromHandle
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64c71f1263ae6fd2c72126ec83bda74d5902a311
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469105"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="c2a2c-102">Funzione GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="c2a2c-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="c2a2c-103">Genera un hash basato sul contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="c2a2c-104">Questa funzione è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-104">This function has been deprecated.</span></span> <span data-ttu-id="c2a2c-105">Usare la [GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a2c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2a2c-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a2c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2a2c-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="c2a2c-108">[in] L'handle del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c2a2c-109">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="c2a2c-110">Usa lo zero per l'algoritmo predefinito.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c2a2c-111">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c2a2c-112">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c2a2c-113">[out] Le dimensioni, in byte, del valore restituito `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="c2a2c-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a2c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2a2c-114">Requirements</span></span>  
 <span data-ttu-id="c2a2c-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a2c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a2c-116">**Intestazione:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c2a2c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c2a2c-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c2a2c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a2c-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a2c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a2c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2a2c-119">See also</span></span>
- [<span data-ttu-id="c2a2c-120">Metodo GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="c2a2c-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="c2a2c-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c2a2c-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
