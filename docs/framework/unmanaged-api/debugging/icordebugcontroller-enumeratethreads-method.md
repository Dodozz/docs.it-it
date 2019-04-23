---
title: Metodo ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ba15553d2e7dcd2090870eaab54b4c680631f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163085"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="9084c-102">Metodo ICorDebugController::EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="9084c-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="9084c-103">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="9084c-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9084c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9084c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9084c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9084c-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="9084c-106">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugThreadEnum" che rappresenta un enumeratore per tutti i thread gestiti che sono attive nel processo.</span><span class="sxs-lookup"><span data-stu-id="9084c-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9084c-107">Note</span><span class="sxs-lookup"><span data-stu-id="9084c-107">Remarks</span></span>  
 <span data-ttu-id="9084c-108">Un thread è considerato attivo dopo il [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback è stato inviato e prima di [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback è stato inviato .</span><span class="sxs-lookup"><span data-stu-id="9084c-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="9084c-109">Un thread gestito può non avere necessariamente frame gestiti nel relativo stack.</span><span class="sxs-lookup"><span data-stu-id="9084c-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="9084c-110">I thread possono essere enumerati anche prima che il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="9084c-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="9084c-111">L'enumerazione naturalmente sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="9084c-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9084c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9084c-112">Requirements</span></span>  
 <span data-ttu-id="9084c-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9084c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9084c-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9084c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9084c-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9084c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9084c-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9084c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9084c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9084c-117">See also</span></span>
