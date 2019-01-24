---
title: Interfaccia1 ICorDebugFunctionBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8403873fb7bc15e3109821bf738d7b68e20f878
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662686"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="6e29a-102">Interfaccia1 ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6e29a-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="6e29a-103">Estende l'interfaccia ICorDebugBreakpoint per supportare i punti di interruzione all'interno delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="6e29a-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e29a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6e29a-104">Methods</span></span>  
  
|<span data-ttu-id="6e29a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6e29a-105">Method</span></span>|<span data-ttu-id="6e29a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e29a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e29a-107">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="6e29a-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="6e29a-108">Ottiene un puntatore a interfaccia ICorDebugFunction che fa riferimento alla funzione in cui viene impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="6e29a-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="6e29a-109">Metodo GetOffset</span><span class="sxs-lookup"><span data-stu-id="6e29a-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="6e29a-110">Ottiene l'offset del punto di interruzione all'interno della funzione.</span><span class="sxs-lookup"><span data-stu-id="6e29a-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e29a-111">Note</span><span class="sxs-lookup"><span data-stu-id="6e29a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e29a-112">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6e29a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e29a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e29a-113">Requirements</span></span>  
 <span data-ttu-id="6e29a-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e29a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e29a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e29a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e29a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e29a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e29a-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e29a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e29a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e29a-118">See also</span></span>
- [<span data-ttu-id="6e29a-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6e29a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
