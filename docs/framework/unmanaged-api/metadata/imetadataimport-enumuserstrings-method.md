---
title: Metodo IMetaDataImport::EnumUserStrings
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79e65d86eda2f01e1d6f2af46c5ee8e15ff03ccb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730243"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="3ecc0-102">Metodo IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="3ecc0-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="3ecc0-103">Enumera i token String che rappresentano le stringhe specificate a livello di codice (hard-coded) nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ecc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ecc0-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ecc0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ecc0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3ecc0-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3ecc0-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="3ecc0-108">[out] Matrice utilizzata per archiviare i token di stringa.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3ecc0-109">[in] Dimensione massima della matrice `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="3ecc0-110">[out] Il numero di token di stringa restituiti in `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ecc0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3ecc0-111">Return Value</span></span>  
  
|<span data-ttu-id="3ecc0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ecc0-112">HRESULT</span></span>|<span data-ttu-id="3ecc0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ecc0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3ecc0-114">`EnumUserStrings` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3ecc0-115">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3ecc0-116">In tal caso, `pcStrings` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ecc0-117">Note</span><span class="sxs-lookup"><span data-stu-id="3ecc0-117">Remarks</span></span>  
 <span data-ttu-id="3ecc0-118">I token di stringa creati tramite il [DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3ecc0-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="3ecc0-119">Questo metodo è progettato per essere utilizzato da un browser di metadati anziché da un compilatore.</span><span class="sxs-lookup"><span data-stu-id="3ecc0-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ecc0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ecc0-120">Requirements</span></span>  
 <span data-ttu-id="3ecc0-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ecc0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ecc0-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3ecc0-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ecc0-123">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3ecc0-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ecc0-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ecc0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecc0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ecc0-125">See also</span></span>
- [<span data-ttu-id="3ecc0-126">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3ecc0-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3ecc0-127">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3ecc0-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
