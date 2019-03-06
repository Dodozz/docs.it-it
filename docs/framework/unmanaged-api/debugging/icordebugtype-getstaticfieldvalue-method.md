---
title: Metodo ICorDebugType::GetStaticFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c6b86c5ce3cc246af600d9b65d2fe12a0427f9f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485395"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="894b2-102">Metodo ICorDebugType::GetStaticFieldValue</span><span class="sxs-lookup"><span data-stu-id="894b2-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="894b2-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token lo stack frame specificato.</span><span class="sxs-lookup"><span data-stu-id="894b2-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="894b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="894b2-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="894b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="894b2-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="894b2-106">[in] Un `mdFieldDef` token che specifica il campo statico.</span><span class="sxs-lookup"><span data-stu-id="894b2-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="894b2-107">[in] Un puntatore a un'interfaccia ICorDebugFrame che rappresenta il frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="894b2-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="894b2-108">[out] Un puntatore all'indirizzo di un `ICorDebugValue` che contiene il valore del campo statico.</span><span class="sxs-lookup"><span data-stu-id="894b2-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="894b2-109">Note</span><span class="sxs-lookup"><span data-stu-id="894b2-109">Remarks</span></span>  
 <span data-ttu-id="894b2-110">Il `GetStaticFieldValue` metodo può essere usato solo se il tipo è ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, come indicato dal [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="894b2-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="894b2-111">Per i tipi non generici, l'operazione eseguita da `GetStaticFieldValue` è identica alla chiamata [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) sull'oggetto restituito da ICorDebugClass [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="894b2-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="894b2-112">Per i tipi generici, un valore del campo statico è relativo alla creazione di un'istanza particolare.</span><span class="sxs-lookup"><span data-stu-id="894b2-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="894b2-113">Inoltre, se il campo statico può essere relativo a un thread, un contesto o un dominio dell'applicazione, quindi lo stack frame per il debugger di determinare il valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="894b2-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="894b2-114">Note</span><span class="sxs-lookup"><span data-stu-id="894b2-114">Remarks</span></span>  
 <span data-ttu-id="894b2-115">`GetStaticFieldValue` può essere utilizzato solo quando una chiamata a `ICorDebugType::GetType` restituisce un valore di ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="894b2-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="894b2-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="894b2-116">Requirements</span></span>  
 <span data-ttu-id="894b2-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="894b2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="894b2-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="894b2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="894b2-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="894b2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="894b2-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="894b2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
