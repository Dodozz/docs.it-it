---
title: Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0651609e6d2597336ee42ceae752df7e561cd252
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692652"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="8fa2a-102">Metodo ICorProfilerInfo2::GetClassFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="8fa2a-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="8fa2a-103">Ottiene il `ClassID` di un tipo usando il token di metadati specificati e il `ClassID` valori di qualsiasi tipo di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fa2a-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fa2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fa2a-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="8fa2a-106">[in] L'ID del modulo in cui si trova il tipo.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="8fa2a-107">[in] Un `mdTypeDef` token di metadati che fa riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="8fa2a-108">[in] Il numero di parametri di tipo per il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="8fa2a-109">Questo valore deve essere zero per i tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="8fa2a-110">[in] Matrice di `ClassID` valori, ognuno dei quali è un argomento del tipo.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="8fa2a-111">Il valore di `typeArgs` può essere NULL se `cTypeArgs` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="8fa2a-112">[out] Un puntatore al `ClassID` del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fa2a-113">Note</span><span class="sxs-lookup"><span data-stu-id="8fa2a-113">Remarks</span></span>  
 <span data-ttu-id="8fa2a-114">Chiama il `GetClassFromTokenAndTypeArgs` metodo con un `mdTypeRef` invece di un `mdTypeDef` token di metadati possono produrre risultati imprevisti; i chiamanti devono risolvere il `mdTypeRef` a un `mdTypeDef` quando viene passato.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="8fa2a-115">Se il tipo non è già stato caricato, la chiamata `GetClassFromTokenAndTypeArgs` attiverà il caricamento, che è un'operazione pericolosa in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="8fa2a-116">Ad esempio, si chiama questo metodo durante il caricamento dei moduli o altri tipi di provocare un ciclo infinito come il runtime tenta di caricare in modo circolare le cose.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="8fa2a-117">In generale, usare di `GetClassFromTokenAndTypeArgs` è sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="8fa2a-118">Se profiler sono interessati agli eventi per un determinato tipo, è consigliabile archiviare il `ModuleID` e `mdTypeDef` di quel tipo e usare [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) per verificare se un determinato `ClassID` è quello del tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="8fa2a-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fa2a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8fa2a-119">Requirements</span></span>  
 <span data-ttu-id="8fa2a-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fa2a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fa2a-121">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8fa2a-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8fa2a-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fa2a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fa2a-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fa2a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa2a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa2a-124">See also</span></span>
- [<span data-ttu-id="8fa2a-125">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="8fa2a-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="8fa2a-126">Interfaccia ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="8fa2a-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
