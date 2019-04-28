---
title: Enumerazione CorDebugSetContextFlag
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5754968511f7b2db48f60b99748f10f5d27e8d21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599403"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="b9784-102">Enumerazione CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="b9784-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="b9784-103">Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.</span><span class="sxs-lookup"><span data-stu-id="b9784-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9784-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9784-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="b9784-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b9784-105">Members</span></span>  
  
|<span data-ttu-id="b9784-106">Member</span><span class="sxs-lookup"><span data-stu-id="b9784-106">Member</span></span>|<span data-ttu-id="b9784-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9784-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b9784-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="b9784-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="b9784-109">Il contesto è il contesto del thread attivo.</span><span class="sxs-lookup"><span data-stu-id="b9784-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="b9784-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="b9784-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="b9784-111">Il contesto è stato calcolato dalla rimozione da un altro frame.</span><span class="sxs-lookup"><span data-stu-id="b9784-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9784-112">Note</span><span class="sxs-lookup"><span data-stu-id="b9784-112">Remarks</span></span>  
 <span data-ttu-id="b9784-113">`CorDebugSetContextFlag` Fornisce i valori utilizzati per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b9784-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9784-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9784-114">Requirements</span></span>  
 <span data-ttu-id="b9784-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9784-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9784-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9784-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9784-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9784-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9784-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9784-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9784-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9784-119">See also</span></span>

- [<span data-ttu-id="b9784-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b9784-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="b9784-121">Debug</span><span class="sxs-lookup"><span data-stu-id="b9784-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
