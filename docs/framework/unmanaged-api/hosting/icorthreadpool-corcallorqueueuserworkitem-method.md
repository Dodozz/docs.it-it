---
title: Metodo ICorThreadpool::CorCallOrQueueUserWorkItem
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7dd4589da9b59d7e701ac641c8d45be3735d0b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199167"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="032f5-102">Metodo ICorThreadpool::CorCallOrQueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="032f5-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="032f5-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="032f5-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="032f5-104">Syntax</span></span>  
  
```  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="032f5-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="032f5-105">Requirements</span></span>  
 <span data-ttu-id="032f5-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="032f5-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032f5-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="032f5-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="032f5-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="032f5-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="032f5-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032f5-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032f5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="032f5-110">See also</span></span>

- [<span data-ttu-id="032f5-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="032f5-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
