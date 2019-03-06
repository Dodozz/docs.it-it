---
title: Metodo ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364151"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="b0592-102">Metodo ICorDebugEval::CallFunction</span><span class="sxs-lookup"><span data-stu-id="b0592-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="b0592-103">Imposta una chiamata alla funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="b0592-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="b0592-104">Questo metodo è obsoleto in .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="b0592-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b0592-105">Uso [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) invece.</span><span class="sxs-lookup"><span data-stu-id="b0592-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="b0592-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0592-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="b0592-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0592-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="b0592-108">[in] Puntatore a un oggetto ICorDebugFunction che specifica la funzione da chiamare.</span><span class="sxs-lookup"><span data-stu-id="b0592-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="b0592-109">[in] Il numero di argomenti per la funzione.</span><span class="sxs-lookup"><span data-stu-id="b0592-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="b0592-110">[in] Una matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugValue che specifica un argomento deve essere passato alla funzione.</span><span class="sxs-lookup"><span data-stu-id="b0592-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="b0592-111">Note</span><span class="sxs-lookup"><span data-stu-id="b0592-111">Remarks</span></span>

<span data-ttu-id="b0592-112">Se la funzione è virtuale, `CallFunction` eseguirà chiamate virtuali.</span><span class="sxs-lookup"><span data-stu-id="b0592-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="b0592-113">Se la funzione è in un altro dominio applicazione, si verificherà una transizione, purché tutti gli argomenti sono presenti anche in tale dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0592-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="b0592-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0592-114">Requirements</span></span>

<span data-ttu-id="b0592-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0592-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b0592-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0592-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b0592-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0592-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b0592-118">**Versioni di .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b0592-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="b0592-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0592-119">See also</span></span>

- [<span data-ttu-id="b0592-120">Metodo CallParameterizedFunction</span><span class="sxs-lookup"><span data-stu-id="b0592-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)