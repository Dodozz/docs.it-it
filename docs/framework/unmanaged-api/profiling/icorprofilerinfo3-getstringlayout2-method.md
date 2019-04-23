---
title: Metodo ICorProfilerInfo3::GetStringLayout2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0957228489df30833790e59da1ca597fc1f92f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076507"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="d99e2-102">Metodo ICorProfilerInfo3::GetStringLayout2</span><span class="sxs-lookup"><span data-stu-id="d99e2-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="d99e2-103">Ottiene informazioni sul layout di un oggetto stringa.</span><span class="sxs-lookup"><span data-stu-id="d99e2-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="d99e2-104">Questo metodo sostituisce le [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d99e2-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d99e2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d99e2-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d99e2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d99e2-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="d99e2-107">[out] Un puntatore all'offset della posizione relativa per il `ObjectID` puntatore, che archivia la lunghezza della stringa stessa.</span><span class="sxs-lookup"><span data-stu-id="d99e2-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="d99e2-108">La lunghezza viene archiviata come un `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="d99e2-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="d99e2-109">[out] L'offset del buffer relativo a un puntatore di `ObjectID` puntatore, che archivia la stringa di caratteri "wide".</span><span class="sxs-lookup"><span data-stu-id="d99e2-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d99e2-110">Note</span><span class="sxs-lookup"><span data-stu-id="d99e2-110">Remarks</span></span>  
 <span data-ttu-id="d99e2-111">Le stringhe possono o potrebbero non essere con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="d99e2-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d99e2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d99e2-112">Requirements</span></span>  
 <span data-ttu-id="d99e2-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d99e2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d99e2-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d99e2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d99e2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d99e2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d99e2-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d99e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99e2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d99e2-117">See also</span></span>

- [<span data-ttu-id="d99e2-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="d99e2-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d99e2-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d99e2-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
