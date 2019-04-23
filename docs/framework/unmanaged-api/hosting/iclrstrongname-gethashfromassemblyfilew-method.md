---
title: Metodo ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 578dd7941ad7a2cf1d39a3aeed7fa823eb7efa79
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162164"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="cb996-102">Metodo ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="cb996-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="cb996-103">Genera un hash basato sul contenuto del file specificato da una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="cb996-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb996-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb996-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb996-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb996-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cb996-106">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="cb996-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="cb996-107">Questo parametro deve essere una stringa Unicode.</span><span class="sxs-lookup"><span data-stu-id="cb996-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cb996-108">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="cb996-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cb996-109">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="cb996-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cb996-110">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="cb996-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cb996-111">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cb996-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cb996-112">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cb996-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb996-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb996-113">Return Value</span></span>  
 <span data-ttu-id="cb996-114">`S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="cb996-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb996-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb996-115">Requirements</span></span>  
 <span data-ttu-id="cb996-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb996-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb996-117">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cb996-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cb996-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cb996-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb996-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb996-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb996-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb996-120">See also</span></span>

- [<span data-ttu-id="cb996-121">Metodo GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="cb996-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="cb996-122">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cb996-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
