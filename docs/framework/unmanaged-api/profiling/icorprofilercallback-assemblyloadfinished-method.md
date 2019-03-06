---
title: Metodo ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bb5586271c252879b503dd093c88380197d5bce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479727"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="137f0-102">Metodo ICorProfilerCallback::AssemblyLoadFinished</span><span class="sxs-lookup"><span data-stu-id="137f0-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="137f0-103">Notifica al profiler che un assembly ha terminato il caricamento.</span><span class="sxs-lookup"><span data-stu-id="137f0-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="137f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="137f0-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="137f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="137f0-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="137f0-106">[in] Identifica l'assembly che è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="137f0-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="137f0-107">[in] HRESULT che indica se l'assembly è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="137f0-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="137f0-108">Note</span><span class="sxs-lookup"><span data-stu-id="137f0-108">Remarks</span></span>  
 <span data-ttu-id="137f0-109">Il valore di `assemblyId` non è valido per una richiesta di informazioni finché non la `AssemblyLoadFinished` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="137f0-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="137f0-110">Alcune parti del caricamento dell'assembly potrebbero continuare dopo il `AssemblyLoadFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="137f0-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="137f0-111">Un HRESULT di errore in `hrStatus` indica un errore.</span><span class="sxs-lookup"><span data-stu-id="137f0-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="137f0-112">Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="137f0-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="137f0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="137f0-113">Requirements</span></span>  
 <span data-ttu-id="137f0-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="137f0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="137f0-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="137f0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="137f0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="137f0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="137f0-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="137f0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="137f0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="137f0-118">See also</span></span>
- [<span data-ttu-id="137f0-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="137f0-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
