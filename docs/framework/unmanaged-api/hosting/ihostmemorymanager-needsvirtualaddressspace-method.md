---
title: Metodo IHostMemoryManager::NeedsVirtualAddressSpace
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0f029c8fbab97afe3089956391e8446d4cc5e15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215495"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="313e4-102">Metodo IHostMemoryManager::NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="313e4-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="313e4-103">Notifica all'host che common language runtime (CLR) sta per tentare di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="313e4-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313e4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="313e4-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="313e4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="313e4-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="313e4-106">[in] Indirizzo iniziale della memoria.</span><span class="sxs-lookup"><span data-stu-id="313e4-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="313e4-107">[in] Le dimensioni, in byte, della memoria.</span><span class="sxs-lookup"><span data-stu-id="313e4-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="313e4-108">Note</span><span class="sxs-lookup"><span data-stu-id="313e4-108">Remarks</span></span>  
 <span data-ttu-id="313e4-109">Il `NeedsVirtualAddressSpace` metodo è un metodo di callback e devono essere implementato dal writer dell'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="313e4-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="313e4-110">Viene chiamato da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="313e4-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="313e4-111">Se l'host non desidera che il Common Language Runtime utilizza la memoria specificata, può restituire un valore HRESULT E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="313e4-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="313e4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="313e4-112">Requirements</span></span>  
 <span data-ttu-id="313e4-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="313e4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="313e4-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="313e4-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="313e4-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="313e4-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="313e4-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="313e4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="313e4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313e4-117">See also</span></span>

- [<span data-ttu-id="313e4-118">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="313e4-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
