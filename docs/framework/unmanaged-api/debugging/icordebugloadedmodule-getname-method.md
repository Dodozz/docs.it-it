---
title: Metodo ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8b3b25c5e6e80b45ffc97e116c8649078f00861
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478713"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="f6988-102">Metodo ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="f6988-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="f6988-103">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="f6988-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6988-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6988-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6988-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6988-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f6988-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6988-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f6988-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6988-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f6988-108">[out] Matrice di caratteri che contiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="f6988-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6988-109">Note</span><span class="sxs-lookup"><span data-stu-id="f6988-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6988-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f6988-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6988-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6988-111">Requirements</span></span>  
 <span data-ttu-id="f6988-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6988-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6988-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6988-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6988-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6988-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6988-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6988-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6988-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6988-116">See also</span></span>
- [<span data-ttu-id="f6988-117">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="f6988-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="f6988-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f6988-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
