---
title: Metodo ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4c45290b1ef4360e51b5ed8e1b0fac3dcdde727
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217341"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="84a60-102">Metodo ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="84a60-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="84a60-103">Notifica al profiler che un thread è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="84a60-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84a60-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84a60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84a60-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="84a60-106">[in] L'ID del thread che sono stati eliminati definitivamente.</span><span class="sxs-lookup"><span data-stu-id="84a60-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84a60-107">Note</span><span class="sxs-lookup"><span data-stu-id="84a60-107">Remarks</span></span>  
 <span data-ttu-id="84a60-108">Il `threadId` valore non è più valido al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="84a60-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a60-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84a60-109">Requirements</span></span>  
 <span data-ttu-id="84a60-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a60-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a60-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84a60-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84a60-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84a60-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="84a60-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="84a60-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84a60-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a60-114">See also</span></span>

- [<span data-ttu-id="84a60-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="84a60-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="84a60-116">Metodo ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="84a60-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
