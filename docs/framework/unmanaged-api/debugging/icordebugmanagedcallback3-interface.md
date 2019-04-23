---
title: Interfaccia ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acab49097059081540ec364d7f134d31432988a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108277"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="d7eca-102">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="d7eca-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="d7eca-103">Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="d7eca-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7eca-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d7eca-104">Methods</span></span>  
  
|<span data-ttu-id="d7eca-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d7eca-105">Method</span></span>|<span data-ttu-id="d7eca-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7eca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7eca-107">Metodo CustomNotification</span><span class="sxs-lookup"><span data-stu-id="d7eca-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="d7eca-108">Indica che è stata generata una notifica di debugger personalizzata abilitata.</span><span class="sxs-lookup"><span data-stu-id="d7eca-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7eca-109">Note</span><span class="sxs-lookup"><span data-stu-id="d7eca-109">Remarks</span></span>  
 <span data-ttu-id="d7eca-110">Questa interfaccia è un'estensione logica delle [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfacce.</span><span class="sxs-lookup"><span data-stu-id="d7eca-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7eca-111">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="d7eca-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7eca-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7eca-112">Requirements</span></span>  
 <span data-ttu-id="d7eca-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7eca-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7eca-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7eca-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7eca-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7eca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7eca-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7eca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7eca-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7eca-117">See also</span></span>

- [<span data-ttu-id="d7eca-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="d7eca-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="d7eca-119">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="d7eca-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d7eca-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d7eca-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d7eca-121">Debug</span><span class="sxs-lookup"><span data-stu-id="d7eca-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
