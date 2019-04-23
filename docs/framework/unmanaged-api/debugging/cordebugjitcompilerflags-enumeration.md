---
title: Enumerazione CorDebugJITCompilerFlags
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66a8ba59d221bb3fa2e815a1cbcfa79c474666cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105469"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="d2279-102">Enumerazione CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="d2279-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="d2279-103">Contiene valori che influenzano il comportamento del compilatore JIT gestito.</span><span class="sxs-lookup"><span data-stu-id="d2279-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2279-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2279-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d2279-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d2279-105">Members</span></span>  
  
|<span data-ttu-id="d2279-106">Member</span><span class="sxs-lookup"><span data-stu-id="d2279-106">Member</span></span>|<span data-ttu-id="d2279-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2279-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="d2279-108">Specifica che il compilatore deve tenere traccia dei dati di compilazione e consentire l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="d2279-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="d2279-109">Specifica che il compilatore deve tenere traccia dei dati di compilazione, ma disabilitare le ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d2279-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="d2279-110">Specifica che il compilatore deve tenere traccia dei dati di compilazione, disabilitare le ottimizzazioni e Abilita modifica e continuazione tecnologie.</span><span class="sxs-lookup"><span data-stu-id="d2279-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2279-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2279-111">Requirements</span></span>  
 <span data-ttu-id="d2279-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2279-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2279-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2279-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2279-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2279-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2279-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2279-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2279-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2279-116">See also</span></span>

- [<span data-ttu-id="d2279-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="d2279-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
