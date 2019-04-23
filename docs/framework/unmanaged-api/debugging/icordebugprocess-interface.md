---
title: Interfaccia ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216795"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="dea85-102">Interfaccia ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="dea85-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="dea85-103">Rappresenta un processo che esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dea85-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="dea85-104">Questa interfaccia è una sottoclasse di ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="dea85-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dea85-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dea85-105">Methods</span></span>  
  
|<span data-ttu-id="dea85-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="dea85-106">Method</span></span>|<span data-ttu-id="dea85-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dea85-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dea85-108">Metodo ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="dea85-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="dea85-109">Cancella l'eccezione non gestita corrente sul thread specificato.</span><span class="sxs-lookup"><span data-stu-id="dea85-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="dea85-110">Metodo EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="dea85-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="dea85-111">Abilita e disabilita l'invio di messaggi di log per il debugger.</span><span class="sxs-lookup"><span data-stu-id="dea85-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="dea85-112">Metodo EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="dea85-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="dea85-113">Enumera tutti i domini applicazione nel processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="dea85-114">Metodo EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="dea85-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="dea85-115">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="dea85-115">Not implemented.</span></span>|  
|[<span data-ttu-id="dea85-116">Metodo GetHandle</span><span class="sxs-lookup"><span data-stu-id="dea85-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="dea85-117">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="dea85-118">Metodo GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="dea85-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="dea85-119">Ottiene l'ID del thread del sistema operativo (OS) per il thread di supporto interno del debugger.</span><span class="sxs-lookup"><span data-stu-id="dea85-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="dea85-120">Metodo GetID</span><span class="sxs-lookup"><span data-stu-id="dea85-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="dea85-121">Ottiene l'ID del sistema operativo (OS) del processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="dea85-122">Metodo GetObject</span><span class="sxs-lookup"><span data-stu-id="dea85-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="dea85-123">Non implementato.</span><span class="sxs-lookup"><span data-stu-id="dea85-123">Not implemented.</span></span>|  
|[<span data-ttu-id="dea85-124">Metodo GetThread</span><span class="sxs-lookup"><span data-stu-id="dea85-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="dea85-125">Ottiene l'istanza ICorDebugThread con il thread del sistema operativo specificato ID.</span><span class="sxs-lookup"><span data-stu-id="dea85-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="dea85-126">Metodo GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dea85-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="dea85-127">Ottiene il contesto per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="dea85-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="dea85-128">Metodo IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="dea85-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="dea85-129">Determina se il thread è stata sospesa a causa del debugger l'interruzione del processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="dea85-130">Metodo IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="dea85-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="dea85-131">Determina se un indirizzo è all'interno di uno stub che causa una transizione al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dea85-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="dea85-132">Metodo ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="dea85-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="dea85-133">Imposta il livello di gravità dell'opzione di log specificato.</span><span class="sxs-lookup"><span data-stu-id="dea85-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="dea85-134">Metodo ReadMemory</span><span class="sxs-lookup"><span data-stu-id="dea85-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="dea85-135">Legge memoria dal processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="dea85-136">Metodo SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dea85-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="dea85-137">Imposta il contesto per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="dea85-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="dea85-138">Metodo ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="dea85-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="dea85-139">Deprecato.</span><span class="sxs-lookup"><span data-stu-id="dea85-139">Deprecated.</span></span>|  
|[<span data-ttu-id="dea85-140">Metodo WriteMemory</span><span class="sxs-lookup"><span data-stu-id="dea85-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="dea85-141">Scrive dati in un'area di memoria del processo.</span><span class="sxs-lookup"><span data-stu-id="dea85-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dea85-142">Note</span><span class="sxs-lookup"><span data-stu-id="dea85-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dea85-143">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="dea85-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea85-144">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dea85-144">Requirements</span></span>  
 <span data-ttu-id="dea85-145">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dea85-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea85-146">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dea85-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dea85-147">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dea85-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dea85-148">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea85-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea85-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dea85-149">See also</span></span>

- [<span data-ttu-id="dea85-150">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="dea85-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="dea85-151">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="dea85-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
