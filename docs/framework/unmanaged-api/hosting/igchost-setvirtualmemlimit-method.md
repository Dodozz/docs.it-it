---
title: Metodo IGCHost::SetVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5b4210bda7d41b190f1025b62132c5df896a2a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703621"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="83c51-102">Metodo IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="83c51-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="83c51-103">Imposta la dimensione massima di memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="83c51-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83c51-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c51-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83c51-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="83c51-106">[in] Le dimensioni massime, in megabyte, della memoria virtuale del runtime.</span><span class="sxs-lookup"><span data-stu-id="83c51-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83c51-107">Note</span><span class="sxs-lookup"><span data-stu-id="83c51-107">Remarks</span></span>  
 <span data-ttu-id="83c51-108">La dimensione massima di memoria virtuale del runtime può essere modificata in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="83c51-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c51-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83c51-109">Requirements</span></span>  
 <span data-ttu-id="83c51-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c51-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c51-111">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="83c51-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="83c51-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83c51-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83c51-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c51-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c51-114">See also</span></span>

- [<span data-ttu-id="83c51-115">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="83c51-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
