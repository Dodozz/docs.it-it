---
title: Metodo ICorDebugController::Detach
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151801"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="93533-102">Metodo ICorDebugController::Detach</span><span class="sxs-lookup"><span data-stu-id="93533-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="93533-103">Scollega debugger dal dominio dell'applicazione o processo.</span><span class="sxs-lookup"><span data-stu-id="93533-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93533-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93533-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="93533-105">Note</span><span class="sxs-lookup"><span data-stu-id="93533-105">Remarks</span></span>  
 <span data-ttu-id="93533-106">Il processo o dominio applicazione continua l'esecuzione in genere, ma l'oggetto "ICorDebugProcess" o "ICorDebugAppDomain" non è più valido e si verificherà alcun callback ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="93533-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="93533-107">In .NET Framework versione 2.0, se il debug non gestito è abilitato, questo metodo avrà esito negativo a causa di limitazioni del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="93533-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93533-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93533-108">Requirements</span></span>  
 <span data-ttu-id="93533-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93533-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93533-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93533-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93533-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93533-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93533-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93533-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93533-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93533-113">See also</span></span>
