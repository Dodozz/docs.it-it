---
title: Metodo ICorDebugBreakpoint::Activate
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac37df58762dac4e3a6161361cafd8ea87e2657
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645383"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="dfff8-102">Metodo ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="dfff8-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="dfff8-103">Imposta lo stato attivo di questa `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="dfff8-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfff8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfff8-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfff8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfff8-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="dfff8-106">[in] Impostare questo valore su `true` per specificare lo stato come attivo; in caso contrario, impostare questo valore su `false`.</span><span class="sxs-lookup"><span data-stu-id="dfff8-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfff8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfff8-107">Requirements</span></span>  
 <span data-ttu-id="dfff8-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfff8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfff8-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfff8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfff8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfff8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfff8-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfff8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
