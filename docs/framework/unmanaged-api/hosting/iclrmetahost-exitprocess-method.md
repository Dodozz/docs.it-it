---
title: Metodo ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf3c00eafe47556c6b46e1acb687a19df5a2b28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601756"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="a0476-102">Metodo ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="a0476-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="a0476-103">Tenta di arresto normale runtime caricati tutti e quindi termina il processo.</span><span class="sxs-lookup"><span data-stu-id="a0476-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="a0476-104">Sostituisce il [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="a0476-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0476-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0476-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0476-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0476-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="a0476-107">[in] Il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="a0476-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0476-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a0476-108">Return Value</span></span>  
 <span data-ttu-id="a0476-109">Questo metodo non restituisce mai, pertanto il relativo valore restituito è indefinito.</span><span class="sxs-lookup"><span data-stu-id="a0476-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0476-110">Note</span><span class="sxs-lookup"><span data-stu-id="a0476-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0476-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0476-111">Requirements</span></span>  
 <span data-ttu-id="a0476-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0476-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0476-113">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a0476-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a0476-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a0476-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0476-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0476-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0476-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0476-116">See also</span></span>
- [<span data-ttu-id="a0476-117">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="a0476-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="a0476-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="a0476-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
