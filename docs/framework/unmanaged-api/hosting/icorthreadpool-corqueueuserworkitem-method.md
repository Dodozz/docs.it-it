---
title: Metodo ICorThreadpool::CorQueueUserWorkItem
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b13a2342510b48e72c7fd535cd085d0f50ca474
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534657"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="68a39-102">Metodo ICorThreadpool::CorQueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="68a39-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="68a39-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="68a39-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68a39-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="68a39-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68a39-105">Requirements</span></span>  
 <span data-ttu-id="68a39-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68a39-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a39-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68a39-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68a39-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="68a39-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68a39-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a39-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a39-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68a39-110">See also</span></span>
- [<span data-ttu-id="68a39-111">Interfaccia ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="68a39-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
