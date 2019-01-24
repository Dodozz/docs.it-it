---
title: Metodo ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5095dc04b118e782b00bb385427ad23a2786343c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740164"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="421b9-102">Metodo ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="421b9-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="421b9-103">Fornisce un'enumerazione di ordinato [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture che forniscono le informazioni di blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="421b9-103">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="421b9-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a><span data-ttu-id="421b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="421b9-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="421b9-106">[out] Un puntatore a un'enumerazione di ordinato [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.</span><span class="sxs-lookup"><span data-stu-id="421b9-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="421b9-107">Note</span><span class="sxs-lookup"><span data-stu-id="421b9-107">Remarks</span></span>  
 <span data-ttu-id="421b9-108">Il primo elemento nell'enumerazione restituita corrisponde alla struttura prima che sta bloccando il thread.</span><span class="sxs-lookup"><span data-stu-id="421b9-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="421b9-109">Il secondo elemento corrisponde a un elemento di blocco che viene rilevato durante l'esecuzione di una chiamata di procedura asincrono (APC) quando è bloccata in corrispondenza del primo e così via.</span><span class="sxs-lookup"><span data-stu-id="421b9-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="421b9-110">L'enumerazione è valida solo per la durata dello stato di sincronizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="421b9-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="421b9-111">Questo metodo deve essere chiamato mentre l'oggetto del debug è in uno stato sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="421b9-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="421b9-112">Se `ppBlockingObjectEnum` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="421b9-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="421b9-113">Se un thread è bloccato e non può essere determinato l'errore, il metodo restituisce un HRESULT che indica un errore. in caso contrario, viene restituito S_OK.</span><span class="sxs-lookup"><span data-stu-id="421b9-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421b9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="421b9-114">Requirements</span></span>  
 <span data-ttu-id="421b9-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421b9-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="421b9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="421b9-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421b9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421b9-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421b9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="421b9-119">See also</span></span>
- [<span data-ttu-id="421b9-120">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="421b9-120">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="421b9-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="421b9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="421b9-122">Debug</span><span class="sxs-lookup"><span data-stu-id="421b9-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
