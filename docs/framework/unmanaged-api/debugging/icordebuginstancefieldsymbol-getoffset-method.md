---
title: Metodo ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8ea777755aebb59f3e865df26c38c74ef68ae31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203873"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="62c6a-102">Metodo ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="62c6a-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="62c6a-103">Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="62c6a-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62c6a-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62c6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62c6a-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="62c6a-106">Puntatore al numero di byte di offset di questo campo di istanza nella relativa classe padre.</span><span class="sxs-lookup"><span data-stu-id="62c6a-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c6a-107">Note</span><span class="sxs-lookup"><span data-stu-id="62c6a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62c6a-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="62c6a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c6a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62c6a-109">Requirements</span></span>  
 <span data-ttu-id="62c6a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c6a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c6a-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62c6a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62c6a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62c6a-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="62c6a-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="62c6a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62c6a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62c6a-114">See also</span></span>

- [<span data-ttu-id="62c6a-115">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="62c6a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="62c6a-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="62c6a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
