---
title: Interfaccia ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5206b7cd07acd76237ab72268b492782ac6e49ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616719"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="1c904-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="1c904-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="1c904-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati in sulla pubblicazione delle informazioni sui processi e domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1c904-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c904-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1c904-104">Methods</span></span>  
  
|<span data-ttu-id="1c904-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1c904-105">Method</span></span>|<span data-ttu-id="1c904-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c904-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c904-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="1c904-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="1c904-108">Crea una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c904-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="1c904-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="1c904-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="1c904-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1c904-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="1c904-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="1c904-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="1c904-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1c904-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="1c904-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="1c904-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="1c904-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="1c904-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c904-115">Note</span><span class="sxs-lookup"><span data-stu-id="1c904-115">Remarks</span></span>  
 <span data-ttu-id="1c904-116">Gli enumeratori seguenti derivano da `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="1c904-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="1c904-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="1c904-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="1c904-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="1c904-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="1c904-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c904-119">Requirements</span></span>  
 <span data-ttu-id="1c904-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c904-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c904-121">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="1c904-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1c904-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c904-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c904-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c904-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c904-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c904-124">See also</span></span>
- [<span data-ttu-id="1c904-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="1c904-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="1c904-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1c904-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
