---
title: Metodo IMetaDataEmit::SaveToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050064"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="486d8-102">Metodo IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="486d8-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="486d8-103">Salva tutti i metadati nell'ambito corrente per l'area specificata di memoria.</span><span class="sxs-lookup"><span data-stu-id="486d8-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="486d8-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="486d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="486d8-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="486d8-106">[out] L'indirizzo in corrispondenza del quale iniziare la scrittura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="486d8-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="486d8-107">[in] Le dimensioni, in byte, della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="486d8-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="486d8-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="486d8-108">Requirements</span></span>  
 <span data-ttu-id="486d8-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="486d8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="486d8-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="486d8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="486d8-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="486d8-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="486d8-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="486d8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486d8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="486d8-113">See also</span></span>

- [<span data-ttu-id="486d8-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="486d8-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="486d8-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="486d8-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
