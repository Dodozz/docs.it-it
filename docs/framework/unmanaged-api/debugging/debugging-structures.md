---
title: Strutture di debug
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23aa619d666f2e0b9eb67ab4cf8d4f92761865d3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415325"
---
# <a name="debugging-structures"></a><span data-ttu-id="3ee9e-102">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-102">Debugging Structures</span></span>
<span data-ttu-id="3ee9e-103">Questa sezione descrive le strutture non gestite usate dall'API di debug.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-103">This section describes the unmanaged structures that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ee9e-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3ee9e-104">In This Section</span></span>  
 [<span data-ttu-id="3ee9e-105">Struttura CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="3ee9e-105">CLR_DEBUGGING_VERSION Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 <span data-ttu-id="3ee9e-106">Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-106">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
 [<span data-ttu-id="3ee9e-107">Struttura1 CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="3ee9e-107">CodeChunkInfo Structure1</span></span>](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 <span data-ttu-id="3ee9e-108">Rappresenta un singolo blocco di codice in memoria.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-108">Represents a single chunk of code in memory.</span></span>  
  
 [<span data-ttu-id="3ee9e-109">Struttura CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="3ee9e-109">CorDebugBlockingObject Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 <span data-ttu-id="3ee9e-110">Definisce un oggetto che blocca un thread e il motivo del blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-110">Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>  
  
 [<span data-ttu-id="3ee9e-111">Struttura CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="3ee9e-111">CorDebugEHClause Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 <span data-ttu-id="3ee9e-112">Rappresenta una clausola di gestione delle eccezioni (EH, Exception Handling) per una determinata parte di codice del linguaggio intermedio (IL, Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="3ee9e-112">Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>  
  
 [<span data-ttu-id="3ee9e-113">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="3ee9e-113">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="3ee9e-114">Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-114">Represents stack frame information from an exception object.</span></span>  
  
 [<span data-ttu-id="3ee9e-115">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="3ee9e-115">CorDebugExceptionObjectStackFrame Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 <span data-ttu-id="3ee9e-116">Esegue il mapping una [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID all'oggetto corrispondente [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-116">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>  
  
 <span data-ttu-id="3ee9e-117">COR_ACTIVE_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="3ee9e-117">COR_ACTIVE_FUNCTION</span></span>  
 <span data-ttu-id="3ee9e-118">Contiene informazioni sulle funzioni attualmente attive nei frame di un thread.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-118">Contains information about the functions that are currently active in a thread's frames.</span></span>  
  
 [<span data-ttu-id="3ee9e-119">Struttura COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="3ee9e-119">COR_ARRAY_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 <span data-ttu-id="3ee9e-120">Fornisce informazioni sul layout di un oggetto Array in memoria.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-120">Provides information about the layout of an array object in memory.</span></span>  
  
 <span data-ttu-id="3ee9e-121">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="3ee9e-121">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
 <span data-ttu-id="3ee9e-122">Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-122">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
 <span data-ttu-id="3ee9e-123">COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="3ee9e-123">COR_DEBUG_STEP_RANGE</span></span>  
 <span data-ttu-id="3ee9e-124">Contene le informazioni sugli offset per un intervallo di codice.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-124">Contains the offset information for a range of code.</span></span>  
  
 [<span data-ttu-id="3ee9e-125">Struttura COR_FIELD</span><span class="sxs-lookup"><span data-stu-id="3ee9e-125">COR_FIELD Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 <span data-ttu-id="3ee9e-126">Fornisce informazioni su un campo in un oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-126">Provides information about a field in an object.</span></span>  
  
 [<span data-ttu-id="3ee9e-127">Struttura COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="3ee9e-127">COR_GC_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 <span data-ttu-id="3ee9e-128">Contiene informazioni su on oggetto da sottoporre a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-128">Contains information about an object that is to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="3ee9e-129">Struttura COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="3ee9e-129">COR_HEAPINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 <span data-ttu-id="3ee9e-130">Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-130">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
 [<span data-ttu-id="3ee9e-131">Struttura COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="3ee9e-131">COR_HEAPOBJECT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 <span data-ttu-id="3ee9e-132">Fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-132">Provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="3ee9e-133">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="3ee9e-133">COR_IL_MAP</span></span>  
 <span data-ttu-id="3ee9e-134">Specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-134">Specifies changes in the relative offset of a function.</span></span>  
  
 [<span data-ttu-id="3ee9e-135">Struttura COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="3ee9e-135">COR_SEGMENT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 <span data-ttu-id="3ee9e-136">Contiene informazioni su un'area della memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-136">Contains information about a region of memory in the managed heap.</span></span>  
  
 [<span data-ttu-id="3ee9e-137">Struttura COR_TYPEID</span><span class="sxs-lookup"><span data-stu-id="3ee9e-137">COR_TYPEID Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 <span data-ttu-id="3ee9e-138">Contiene un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-138">Contains a type identifier.</span></span>  
  
 [<span data-ttu-id="3ee9e-139">Struttura COR_TYPE_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="3ee9e-139">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 <span data-ttu-id="3ee9e-140">Fornisce informazioni sul layout di un oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-140">Provides information about the layout of an object in memory.</span></span>  
  
 <span data-ttu-id="3ee9e-141">COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="3ee9e-141">COR_VERSION</span></span>  
 <span data-ttu-id="3ee9e-142">Archivia il numero di versione in quattro parti standard di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-142">Stores the standard four-part version number of the common language runtime.</span></span>  
  
 [<span data-ttu-id="3ee9e-143">Struttura StackTrace_SimpleContext</span><span class="sxs-lookup"><span data-stu-id="3ee9e-143">StackTrace_SimpleContext Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 <span data-ttu-id="3ee9e-144">Fornisce un contesto semplice che può essere usato invece di una struttura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-144">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

 <span data-ttu-id="3ee9e-145">[Struttura CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) definisce un intervallo di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-145">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>
 
 <span data-ttu-id="3ee9e-146">[Struttura CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definisce un livello di integrità per il mapping dell'indirizzo</span><span class="sxs-lookup"><span data-stu-id="3ee9e-146">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>
 
 <span data-ttu-id="3ee9e-147">[Struttura DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definisce il contenitore per una richiesta del modulo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="3ee9e-147">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

  
## <a name="related-sections"></a><span data-ttu-id="3ee9e-148">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3ee9e-148">Related Sections</span></span>  
 [<span data-ttu-id="3ee9e-149">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-149">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="3ee9e-150">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="3ee9e-151">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-151">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="3ee9e-152">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-152">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="3ee9e-153">Debug</span><span class="sxs-lookup"><span data-stu-id="3ee9e-153">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
