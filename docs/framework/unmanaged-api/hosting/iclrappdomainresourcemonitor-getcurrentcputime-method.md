---
title: Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8022428c7f803f96e2fa150588edf95542bf19b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985218"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="3d9b6-102">Metodo ICLRAppDomainResourceMonitor::GetCurrentCpuTime</span><span class="sxs-lookup"><span data-stu-id="3d9b6-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="3d9b6-103">Ottiene il tempo processore totale che è stato usato da tutti i thread durante l'esecuzione nel dominio dell'applicazione corrente, poiché è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9b6-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d9b6-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="3d9b6-106">[in] L'ID del dominio dell'applicazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="3d9b6-107">[out] Un puntatore per il tempo processore totale che è stato usato da tutti i thread durante l'esecuzione nel dominio applicazione corrente poiché è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="3d9b6-108">Questo parametro può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d9b6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3d9b6-109">Return Value</span></span>  
  
|<span data-ttu-id="3d9b6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d9b6-110">HRESULT</span></span>|<span data-ttu-id="3d9b6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d9b6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d9b6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d9b6-112">S_OK</span></span>|<span data-ttu-id="3d9b6-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="3d9b6-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="3d9b6-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="3d9b6-115">Il dominio dell'applicazione è stato scaricato o non esiste.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="3d9b6-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d9b6-116">E_FAIL</span></span>|<span data-ttu-id="3d9b6-117">Monitoraggio delle risorse del dominio applicazione non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="3d9b6-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3d9b6-118">-or-</span></span><br /><br /> <span data-ttu-id="3d9b6-119">Tutti gli altri errori.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d9b6-120">Note</span><span class="sxs-lookup"><span data-stu-id="3d9b6-120">Remarks</span></span>  
 <span data-ttu-id="3d9b6-121">Questo metodo è l'equivalente gestito di gestita <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9b6-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d9b6-122">Requirements</span></span>  
 <span data-ttu-id="3d9b6-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d9b6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9b6-124">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3d9b6-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3d9b6-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3d9b6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d9b6-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9b6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9b6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9b6-127">See also</span></span>

- [<span data-ttu-id="3d9b6-128">Interfaccia ICLRAppDomainResourceMonitor</span><span class="sxs-lookup"><span data-stu-id="3d9b6-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="3d9b6-129">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3d9b6-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3d9b6-130">Monitoraggio delle risorse del dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3d9b6-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="3d9b6-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="3d9b6-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
