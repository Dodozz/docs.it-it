---
title: Metodo ICorProfilerModuleEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d246acbf314a83ca3f8113e9a2fb223ac0ebcafe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223706"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="56293-102">Metodo ICorProfilerModuleEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="56293-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="56293-103">Ottiene il numero di moduli gestiti caricati nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="56293-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56293-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56293-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56293-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56293-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="56293-106">[out] Il numero di moduli CLR nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="56293-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56293-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56293-107">Requirements</span></span>  
 <span data-ttu-id="56293-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56293-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56293-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56293-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56293-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56293-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="56293-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56293-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56293-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56293-112">See also</span></span>

- [<span data-ttu-id="56293-113">Interfaccia ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="56293-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="56293-114">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="56293-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
