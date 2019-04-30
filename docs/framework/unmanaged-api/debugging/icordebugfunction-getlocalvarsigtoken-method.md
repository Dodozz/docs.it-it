---
title: Metodo ICorDebugFunction::GetLocalVarSigToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a682999c888a93cef94162a8179673c862dc43ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988715"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="db387-102">Metodo ICorDebugFunction::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="db387-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="db387-103">Ottiene i metadati del token per la firma della variabile locale della funzione che è rappresentata da questa istanza ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="db387-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db387-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db387-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db387-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db387-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="db387-106">[out] Un puntatore per il `mdSignature` token di firma della variabile locale di questa funzione, o `mdSignatureNil`, se questa funzione non ha variabili locali.</span><span class="sxs-lookup"><span data-stu-id="db387-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db387-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db387-107">Requirements</span></span>  
 <span data-ttu-id="db387-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db387-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db387-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db387-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db387-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db387-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db387-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db387-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
