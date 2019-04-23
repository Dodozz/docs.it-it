---
title: Metodo IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48055103b49b4c61bb7561f2d4aa6c8daae07ae2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128908"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="85848-102">Metodo IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="85848-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="85848-103">Crea una definizione per un evento con la firma dei metadati specificati e ottiene un token di definizione di tale evento.</span><span class="sxs-lookup"><span data-stu-id="85848-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85848-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85848-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85848-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85848-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="85848-106">[in] Il token per la classe di destinazione o l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="85848-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="85848-107">Questo è un `mdTypeDef` o `mdTypeDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="85848-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="85848-108">[in] Il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="85848-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="85848-109">[in] Flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="85848-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="85848-110">[in] Il token per la classe di evento.</span><span class="sxs-lookup"><span data-stu-id="85848-110">[in] The token for the event class.</span></span> <span data-ttu-id="85848-111">Si tratta di un `mdTypeDef`, una `mdTypeRef`, o un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="85848-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="85848-112">[in] Il metodo utilizzato per sottoscrivere l'evento, o null.</span><span class="sxs-lookup"><span data-stu-id="85848-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="85848-113">[in] Il metodo utilizzato per annullare la sottoscrizione per l'evento, o null.</span><span class="sxs-lookup"><span data-stu-id="85848-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="85848-114">[in] Il metodo utilizzato (da una classe derivata) per generare l'evento.</span><span class="sxs-lookup"><span data-stu-id="85848-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="85848-115">[in] Matrice dei token per gli altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="85848-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="85848-116">La matrice viene terminata con un `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="85848-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="85848-117">[out] Il token di metadati assegnato all'evento.</span><span class="sxs-lookup"><span data-stu-id="85848-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85848-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85848-118">Requirements</span></span>  
 <span data-ttu-id="85848-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85848-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85848-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="85848-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85848-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="85848-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85848-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85848-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85848-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85848-123">See also</span></span>

- [<span data-ttu-id="85848-124">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="85848-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="85848-125">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="85848-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
