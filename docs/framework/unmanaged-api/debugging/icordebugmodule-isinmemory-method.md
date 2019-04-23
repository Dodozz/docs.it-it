---
title: Metodo ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d79a8b0c3c56ffe2b8f57ec26f5942ee0d681194
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187590"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="1a684-102">Metodo ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="1a684-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="1a684-103">Ottiene un valore che indica se questo modulo esiste solo in memoria.</span><span class="sxs-lookup"><span data-stu-id="1a684-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a684-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a684-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a684-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1a684-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="1a684-106">[out] `true` se questo modulo esiste solo in memoria; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1a684-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a684-107">Note</span><span class="sxs-lookup"><span data-stu-id="1a684-107">Remarks</span></span>  
 <span data-ttu-id="1a684-108">Common language runtime (CLR) supporta il caricamento dei moduli da flussi di byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="1a684-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="1a684-109">Questi moduli sono denominati *i moduli in memoria* e non esistono sul disco.</span><span class="sxs-lookup"><span data-stu-id="1a684-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a684-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a684-110">Requirements</span></span>  
 <span data-ttu-id="1a684-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a684-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a684-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a684-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a684-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a684-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a684-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a684-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a684-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a684-115">See also</span></span>
