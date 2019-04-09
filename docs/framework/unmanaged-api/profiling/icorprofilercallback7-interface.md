---
title: Interfaccia ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81477010b22edee71098edfc1b8557db08b6038f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178633"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="7baae-102">Interfaccia ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="7baae-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="7baae-103">[Supportata in .NET Framework 4.6.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="7baae-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7baae-104">Sottoclasse di [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) che fornisce un metodo callback usato da Common Language Runtime per notificare al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="7baae-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7baae-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="7baae-105">Methods</span></span>  
  
|<span data-ttu-id="7baae-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="7baae-106">Method</span></span>|<span data-ttu-id="7baae-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7baae-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7baae-108">Metodo ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="7baae-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="7baae-109">Notifica al profiler che il flusso di simboli associato a un modulo in memoria è stato aggiornato.</span><span class="sxs-lookup"><span data-stu-id="7baae-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7baae-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7baae-110">Requirements</span></span>  
 <span data-ttu-id="7baae-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7baae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7baae-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7baae-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="7baae-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7baae-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7baae-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7baae-114">See also</span></span>

- [<span data-ttu-id="7baae-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="7baae-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
