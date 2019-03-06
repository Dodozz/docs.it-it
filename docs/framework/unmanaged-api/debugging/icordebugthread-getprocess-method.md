---
title: Metodo ICorDebugThread::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46aa2ec5a282ef56f28d5fa0499571028e6602e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483628"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="63d22-102">Metodo ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="63d22-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="63d22-103">Ottiene un puntatore a interfaccia per il processo di cui ICorDebugThread costituisce una parte.</span><span class="sxs-lookup"><span data-stu-id="63d22-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63d22-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d22-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63d22-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="63d22-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="63d22-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d22-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63d22-107">Requirements</span></span>  
 <span data-ttu-id="63d22-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d22-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d22-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63d22-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63d22-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d22-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d22-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d22-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
