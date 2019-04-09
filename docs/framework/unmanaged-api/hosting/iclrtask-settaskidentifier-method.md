---
title: Metodo ICLRTask::SetTaskIdentifier
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abd8848ed54b26b66090e4865f9c3a0e5c4d20db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078317"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="8d7a1-102">Metodo ICLRTask::SetTaskIdentifier</span><span class="sxs-lookup"><span data-stu-id="8d7a1-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="8d7a1-103">Indica a common language runtime (CLR) per associare il valore dell'identificatore specificato con l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d7a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d7a1-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d7a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d7a1-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="8d7a1-106">[in] L'identificatore univoco per il common language runtime associare l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d7a1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8d7a1-107">Return Value</span></span>  
  
|<span data-ttu-id="8d7a1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d7a1-108">HRESULT</span></span>|<span data-ttu-id="8d7a1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d7a1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d7a1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d7a1-110">S_OK</span></span>|`SetTaskIdentifier` <span data-ttu-id="8d7a1-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-111">returned successfully.</span></span>|  
|<span data-ttu-id="8d7a1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d7a1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d7a1-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d7a1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d7a1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d7a1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-115">The call timed out.</span></span>|  
|<span data-ttu-id="8d7a1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d7a1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d7a1-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d7a1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d7a1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d7a1-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d7a1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d7a1-120">E_FAIL</span></span>|<span data-ttu-id="8d7a1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d7a1-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d7a1-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d7a1-124">Note</span><span class="sxs-lookup"><span data-stu-id="8d7a1-124">Remarks</span></span>  
 <span data-ttu-id="8d7a1-125">L'host è possibile associare un'attività per semplificare l'integrazione CLR e l'host in un ambiente di debug di un identificatore.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="8d7a1-126">L'identificatore non ha significato per CLR.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="8d7a1-127">Common Language Runtime li passa a un'applicazione del debugger.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="8d7a1-128">Il debugger può usare questo identificatore per associare uno stack di chiamate CLR a uno stack di chiamate di host e abilitare le rispettive informazioni di analisi unificati quando viene visualizzato nell'interfaccia utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="8d7a1-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d7a1-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d7a1-129">Requirements</span></span>  
 <span data-ttu-id="8d7a1-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d7a1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d7a1-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d7a1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d7a1-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8d7a1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8d7a1-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8d7a1-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d7a1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d7a1-134">See also</span></span>

- [<span data-ttu-id="8d7a1-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8d7a1-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8d7a1-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8d7a1-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8d7a1-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8d7a1-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8d7a1-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8d7a1-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
