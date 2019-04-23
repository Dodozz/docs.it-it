---
title: Metodo ITypeName::GetTypeArguments
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cd4fa8f4ba2bea5a2a853544eae6239bfaaeba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132275"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="16e68-102">Metodo ITypeName::GetTypeArguments</span><span class="sxs-lookup"><span data-stu-id="16e68-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="16e68-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="16e68-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16e68-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="16e68-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16e68-105">Requirements</span></span>  
 <span data-ttu-id="16e68-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16e68-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e68-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16e68-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16e68-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="16e68-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16e68-109">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e68-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e68-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16e68-110">See also</span></span>

- [<span data-ttu-id="16e68-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="16e68-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
