---
title: Interfaccia ICorDebugCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca47eb5508907297a78dba1ab2b0a6d2b8ece0d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976928"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="6b488-102">Interfaccia ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="6b488-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="6b488-103">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6b488-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b488-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6b488-104">Methods</span></span>  
  
|<span data-ttu-id="6b488-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6b488-105">Method</span></span>|<span data-ttu-id="6b488-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b488-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b488-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="6b488-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="6b488-108">Crea un punto di interruzione in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="6b488-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="6b488-109">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="6b488-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="6b488-110">Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="6b488-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="6b488-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="6b488-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="6b488-112">Ottiene tutto il codice per la funzione specificata, formattata per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="6b488-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="6b488-113">Questo metodo è deprecato. usare [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="6b488-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="6b488-114">Metodo GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="6b488-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="6b488-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="6b488-115">Not implemented.</span></span>|  
|[<span data-ttu-id="6b488-116">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="6b488-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="6b488-117">Ottiene il "ICorDebugFunction" associato a questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="6b488-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="6b488-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="6b488-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="6b488-119">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping dagli offset MSIL agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="6b488-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="6b488-120">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="6b488-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="6b488-121">Ottiene la dimensione, espressa in byte, del codice binario rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="6b488-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="6b488-122">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="6b488-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="6b488-123">Ottiene il numero in base 1 che identifica la versione del codice che questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="6b488-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="6b488-124">Metodo IsIL</span><span class="sxs-lookup"><span data-stu-id="6b488-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="6b488-125">Ottiene un valore che indica se questo `ICorDebugCode` viene compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="6b488-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b488-126">Note</span><span class="sxs-lookup"><span data-stu-id="6b488-126">Remarks</span></span>  
 <span data-ttu-id="6b488-127">`ICorDebugCode` può rappresentare MSIL o codice nativo.</span><span class="sxs-lookup"><span data-stu-id="6b488-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="6b488-128">Un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può avere zero o uno `ICorDebugCode` associati oggetti.</span><span class="sxs-lookup"><span data-stu-id="6b488-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="6b488-129">Un oggetto "ICorDebugFunction" che rappresenta il codice nativo può avere un numero qualsiasi di `ICorDebugCode` associati oggetti.</span><span class="sxs-lookup"><span data-stu-id="6b488-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b488-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6b488-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b488-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b488-131">Requirements</span></span>  
 <span data-ttu-id="6b488-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b488-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b488-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b488-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b488-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b488-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b488-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b488-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b488-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b488-136">See also</span></span>

- [<span data-ttu-id="6b488-137">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="6b488-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="6b488-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6b488-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
