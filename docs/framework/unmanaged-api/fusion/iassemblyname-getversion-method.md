---
title: Metodo IAssemblyName::GetVersion
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a28cb9f1fd2e12cd750d4eeb8db6c2d7a181b414
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197425"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="2ad16-102">Metodo IAssemblyName::GetVersion</span><span class="sxs-lookup"><span data-stu-id="2ad16-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="2ad16-103">Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="2ad16-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ad16-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ad16-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ad16-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="2ad16-106">[out] 32 bit alti della versione.</span><span class="sxs-lookup"><span data-stu-id="2ad16-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="2ad16-107">[out] 32 bit bassi della versione.</span><span class="sxs-lookup"><span data-stu-id="2ad16-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad16-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ad16-108">Requirements</span></span>  
 <span data-ttu-id="2ad16-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad16-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad16-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2ad16-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="2ad16-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ad16-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ad16-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ad16-112">See also</span></span>

- [<span data-ttu-id="2ad16-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="2ad16-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
