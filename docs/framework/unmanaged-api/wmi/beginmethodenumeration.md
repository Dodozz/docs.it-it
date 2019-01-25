---
title: Funzione BeginMethodEnumeration (riferimenti alle API non gestite)
description: La funzione BeginMethodEnumeration avvia un'enumerazione dei metodi dell'oggetto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b682904a8e7f2eafa8833d784febe7b3b2a1e5f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611085"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="564e8-103">BeginEnumeration (funzione)</span><span class="sxs-lookup"><span data-stu-id="564e8-103">BeginEnumeration function</span></span>
<span data-ttu-id="564e8-104">Avvia un'enumerazione dei metodi disponibili per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="564e8-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="564e8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="564e8-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="564e8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="564e8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="564e8-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="564e8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="564e8-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="564e8-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="564e8-109">[in] Zero (0) per tutti i metodi, o un flag che specifica l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="564e8-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="564e8-110">I flag seguenti sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="564e8-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="564e8-111">Costante</span><span class="sxs-lookup"><span data-stu-id="564e8-111">Constant</span></span>  |<span data-ttu-id="564e8-112">Valore</span><span class="sxs-lookup"><span data-stu-id="564e8-112">Value</span></span>  |<span data-ttu-id="564e8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="564e8-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="564e8-114">0x10</span><span class="sxs-lookup"><span data-stu-id="564e8-114">0x10</span></span> | <span data-ttu-id="564e8-115">Limitare l'enumerazione per i metodi definiti nella classe stessa.</span><span class="sxs-lookup"><span data-stu-id="564e8-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="564e8-116">0x20</span><span class="sxs-lookup"><span data-stu-id="564e8-116">0x20</span></span> | <span data-ttu-id="564e8-117">Limitare l'enumerazione delle proprietà ereditate dalle classi di base.</span><span class="sxs-lookup"><span data-stu-id="564e8-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="564e8-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="564e8-118">Return value</span></span>

<span data-ttu-id="564e8-119">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="564e8-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="564e8-120">Costante</span><span class="sxs-lookup"><span data-stu-id="564e8-120">Constant</span></span>  |<span data-ttu-id="564e8-121">Value</span><span class="sxs-lookup"><span data-stu-id="564e8-121">Value</span></span>  |<span data-ttu-id="564e8-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="564e8-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="564e8-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="564e8-123">0x80041008</span></span> | <span data-ttu-id="564e8-124">`lEnnumFlags` è diverso da zero e non è uno dei flag specificati.</span><span class="sxs-lookup"><span data-stu-id="564e8-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="564e8-125">0</span><span class="sxs-lookup"><span data-stu-id="564e8-125">0</span></span> | <span data-ttu-id="564e8-126">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="564e8-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="564e8-127">Note</span><span class="sxs-lookup"><span data-stu-id="564e8-127">Remarks</span></span>

<span data-ttu-id="564e8-128">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) (metodo).</span><span class="sxs-lookup"><span data-stu-id="564e8-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="564e8-129">Questa chiamata al metodo è supportata solo se l'oggetto corrente è una definizione di classe.</span><span class="sxs-lookup"><span data-stu-id="564e8-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="564e8-130">Manipolazione di metodo non è disponibile dal [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntatori che puntano a istanze.</span><span class="sxs-lookup"><span data-stu-id="564e8-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="564e8-131">L'ordine in cui vengono enumerati i metodi è garantito a essere invariante per una determinata istanza del [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="564e8-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="564e8-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="564e8-132">Requirements</span></span>  
 <span data-ttu-id="564e8-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="564e8-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="564e8-134">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="564e8-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="564e8-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="564e8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564e8-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="564e8-136">See also</span></span>
- [<span data-ttu-id="564e8-137">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="564e8-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
