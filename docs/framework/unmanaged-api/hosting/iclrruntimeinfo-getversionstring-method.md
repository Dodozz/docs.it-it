---
title: Metodo ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbfa25300cbed83d36cc43d9a0dd0beb2520dea1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475290"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="7f29d-102">Metodo ICLRRuntimeInfo::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="7f29d-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="7f29d-103">Ottiene common language runtime (CLR) informazioni sulla versione associati con un determinato [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7f29d-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="7f29d-104">Questo metodo sostituisce le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f29d-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="7f29d-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7f29d-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [<span data-ttu-id="7f29d-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="7f29d-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="7f29d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f29d-107">Syntax</span></span>  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f29d-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f29d-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="7f29d-109">[out] La versione di compilazione di .NET Framework nel formato "v*un'*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="7f29d-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="7f29d-110">*Oggetto*, *B*, e *X* sono numeri decimali che corrispondono alla versione principale, la versione secondaria e il numero di build.</span><span class="sxs-lookup"><span data-stu-id="7f29d-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="7f29d-111">*X* è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7f29d-111">*X* is optional.</span></span> <span data-ttu-id="7f29d-112">Se *X* è non è presente, non è previsto alcun periodo finale.</span><span class="sxs-lookup"><span data-stu-id="7f29d-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f29d-113">Questo parametro deve corrispondere al nome di directory per la versione di .NET Framework, così come appare sotto C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="7f29d-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="7f29d-114">I valori di esempio sono "v1.0.3705", "v1.1.4322", "v2.0.50727" e "v4.0. *x*", dove *x* dipende dal numero di build installato.</span><span class="sxs-lookup"><span data-stu-id="7f29d-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="7f29d-115">Si noti che il prefisso "v" è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f29d-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="7f29d-116">[in, out] Specifica la dimensione del `pwzBuffer` per evitare i sovraccarichi del buffer.</span><span class="sxs-lookup"><span data-stu-id="7f29d-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="7f29d-117">Se `pwzBuffer` viene `null`, `pchBuffer` restituisce la dimensione necessaria della `pwzBuffer` per consentire la preallocazione.</span><span class="sxs-lookup"><span data-stu-id="7f29d-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f29d-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7f29d-118">Return Value</span></span>  
 <span data-ttu-id="7f29d-119">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="7f29d-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7f29d-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f29d-120">HRESULT</span></span>|<span data-ttu-id="7f29d-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f29d-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f29d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f29d-122">S_OK</span></span>|<span data-ttu-id="7f29d-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f29d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="7f29d-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7f29d-124">E_POINTER</span></span>|<span data-ttu-id="7f29d-125">`pwzBuffer` o `pchBuffer` è null.</span><span class="sxs-lookup"><span data-stu-id="7f29d-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f29d-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f29d-126">Requirements</span></span>  
 <span data-ttu-id="7f29d-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f29d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f29d-128">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7f29d-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7f29d-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7f29d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f29d-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f29d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f29d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f29d-131">See also</span></span>
- [<span data-ttu-id="7f29d-132">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7f29d-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7f29d-133">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7f29d-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7f29d-134">Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5</span><span class="sxs-lookup"><span data-stu-id="7f29d-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="7f29d-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="7f29d-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
