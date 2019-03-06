---
title: Metodo IHostPolicyManager::OnFailure
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b049322751c00895ca340c40274088a795f7b51f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471862"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="73975-102">Metodo IHostPolicyManager::OnFailure</span><span class="sxs-lookup"><span data-stu-id="73975-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="73975-103">Notifica all'host che common language runtime (CLR) sta per eseguire l'azione specificata da una chiamata per il [SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) metodo in risposta a un errore di allocazione o recupero di risorse.</span><span class="sxs-lookup"><span data-stu-id="73975-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73975-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73975-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73975-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="73975-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="73975-106">[in] Uno dei [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) valori, che indica il tipo di errore a cui risponde il CLR.</span><span class="sxs-lookup"><span data-stu-id="73975-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="73975-107">[in] Uno dei [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) che indica l'azione CLR richiede i valori, in risposta a `failure`.</span><span class="sxs-lookup"><span data-stu-id="73975-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73975-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="73975-108">Return Value</span></span>  
  
|<span data-ttu-id="73975-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73975-109">HRESULT</span></span>|<span data-ttu-id="73975-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73975-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73975-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73975-111">S_OK</span></span>|<span data-ttu-id="73975-112">`OnFailure` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="73975-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="73975-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73975-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73975-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="73975-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73975-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73975-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73975-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="73975-116">The call timed out.</span></span>|  
|<span data-ttu-id="73975-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73975-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73975-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="73975-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73975-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73975-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73975-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="73975-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73975-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73975-121">E_FAIL</span></span>|<span data-ttu-id="73975-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="73975-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73975-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="73975-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73975-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73975-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73975-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73975-125">Requirements</span></span>  
 <span data-ttu-id="73975-126">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73975-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73975-127">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73975-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73975-128">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="73975-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73975-129">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73975-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73975-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73975-130">See also</span></span>
- [<span data-ttu-id="73975-131">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="73975-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="73975-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="73975-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="73975-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="73975-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="73975-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="73975-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
