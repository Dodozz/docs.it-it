---
title: Funzione BlessIWbemServicesObject (riferimenti alle API non gestite)
description: La funzione BlessIWbemServicesObject indica se le credenziali utente consentono l'accesso a un oggetto IWbemServices
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eb6b870beabb71e340b0ec39c489cedb02128cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749579"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="4a7fe-103">Funzione BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="4a7fe-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="4a7fe-104">Indica se le credenziali utente di consentono l'accesso a un oggetto specificato [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) oggetto.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4a7fe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a7fe-105">Syntax</span></span>

```
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="4a7fe-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a7fe-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="4a7fe-107">[in] Un puntatore a un oggetto servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="4a7fe-108">[in] Il nome utente.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="4a7fe-109">[in] La password associata `strUser`.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="4a7fe-110">[in] Il nome di dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-110">[in] The domain name of the user.</span></span> <span data-ttu-id="4a7fe-111">Vedere le [ConnectServerWmi](connectserverwmi.md) (funzione) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="4a7fe-112">[in] Il livello di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="4a7fe-113">[in] Il livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="4a7fe-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a7fe-114">Return value</span></span>

<span data-ttu-id="4a7fe-115">I seguenti valori restituiti da questa funzione sono definiti nel *Winerror* file di intestazione, oppure è possibile definirle come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="4a7fe-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4a7fe-116">Costante</span><span class="sxs-lookup"><span data-stu-id="4a7fe-116">Constant</span></span>  |<span data-ttu-id="4a7fe-117">Value</span><span class="sxs-lookup"><span data-stu-id="4a7fe-117">Value</span></span>  |<span data-ttu-id="4a7fe-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a7fe-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="4a7fe-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="4a7fe-119">0x80070057</span></span> | <span data-ttu-id="4a7fe-120">Uno o più argomenti non sono validi.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="4a7fe-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="4a7fe-121">0x80004003</span></span> | <span data-ttu-id="4a7fe-122">`pIWbemServices` è `null`.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="4a7fe-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="4a7fe-123">0x80000008</span></span> | <span data-ttu-id="4a7fe-124">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="4a7fe-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="4a7fe-125">0x80000002</span></span> | <span data-ttu-id="4a7fe-126">Memoria disponibile è insufficiente per eseguire l'operazione.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="4a7fe-127">0</span><span class="sxs-lookup"><span data-stu-id="4a7fe-127">0</span></span> | <span data-ttu-id="4a7fe-128">La chiamata di funzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4a7fe-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="4a7fe-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a7fe-129">Requirements</span></span>

 <span data-ttu-id="4a7fe-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a7fe-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4a7fe-131">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4a7fe-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="4a7fe-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a7fe-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4a7fe-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a7fe-133">See also</span></span>

- [<span data-ttu-id="4a7fe-134">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="4a7fe-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)