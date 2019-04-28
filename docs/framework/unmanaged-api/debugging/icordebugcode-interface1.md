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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750248"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="ea62b-102">Interfaccia ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="ea62b-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="ea62b-103">Rappresenta un segmento di codice MSIL (Microsoft Intermediate Language) o di codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ea62b-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea62b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ea62b-104">Methods</span></span>  
  
|<span data-ttu-id="ea62b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ea62b-105">Method</span></span>|<span data-ttu-id="ea62b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea62b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea62b-107">Metodo CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ea62b-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="ea62b-108">Crea un punto di interruzione in corrispondenza dell'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="ea62b-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="ea62b-109">Metodo GetAddress</span><span class="sxs-lookup"><span data-stu-id="ea62b-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="ea62b-110">Ottiene l'indirizzo virtuale relativo (RVA) del segmento di codice che questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="ea62b-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="ea62b-111">Metodo GetCode</span><span class="sxs-lookup"><span data-stu-id="ea62b-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="ea62b-112">Ottiene tutto il codice per la funzione specificata, formattata per il disassembly.</span><span class="sxs-lookup"><span data-stu-id="ea62b-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="ea62b-113">Questo metodo è deprecato. usare [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="ea62b-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="ea62b-114">Metodo GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="ea62b-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="ea62b-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="ea62b-115">Not implemented.</span></span>|  
|[<span data-ttu-id="ea62b-116">Metodo GetFunction</span><span class="sxs-lookup"><span data-stu-id="ea62b-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="ea62b-117">Ottiene il "ICorDebugFunction" associato a questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ea62b-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="ea62b-118">Metodo GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="ea62b-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="ea62b-119">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping dagli offset MSIL agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="ea62b-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="ea62b-120">Metodo GetSize</span><span class="sxs-lookup"><span data-stu-id="ea62b-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="ea62b-121">Ottiene la dimensione, espressa in byte, del codice binario rappresentato da questo `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="ea62b-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="ea62b-122">Metodo GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="ea62b-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="ea62b-123">Ottiene il numero in base 1 che identifica la versione del codice che questo `ICorDebugCode` rappresenta.</span><span class="sxs-lookup"><span data-stu-id="ea62b-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="ea62b-124">Metodo IsIL</span><span class="sxs-lookup"><span data-stu-id="ea62b-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="ea62b-125">Ottiene un valore che indica se questo `ICorDebugCode` viene compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="ea62b-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea62b-126">Note</span><span class="sxs-lookup"><span data-stu-id="ea62b-126">Remarks</span></span>  
 <span data-ttu-id="ea62b-127">`ICorDebugCode` può rappresentare MSIL o codice nativo.</span><span class="sxs-lookup"><span data-stu-id="ea62b-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="ea62b-128">Un oggetto "ICorDebugFunction" che rappresenta il codice MSIL può avere zero o uno `ICorDebugCode` associati oggetti.</span><span class="sxs-lookup"><span data-stu-id="ea62b-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="ea62b-129">Un oggetto "ICorDebugFunction" che rappresenta il codice nativo può avere un numero qualsiasi di `ICorDebugCode` associati oggetti.</span><span class="sxs-lookup"><span data-stu-id="ea62b-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea62b-130">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ea62b-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea62b-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea62b-131">Requirements</span></span>  
 <span data-ttu-id="ea62b-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea62b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea62b-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea62b-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea62b-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea62b-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea62b-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea62b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea62b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea62b-136">See also</span></span>

- [<span data-ttu-id="ea62b-137">Interfaccia ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="ea62b-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="ea62b-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ea62b-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
