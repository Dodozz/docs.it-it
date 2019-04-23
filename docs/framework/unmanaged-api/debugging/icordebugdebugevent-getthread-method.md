---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103768918f67ca695a47c52b9cd97f24fb8d46ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081580"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="9253a-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="9253a-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="9253a-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="9253a-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9253a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9253a-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9253a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9253a-105">Parameters</span></span>  
 <span data-ttu-id="9253a-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="9253a-106">ppThread</span></span>  
 <span data-ttu-id="9253a-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="9253a-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9253a-108">Note</span><span class="sxs-lookup"><span data-stu-id="9253a-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9253a-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9253a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9253a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9253a-110">Requirements</span></span>  
 <span data-ttu-id="9253a-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9253a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9253a-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9253a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9253a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9253a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9253a-114">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9253a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9253a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9253a-115">See also</span></span>

- [<span data-ttu-id="9253a-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9253a-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="9253a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9253a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
