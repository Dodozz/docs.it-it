---
title: Metodo IGCHost::GetThreadStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c3d71c75527daa9a9c130d5aaa0d6838816c276
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559424"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="90c68-102">Metodo IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="90c68-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="90c68-103">Ottiene le statistiche per ogni thread di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="90c68-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90c68-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90c68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90c68-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="90c68-106">[in] Puntatore a un fiber cookie che specifica il thread per il quale recuperare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="90c68-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="90c68-107">[in, out] Un puntatore a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) struttura che contiene le statistiche di garbage collection per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="90c68-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c68-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90c68-108">Requirements</span></span>  
 <span data-ttu-id="90c68-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90c68-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c68-110">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="90c68-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="90c68-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="90c68-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90c68-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c68-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c68-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90c68-113">See also</span></span>
- [<span data-ttu-id="90c68-114">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="90c68-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
