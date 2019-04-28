---
title: Metodo ICorProfilerCallback2::FinalizeableObjectQueued
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b99a942d5c5fb205a84dd3766c99cc1126998de8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914429"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="6ad96-102">Metodo ICorProfilerCallback2::FinalizeableObjectQueued</span><span class="sxs-lookup"><span data-stu-id="6ad96-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="6ad96-103">Notifica al profiler di codice che un oggetto con un finalizzatore è stato accodato al thread del finalizzatore per l'esecuzione del relativo `Finalize` (metodo).</span><span class="sxs-lookup"><span data-stu-id="6ad96-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad96-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ad96-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ad96-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ad96-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="6ad96-106">[in] Valore di [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumerazione che descrive gli aspetti del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="6ad96-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="6ad96-107">[in] L'ID dell'oggetto che è stata accodata.</span><span class="sxs-lookup"><span data-stu-id="6ad96-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ad96-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ad96-108">Requirements</span></span>  
 <span data-ttu-id="6ad96-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ad96-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ad96-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ad96-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ad96-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ad96-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ad96-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ad96-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad96-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ad96-113">See also</span></span>

- [<span data-ttu-id="6ad96-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6ad96-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6ad96-115">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="6ad96-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
