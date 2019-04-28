---
title: Metodo ICorProfilerThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44595229eaefa0d8fc8ca7bf15a88d0fbf1ee0d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787907"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="3d6ff-102">Metodo ICorProfilerThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="3d6ff-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="3d6ff-103">Ottiene il numero specificato di thread contigui da una raccolta sequenziale di moduli, a partire dalla posizione corrente dell'enumeratore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d6ff-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d6ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d6ff-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3d6ff-106">[in] Numero di thread da recuperare.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="3d6ff-107">[out] Matrice di valori `ThreadID`, ognuno dei quali rappresenta un thread recuperato.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3d6ff-108">[out] Puntatore al numero di thread effettivamente restituiti nella matrice `ids`.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d6ff-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d6ff-109">Return Value</span></span>  
 <span data-ttu-id="3d6ff-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3d6ff-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d6ff-111">HRESULT</span></span>|<span data-ttu-id="3d6ff-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d6ff-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d6ff-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d6ff-113">S_OK</span></span>|<span data-ttu-id="3d6ff-114">Sono stati restituiti `celt` elementi.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="3d6ff-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3d6ff-115">S_FALSE</span></span>|<span data-ttu-id="3d6ff-116">Sono stati restituiti meno di `celt` elementi, il che indica che l'enumerazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="3d6ff-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d6ff-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d6ff-117">Requirements</span></span>  
 <span data-ttu-id="3d6ff-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d6ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d6ff-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d6ff-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d6ff-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d6ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d6ff-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d6ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d6ff-122">See also</span></span>

- [<span data-ttu-id="3d6ff-123">Interfaccia ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="3d6ff-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="3d6ff-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3d6ff-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
