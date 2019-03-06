---
title: Metodo ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468780"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="dc536-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="dc536-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="dc536-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) tohoto objektu ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="dc536-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc536-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc536-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc536-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc536-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="dc536-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="dc536-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc536-107">Note</span><span class="sxs-lookup"><span data-stu-id="dc536-107">Remarks</span></span>  
 <span data-ttu-id="dc536-108">Il `ppFrame` parametro è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="dc536-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc536-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc536-109">Requirements</span></span>  
 <span data-ttu-id="dc536-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc536-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc536-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc536-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc536-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc536-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc536-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc536-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
