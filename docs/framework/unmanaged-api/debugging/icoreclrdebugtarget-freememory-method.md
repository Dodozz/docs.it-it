---
title: Metodo ICoreClrDebugTarget::FreeMemory
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b86989c011ddbc403d52cf65a5c0aa371b6b7aa6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658884"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="156f6-102">Metodo ICoreClrDebugTarget::FreeMemory</span><span class="sxs-lookup"><span data-stu-id="156f6-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="156f6-103">Libera la memoria allocata per il [ICoreClrDebugTarget:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) e [ICoreClrDebugTarget:: EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="156f6-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="156f6-104">Syntax</span></span>  
  
```  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="156f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="156f6-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="156f6-106">[in] Un puntatore alla matrice restituita tramite il [ICoreClrDebugTarget:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) o il [ICoreClrDebugTarget:: EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="156f6-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="156f6-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="156f6-107">Requirements</span></span>  
 <span data-ttu-id="156f6-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="156f6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="156f6-109">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="156f6-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="156f6-110">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="156f6-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="156f6-111">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="156f6-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="156f6-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="156f6-112">See also</span></span>
- [<span data-ttu-id="156f6-113">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="156f6-113">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
