---
title: Metodo IMetaDataEmit2::GetDeltaSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.GetDeltaSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69897a7b646eb9f58e6b38588e302287b4241779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043680"
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="31939-102">Metodo IMetaDataEmit2::GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="31939-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="31939-103">Ottiene un valore che indica qualsiasi modifica nelle dimensioni dei metadati che risulta dalla sessione corrente di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="31939-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31939-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31939-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31939-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31939-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="31939-106">[in] Uno dei [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) valori, che indica il livello di precisione desiderato.</span><span class="sxs-lookup"><span data-stu-id="31939-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="31939-107">Per .NET Framework versione 2.0, questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="31939-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="31939-108">[out] La variazione delle dimensioni dei metadati.</span><span class="sxs-lookup"><span data-stu-id="31939-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31939-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31939-109">Requirements</span></span>  
 <span data-ttu-id="31939-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31939-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31939-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="31939-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31939-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="31939-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31939-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31939-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31939-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31939-114">See also</span></span>

- [<span data-ttu-id="31939-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="31939-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="31939-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="31939-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
