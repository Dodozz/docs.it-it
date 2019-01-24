---
title: Funzione GetQualifierSet (riferimenti alle API non gestite)
description: La funzione GetQualifierSet recupera il qualificatore impostata per una classe o istanza.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b35a901586a4e0951b9915330f974dc48e931c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632179"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="afd42-103">GetQualifierSet (funzione)</span><span class="sxs-lookup"><span data-stu-id="afd42-103">GetQualifierSet function</span></span>
<span data-ttu-id="afd42-104">Recupera il qualificatore impostato per l'istanza di una classe o la definizione di una classe.</span><span class="sxs-lookup"><span data-stu-id="afd42-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="afd42-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afd42-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="afd42-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="afd42-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="afd42-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="afd42-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="afd42-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="afd42-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="afd42-109">[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori dell'oggetto di classe.</span><span class="sxs-lookup"><span data-stu-id="afd42-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="afd42-110">Il parametro `ppQualSet` non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="afd42-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="afd42-111">Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore viene lasciato invariato.</span><span class="sxs-lookup"><span data-stu-id="afd42-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="afd42-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="afd42-112">Return value</span></span>

<span data-ttu-id="afd42-113">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="afd42-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="afd42-114">Costante</span><span class="sxs-lookup"><span data-stu-id="afd42-114">Constant</span></span>  |<span data-ttu-id="afd42-115">Valore</span><span class="sxs-lookup"><span data-stu-id="afd42-115">Value</span></span>  |<span data-ttu-id="afd42-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afd42-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="afd42-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="afd42-117">0x80041001</span></span> | <span data-ttu-id="afd42-118">Si è verificato un errore generale.</span><span class="sxs-lookup"><span data-stu-id="afd42-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="afd42-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="afd42-119">0x80041002</span></span> | <span data-ttu-id="afd42-120">Il metodo specificato non esiste.</span><span class="sxs-lookup"><span data-stu-id="afd42-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="afd42-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="afd42-121">0x80041006</span></span> | <span data-ttu-id="afd42-122">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="afd42-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="afd42-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="afd42-123">0x80041008</span></span> | <span data-ttu-id="afd42-124">È un parametro `null`.</span><span class="sxs-lookup"><span data-stu-id="afd42-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="afd42-125">0</span><span class="sxs-lookup"><span data-stu-id="afd42-125">0</span></span> | <span data-ttu-id="afd42-126">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="afd42-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="afd42-127">Note</span><span class="sxs-lookup"><span data-stu-id="afd42-127">Remarks</span></span>

<span data-ttu-id="afd42-128">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) (metodo).</span><span class="sxs-lookup"><span data-stu-id="afd42-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="afd42-129">Il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.</span><span class="sxs-lookup"><span data-stu-id="afd42-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="afd42-130">Tali qualificatori aggiunti, modificati o eliminati vengono applicati per l'intera definizione di classe o istanza.</span><span class="sxs-lookup"><span data-stu-id="afd42-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="afd42-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="afd42-131">Requirements</span></span>  
<span data-ttu-id="afd42-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afd42-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afd42-133">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="afd42-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="afd42-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="afd42-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd42-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afd42-135">See also</span></span>
- [<span data-ttu-id="afd42-136">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="afd42-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
