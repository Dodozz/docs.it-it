---
title: Metodo ICorDebugAssembly2::IsFullyTrusted
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645565"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="a10f7-102">Metodo ICorDebugAssembly2::IsFullyTrusted</span><span class="sxs-lookup"><span data-stu-id="a10f7-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="a10f7-103">Ottiene un valore che indica se l'assembly è stata concessa l'attendibilità totale da sistema di sicurezza di runtime.</span><span class="sxs-lookup"><span data-stu-id="a10f7-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a10f7-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a10f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a10f7-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="a10f7-106">[out] `true` se l'assembly è stata concessa l'attendibilità totale da sistema di sicurezza di runtime; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a10f7-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a10f7-107">Note</span><span class="sxs-lookup"><span data-stu-id="a10f7-107">Remarks</span></span>  
 <span data-ttu-id="a10f7-108">Questo metodo restituisce un valore HRESULT di CORDBG_E_NOTREADY se i criteri di sicurezza per l'assembly non sono ancora stato risolto, vale a dire, se nessun codice nell'assembly è stato ancora eseguito.</span><span class="sxs-lookup"><span data-stu-id="a10f7-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10f7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a10f7-109">Requirements</span></span>  
 <span data-ttu-id="a10f7-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a10f7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a10f7-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a10f7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a10f7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a10f7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a10f7-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a10f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
