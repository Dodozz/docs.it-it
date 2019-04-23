---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223537"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="e5f19-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="e5f19-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="e5f19-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="e5f19-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5f19-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5f19-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="e5f19-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="e5f19-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5f19-107">Note</span><span class="sxs-lookup"><span data-stu-id="e5f19-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5f19-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e5f19-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f19-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5f19-109">Requirements</span></span>  
 <span data-ttu-id="e5f19-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f19-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f19-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5f19-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5f19-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f19-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f19-113">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f19-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f19-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5f19-114">See also</span></span>

- [<span data-ttu-id="e5f19-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="e5f19-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="e5f19-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e5f19-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
