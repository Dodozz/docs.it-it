---
title: Funzione _EFN_GetManagedObjectName
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a95008d98436161ac919ef307273bc797519f15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080618"
---
# <a name="efngetmanagedobjectname-function"></a><span data-ttu-id="17033-102">Funzione _EFN_GetManagedObjectName</span><span class="sxs-lookup"><span data-stu-id="17033-102">_EFN_GetManagedObjectName Function</span></span>
<span data-ttu-id="17033-103">Ottiene il nome di un tipo usando il puntatore all'oggetto gestito specificato.</span><span class="sxs-lookup"><span data-stu-id="17033-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17033-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17033-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17033-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17033-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="17033-106">[in] Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="17033-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="17033-107">[in] Un puntatore all'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="17033-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="17033-108">szName</span><span class="sxs-lookup"><span data-stu-id="17033-108">szName</span></span>  
 <span data-ttu-id="17033-109">[out] Il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="17033-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="17033-110">[out] Il numero di caratteri disponibili nel buffer di stringa.</span><span class="sxs-lookup"><span data-stu-id="17033-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17033-111">Note</span><span class="sxs-lookup"><span data-stu-id="17033-111">Remarks</span></span>  
 <span data-ttu-id="17033-112">Se non vi è nessun codice gestito sul thread attualmente nel contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore di impianto pari a 0xa0 e un codice di errore di 0x1000.</span><span class="sxs-lookup"><span data-stu-id="17033-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17033-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17033-113">Requirements</span></span>  
 <span data-ttu-id="17033-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17033-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17033-115">**Intestazione:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="17033-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="17033-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17033-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17033-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17033-117">See also</span></span>

- [<span data-ttu-id="17033-118">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="17033-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
