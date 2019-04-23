---
title: Metodo ICorDebug::SetManagedHandler
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f30089879f2d023c8fb04b52e75b2942da2a83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130169"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="888a8-102">Metodo ICorDebug::SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="888a8-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="888a8-103">Specifica l'oggetto di gestore eventi per gli eventi gestiti.</span><span class="sxs-lookup"><span data-stu-id="888a8-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="888a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="888a8-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="888a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="888a8-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="888a8-106">[in] Un puntatore a un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) oggetto, ovvero l'oggetto gestore evento.</span><span class="sxs-lookup"><span data-stu-id="888a8-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="888a8-107">Note</span><span class="sxs-lookup"><span data-stu-id="888a8-107">Remarks</span></span>  
 <span data-ttu-id="888a8-108">`SetManagedHandler` deve essere chiamato in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="888a8-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="888a8-109">Se il `ICorDebugManagedCallback` implementazione non contiene interfacce sufficienti per gestire gli eventi di debug per l'applicazione in fase di debug, `SetManagedHandler` restituisce un HRESULT di tipo E_NOINTERFACE.</span><span class="sxs-lookup"><span data-stu-id="888a8-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="888a8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="888a8-110">Requirements</span></span>  
 <span data-ttu-id="888a8-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="888a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="888a8-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="888a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="888a8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="888a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="888a8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="888a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="888a8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="888a8-115">See also</span></span>

- [<span data-ttu-id="888a8-116">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="888a8-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
