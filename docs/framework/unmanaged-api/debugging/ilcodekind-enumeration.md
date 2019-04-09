---
title: Enumerazione ILCodeKind
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7e20618180961ab6d8ad0bbb79a626a4a7f4f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145418"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="26c4c-102">Enumerazione ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="26c4c-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="26c4c-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="26c4c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="26c4c-104">Fornisce valori che specificano se il debugger può accedere a variabili locali o a codice aggiunto nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="26c4c-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c4c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26c4c-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="26c4c-106">Membri</span><span class="sxs-lookup"><span data-stu-id="26c4c-106">Members</span></span>  
  
|<span data-ttu-id="26c4c-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="26c4c-107">Member name</span></span>|<span data-ttu-id="26c4c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26c4c-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="26c4c-109">Il debugger non ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="26c4c-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="26c4c-110">Il debugger ha accesso alle informazioni della strumentazione ReJIT.</span><span class="sxs-lookup"><span data-stu-id="26c4c-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26c4c-111">Note</span><span class="sxs-lookup"><span data-stu-id="26c4c-111">Remarks</span></span>  
 <span data-ttu-id="26c4c-112">Un membro del `ILCodeKind` enumerazione renserlo passabile per il [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) e [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) metodi per determinare se il debugger può accedere a variabili aggiunte nella profiler Strumentazione ReJIT e di ottenere il [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) metodo per determinare se il debugger può accedere IL instrumentato.</span><span class="sxs-lookup"><span data-stu-id="26c4c-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c4c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="26c4c-113">Requirements</span></span>  
 <span data-ttu-id="26c4c-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26c4c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c4c-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26c4c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26c4c-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26c4c-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="26c4c-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="26c4c-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26c4c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26c4c-118">See also</span></span>

- [<span data-ttu-id="26c4c-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="26c4c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="26c4c-120">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="26c4c-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="26c4c-121">ReJIT: Informazioni di Guida</span><span class="sxs-lookup"><span data-stu-id="26c4c-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
