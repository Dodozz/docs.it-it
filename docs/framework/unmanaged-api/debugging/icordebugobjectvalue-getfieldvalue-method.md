---
title: Metodo ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8778edf9ac6e32d5dab3a53a6d9cc643a8df13b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107913"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="55eb0-102">Metodo ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="55eb0-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="55eb0-103">Ottiene il valore del campo specificato della classe specificata per il valore dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="55eb0-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55eb0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55eb0-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55eb0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55eb0-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="55eb0-106">[in] Un puntatore a un oggetto "ICorDebugClass" che rappresenta la classe per cui ottenere il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="55eb0-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="55eb0-107">[in] Un `mdFieldDef` token che fa riferimento a metadati che descrivono il campo.</span><span class="sxs-lookup"><span data-stu-id="55eb0-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="55eb0-108">[out] Un puntatore a un oggetto "ICorDebugValue" che rappresenta il valore del campo specificato.</span><span class="sxs-lookup"><span data-stu-id="55eb0-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55eb0-109">Note</span><span class="sxs-lookup"><span data-stu-id="55eb0-109">Remarks</span></span>  
 <span data-ttu-id="55eb0-110">La classe, specificata nella `pClass` parametro deve essere nella gerarchia della classe del valore dell'oggetto e il campo deve essere un campo di tale classe.</span><span class="sxs-lookup"><span data-stu-id="55eb0-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="55eb0-111">Il `GetFieldValue` metodo avrà comunque esito positivo per oggetti generici e le classi generiche.</span><span class="sxs-lookup"><span data-stu-id="55eb0-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="55eb0-112">Ad esempio, se MyDictionary\<V > eredita dal dizionario\<stringa, V >, e il valore dell'oggetto è di tipo MyDictionary\<int32 >, passando il `ICorDebugClass` oggetto per il dizionario\<K, V > verrà ottenere correttamente un campo del dizionario\<string, int32 >.</span><span class="sxs-lookup"><span data-stu-id="55eb0-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55eb0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55eb0-113">Requirements</span></span>  
 <span data-ttu-id="55eb0-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55eb0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55eb0-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55eb0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55eb0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55eb0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55eb0-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55eb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55eb0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55eb0-118">See also</span></span>
