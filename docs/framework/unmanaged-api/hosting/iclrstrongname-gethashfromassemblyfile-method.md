---
title: Metodo ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 714827da24b3fc0a334210fd94e61f80cb2afe49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135758"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="15c00-102">Metodo ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="15c00-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="15c00-103">Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.</span><span class="sxs-lookup"><span data-stu-id="15c00-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15c00-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15c00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15c00-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="15c00-106">[in] Il percorso del file di cui eseguire l'hashing.</span><span class="sxs-lookup"><span data-stu-id="15c00-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="15c00-107">[in, out] Costante che specifica l'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="15c00-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="15c00-108">Usa lo zero per l'algoritmo hash predefinito.</span><span class="sxs-lookup"><span data-stu-id="15c00-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="15c00-109">[out] Il buffer di hash restituito.</span><span class="sxs-lookup"><span data-stu-id="15c00-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="15c00-110">[in] La dimensione massima richiesta del `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="15c00-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="15c00-111">[out] La dimensione restituita, in byte, di `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="15c00-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15c00-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="15c00-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="15c00-113">Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).</span><span class="sxs-lookup"><span data-stu-id="15c00-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c00-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15c00-114">Requirements</span></span>  
 <span data-ttu-id="15c00-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15c00-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15c00-116">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="15c00-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15c00-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="15c00-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="15c00-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="15c00-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15c00-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c00-119">See also</span></span>

- [<span data-ttu-id="15c00-120">Metodo GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="15c00-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="15c00-121">Interfaccia ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="15c00-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
