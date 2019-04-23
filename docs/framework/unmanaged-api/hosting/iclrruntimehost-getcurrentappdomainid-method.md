---
title: Metodo ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096212"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="b13f1-102">Metodo ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="b13f1-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="b13f1-103">Ottiene l'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b13f1-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b13f1-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b13f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b13f1-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="b13f1-106">[out] L'identificatore numerico del <xref:System.AppDomain> che è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b13f1-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b13f1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b13f1-107">Return Value</span></span>  
  
|<span data-ttu-id="b13f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b13f1-108">HRESULT</span></span>|<span data-ttu-id="b13f1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b13f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b13f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b13f1-110">S_OK</span></span>|<span data-ttu-id="b13f1-111">`GetCurrentAppDomainId` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b13f1-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="b13f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b13f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b13f1-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13f1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b13f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b13f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b13f1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b13f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="b13f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b13f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b13f1-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b13f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b13f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b13f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b13f1-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b13f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b13f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b13f1-120">E_FAIL</span></span>|<span data-ttu-id="b13f1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b13f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b13f1-122">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b13f1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b13f1-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b13f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b13f1-124">Note</span><span class="sxs-lookup"><span data-stu-id="b13f1-124">Remarks</span></span>  
 <span data-ttu-id="b13f1-125">Il `pdwAppDomainId` parametro è impostato sul valore della <xref:System.AppDomain.Id%2A> proprietà del <xref:System.AppDomain> in cui è in esecuzione il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="b13f1-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13f1-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b13f1-126">Requirements</span></span>  
 <span data-ttu-id="b13f1-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b13f1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b13f1-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b13f1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b13f1-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b13f1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b13f1-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b13f1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13f1-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b13f1-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="b13f1-132">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b13f1-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
