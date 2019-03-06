---
title: Metodo ICorDebugAssembly::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeadcbd8f2d09320645c36fdc771cfb2cb976036
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471251"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="a0cd1-102">Metodo ICorDebugAssembly::GetProcess</span><span class="sxs-lookup"><span data-stu-id="a0cd1-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="a0cd1-103">Ottiene un puntatore a interfaccia per il processo in cui è in esecuzione questa istanza ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="a0cd1-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0cd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0cd1-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0cd1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0cd1-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="a0cd1-106">[out] Puntatore a interfaccia ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="a0cd1-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0cd1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0cd1-107">Requirements</span></span>  
 <span data-ttu-id="a0cd1-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0cd1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0cd1-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0cd1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0cd1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0cd1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0cd1-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0cd1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
