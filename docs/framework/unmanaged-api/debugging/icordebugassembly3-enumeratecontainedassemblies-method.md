---
title: Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa99e7289e0e86032f7bb85bbe209932f5c50d16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627577"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="be85b-102">Metodo ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="be85b-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="be85b-103">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="be85b-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be85b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be85b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be85b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be85b-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="be85b-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugAssemblyEnum che corrisponde all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="be85b-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be85b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be85b-107">Return Value</span></span>  
 <span data-ttu-id="be85b-108">`S_OK` se questo oggetto `ICorDebugAssembly3` è un contenitore, altrimenti `S_FALSE` e l'enumerazione è vuota.</span><span class="sxs-lookup"><span data-stu-id="be85b-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be85b-109">Note</span><span class="sxs-lookup"><span data-stu-id="be85b-109">Remarks</span></span>  
 <span data-ttu-id="be85b-110">I simboli sono necessari per enumerare gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="be85b-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="be85b-111">Se non ce ne sono, il metodo restituisce `S_FALSE` e non viene fornito alcun enumeratore valido.</span><span class="sxs-lookup"><span data-stu-id="be85b-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be85b-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="be85b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be85b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be85b-113">Requirements</span></span>  
 <span data-ttu-id="be85b-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be85b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be85b-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be85b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be85b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be85b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be85b-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be85b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be85b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be85b-118">See also</span></span>
- [<span data-ttu-id="be85b-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="be85b-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="be85b-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="be85b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
