---
title: Enumerazione COR_PRF_CLAUSE_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 861f4c18f4c5151dc7215d300775928b88f018aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775193"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="0ec2a-102">Enumerazione COR_PRF_CLAUSE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0ec2a-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="0ec2a-103">Indica il tipo di clausola di eccezione in cui il codice è appena entrato o da cui è appena uscito.</span><span class="sxs-lookup"><span data-stu-id="0ec2a-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ec2a-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="0ec2a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0ec2a-105">Members</span></span>  
  
|<span data-ttu-id="0ec2a-106">Member</span><span class="sxs-lookup"><span data-stu-id="0ec2a-106">Member</span></span>|<span data-ttu-id="0ec2a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ec2a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="0ec2a-108">La clausola di eccezione non è valida.</span><span class="sxs-lookup"><span data-stu-id="0ec2a-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="0ec2a-109">La clausola di eccezione è un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="0ec2a-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="0ec2a-110">La clausola di eccezione è un `catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0ec2a-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="0ec2a-111">La clausola di eccezione è un `finally` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0ec2a-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ec2a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ec2a-112">Requirements</span></span>  
 <span data-ttu-id="0ec2a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ec2a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec2a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ec2a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ec2a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ec2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ec2a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec2a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ec2a-117">See also</span></span>

- [<span data-ttu-id="0ec2a-118">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="0ec2a-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
