---
title: Metodo ICorDebugManagedCallback::CreateThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988273"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="dc9d6-102">Metodo ICorDebugManagedCallback::CreateThread</span><span class="sxs-lookup"><span data-stu-id="dc9d6-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="dc9d6-103">Notifica al debugger che ha avviato un thread esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dc9d6-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc9d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc9d6-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc9d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc9d6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dc9d6-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il thread.</span><span class="sxs-lookup"><span data-stu-id="dc9d6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="dc9d6-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="dc9d6-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc9d6-108">Note</span><span class="sxs-lookup"><span data-stu-id="dc9d6-108">Remarks</span></span>  
 <span data-ttu-id="dc9d6-109">Il thread viene collocato nella prima istruzione di codice gestito deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="dc9d6-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc9d6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc9d6-110">Requirements</span></span>  
 <span data-ttu-id="dc9d6-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc9d6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc9d6-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc9d6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc9d6-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc9d6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc9d6-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc9d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9d6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc9d6-115">See also</span></span>

- [<span data-ttu-id="dc9d6-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dc9d6-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
