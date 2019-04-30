---
title: Metodo ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3948e45b991e667ea90c7846ee0d6fd630c0db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986586"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="532b6-102">Metodo ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="532b6-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="532b6-103">Ottiene l'identificatore del sistema operativo per questo processo.</span><span class="sxs-lookup"><span data-stu-id="532b6-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="532b6-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="532b6-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="532b6-106">[out] Un puntatore all'identificatore del processo rappresentato da questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="532b6-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="532b6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="532b6-107">Requirements</span></span>  
 <span data-ttu-id="532b6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="532b6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532b6-109">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="532b6-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="532b6-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="532b6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="532b6-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532b6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532b6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="532b6-112">See also</span></span>

- [<span data-ttu-id="532b6-113">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="532b6-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
