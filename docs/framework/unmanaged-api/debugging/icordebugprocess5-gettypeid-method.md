---
title: Metodo ICorDebugProcess5::GetTypeID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f58e4213959ca1cd6e65bc809a9ad964bebc31ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494792"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="f97d3-102">Metodo ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="f97d3-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="f97d3-103">Converte un indirizzo di oggetto a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identificatore.</span><span class="sxs-lookup"><span data-stu-id="f97d3-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f97d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f97d3-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f97d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f97d3-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="f97d3-106">[in] L'indirizzo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f97d3-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="f97d3-107">Un puntatore per il [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) valore che identifica l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="f97d3-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f97d3-108">Note</span><span class="sxs-lookup"><span data-stu-id="f97d3-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f97d3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f97d3-109">Requirements</span></span>  
 <span data-ttu-id="f97d3-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f97d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f97d3-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f97d3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f97d3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f97d3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f97d3-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f97d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f97d3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f97d3-114">See also</span></span>
- [<span data-ttu-id="f97d3-115">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="f97d3-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f97d3-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f97d3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
