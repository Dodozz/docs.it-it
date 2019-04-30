---
title: Funzione CompareTo (riferimenti alle API non gestite)
description: La funzione CompareTo Confronta un oggetto in un altro oggetto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb5a26fccf7ceb56089aae4bd4f0732b8a405ba0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049271"
---
# <a name="compareto-function"></a><span data-ttu-id="eff0e-103">Funzione CompareTo</span><span class="sxs-lookup"><span data-stu-id="eff0e-103">CompareTo function</span></span>

<span data-ttu-id="eff0e-104">Confronta un oggetto con un altro oggetto di Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="eff0e-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="eff0e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eff0e-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="eff0e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="eff0e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="eff0e-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="eff0e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="eff0e-108">[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.</span><span class="sxs-lookup"><span data-stu-id="eff0e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="eff0e-109">[in] Combinazione bit per bit di flag che specificano le caratteristiche dell'oggetto da prendere in considerazione per il confronto.</span><span class="sxs-lookup"><span data-stu-id="eff0e-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="eff0e-110">Vedere le [osservazioni](#remarks) sezione per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="eff0e-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="eff0e-111">[in] Oggetto per il confronto.</span><span class="sxs-lookup"><span data-stu-id="eff0e-111">[in] The object for comparison.</span></span> <span data-ttu-id="eff0e-112">`pCompareTo` deve essere un valore valido [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) dell'istanza; non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="eff0e-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="eff0e-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eff0e-113">Return value</span></span>

<span data-ttu-id="eff0e-114">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="eff0e-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eff0e-115">Costante</span><span class="sxs-lookup"><span data-stu-id="eff0e-115">Constant</span></span>  |<span data-ttu-id="eff0e-116">Value</span><span class="sxs-lookup"><span data-stu-id="eff0e-116">Value</span></span>  |<span data-ttu-id="eff0e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eff0e-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="eff0e-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="eff0e-118">0x80041001</span></span> | <span data-ttu-id="eff0e-119">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="eff0e-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eff0e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eff0e-120">0x80041008</span></span> | <span data-ttu-id="eff0e-121">Un parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="eff0e-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="eff0e-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="eff0e-122">0x8004101d</span></span> | <span data-ttu-id="eff0e-123">Una seconda chiamata a `BeginEnumeration` è stata eseguita senza una chiamata corrispondente a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="eff0e-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="eff0e-124">0</span><span class="sxs-lookup"><span data-stu-id="eff0e-124">0</span></span> | <span data-ttu-id="eff0e-125">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="eff0e-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="eff0e-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="eff0e-126">0x40003</span></span> | <span data-ttu-id="eff0e-127">Gli oggetti sono diversi.</span><span class="sxs-lookup"><span data-stu-id="eff0e-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="eff0e-128">0</span><span class="sxs-lookup"><span data-stu-id="eff0e-128">0</span></span> | <span data-ttu-id="eff0e-129">Gli oggetti corrispondono in base ai flag di confronto.</span><span class="sxs-lookup"><span data-stu-id="eff0e-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="eff0e-130">Note</span><span class="sxs-lookup"><span data-stu-id="eff0e-130">Remarks</span></span>

<span data-ttu-id="eff0e-131">Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) (metodo).</span><span class="sxs-lookup"><span data-stu-id="eff0e-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="eff0e-132">I flag che possono essere passati come il `lEnumFlags` definiti nell'argomento di *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice.</span><span class="sxs-lookup"><span data-stu-id="eff0e-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="eff0e-133">È possibile specificare le caratteristiche singole coinvolti nel confronto specificando una combinazione bit per bit dei flag seguenti:</span><span class="sxs-lookup"><span data-stu-id="eff0e-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="eff0e-134">Costante</span><span class="sxs-lookup"><span data-stu-id="eff0e-134">Constant</span></span>  |<span data-ttu-id="eff0e-135">Value</span><span class="sxs-lookup"><span data-stu-id="eff0e-135">Value</span></span>  |<span data-ttu-id="eff0e-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eff0e-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="eff0e-137">2</span><span class="sxs-lookup"><span data-stu-id="eff0e-137">2</span></span> | <span data-ttu-id="eff0e-138">Ignorare l'origine (server e lo spazio dei nomi da cui provengono).</span><span class="sxs-lookup"><span data-stu-id="eff0e-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="eff0e-139">1</span><span class="sxs-lookup"><span data-stu-id="eff0e-139">1</span></span> | <span data-ttu-id="eff0e-140">Ignora tutti i qualificatori (incluso **Key** e **dinamico**)</span><span class="sxs-lookup"><span data-stu-id="eff0e-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="eff0e-141">4</span><span class="sxs-lookup"><span data-stu-id="eff0e-141">4</span></span> | <span data-ttu-id="eff0e-142">Ignora valori predefiniti delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="eff0e-142">Ignore default values of properties.</span></span> <span data-ttu-id="eff0e-143">Questo flag si applica solo al confronto delle classi.</span><span class="sxs-lookup"><span data-stu-id="eff0e-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="eff0e-144">0x20</span><span class="sxs-lookup"><span data-stu-id="eff0e-144">0x20</span></span> | <span data-ttu-id="eff0e-145">Ignora contrassegno qualificatore.</span><span class="sxs-lookup"><span data-stu-id="eff0e-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="eff0e-146">Questo flag ancora qualificatori di prende in considerazione, ma ignora le distinzioni tra le quali le regole di propagazione e ignorare le restrizioni.</span><span class="sxs-lookup"><span data-stu-id="eff0e-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="eff0e-147">0x10</span><span class="sxs-lookup"><span data-stu-id="eff0e-147">0x10</span></span> | <span data-ttu-id="eff0e-148">Ignora maiuscole/minuscole nel confronto dei valori di stringa.</span><span class="sxs-lookup"><span data-stu-id="eff0e-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="eff0e-149">Questo vale sia per le stringhe e valori di qualificatore.</span><span class="sxs-lookup"><span data-stu-id="eff0e-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="eff0e-150">Il confronto dei nomi di proprietà e il qualificatore è sempre tra maiuscole e minuscole indipendentemente dal fatto che questo flag è impostato.</span><span class="sxs-lookup"><span data-stu-id="eff0e-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="eff0e-151">0x8</span><span class="sxs-lookup"><span data-stu-id="eff0e-151">0x8</span></span> | <span data-ttu-id="eff0e-152">Si supponga che gli oggetti da confrontare siano istanze della stessa classe.</span><span class="sxs-lookup"><span data-stu-id="eff0e-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="eff0e-153">Di conseguenza, questo flag vengono confrontate solo informazioni relativa all'istanza.</span><span class="sxs-lookup"><span data-stu-id="eff0e-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="eff0e-154">Usare questo flag per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="eff0e-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="eff0e-155">Se gli oggetti non sono della stessa classe, i risultati sono indefiniti.</span><span class="sxs-lookup"><span data-stu-id="eff0e-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="eff0e-156">In alternativa, è possibile specificare un singolo flag composito, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eff0e-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="eff0e-157">Costante</span><span class="sxs-lookup"><span data-stu-id="eff0e-157">Constant</span></span>  |<span data-ttu-id="eff0e-158">Value</span><span class="sxs-lookup"><span data-stu-id="eff0e-158">Value</span></span>  |<span data-ttu-id="eff0e-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eff0e-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="eff0e-160">0</span><span class="sxs-lookup"><span data-stu-id="eff0e-160">0</span></span> | <span data-ttu-id="eff0e-161">Prendere in considerazione tutte le funzionalità nel confronto.</span><span class="sxs-lookup"><span data-stu-id="eff0e-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="eff0e-162">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eff0e-162">Requirements</span></span>

<span data-ttu-id="eff0e-163">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eff0e-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="eff0e-164">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eff0e-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="eff0e-165">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eff0e-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eff0e-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eff0e-166">See also</span></span>

- [<span data-ttu-id="eff0e-167">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="eff0e-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)