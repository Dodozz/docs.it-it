---
title: Metodo IHostThreadPoolManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 905ce9183d295568977eb7e216e5327d6b4ee8bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636092"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="81d9e-102">Metodo IHostThreadPoolManager::SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="81d9e-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="81d9e-103">Imposta il numero massimo di thread che l'host può mantenere nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="81d9e-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81d9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81d9e-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81d9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="81d9e-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="81d9e-106">Numero massimo di thread di lavoro nel pool di thread.</span><span class="sxs-lookup"><span data-stu-id="81d9e-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81d9e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="81d9e-107">Return Value</span></span>  
  
|<span data-ttu-id="81d9e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81d9e-108">HRESULT</span></span>|<span data-ttu-id="81d9e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81d9e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81d9e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="81d9e-110">S_OK</span></span>|<span data-ttu-id="81d9e-111">`SetMaxThreads` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="81d9e-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="81d9e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81d9e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81d9e-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="81d9e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81d9e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81d9e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81d9e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="81d9e-115">The call timed out.</span></span>|  
|<span data-ttu-id="81d9e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81d9e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81d9e-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="81d9e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81d9e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81d9e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81d9e-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="81d9e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81d9e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81d9e-120">E_FAIL</span></span>|<span data-ttu-id="81d9e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="81d9e-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="81d9e-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="81d9e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81d9e-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81d9e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81d9e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="81d9e-124">E_NOTIMPL</span></span>|<span data-ttu-id="81d9e-125">L'host non fornisce un'implementazione di `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="81d9e-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81d9e-126">Note</span><span class="sxs-lookup"><span data-stu-id="81d9e-126">Remarks</span></span>  
 <span data-ttu-id="81d9e-127">Un host non è necessario per consentire a configurare le dimensioni del pool di thread CLR.</span><span class="sxs-lookup"><span data-stu-id="81d9e-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="81d9e-128">Alcuni host potrebbe essere necessario un controllo esclusivo sul pool di thread, per motivi, ad esempio la scalabilità, prestazioni o implementazione.</span><span class="sxs-lookup"><span data-stu-id="81d9e-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="81d9e-129">In questo caso, un host deve restituire un valore HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="81d9e-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81d9e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81d9e-130">Requirements</span></span>  
 <span data-ttu-id="81d9e-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81d9e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81d9e-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81d9e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81d9e-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="81d9e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81d9e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81d9e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d9e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81d9e-135">See also</span></span>
- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="81d9e-136">Metodo GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="81d9e-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="81d9e-137">Metodo SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="81d9e-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="81d9e-138">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="81d9e-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
