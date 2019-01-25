---
title: Metodo IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ca43ebc257ee4eb9d0ef17f3399e87c03b9f9c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740008"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="b597f-102">Metodo IMetaDataImport::GetMethodProps</span><span class="sxs-lookup"><span data-stu-id="b597f-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="b597f-103">Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="b597f-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b597f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b597f-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b597f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b597f-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b597f-106">[in] Il token MethodDef che rappresenta il metodo per restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="b597f-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="b597f-107">[out] Un puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="b597f-108">[out] Un puntatore a un buffer che contiene il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="b597f-109">[in] La dimensione richiesta del `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="b597f-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="b597f-110">[out] Un puntatore alla dimensione in caratteri wide di `szMethod`, o in caso di troncamento, il numero effettivo di caratteri "wide" nel nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="b597f-111">[out] Puntatore a nessun flag associato al metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="b597f-112">[out] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="b597f-113">[out] Un puntatore alla dimensione in byte del `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b597f-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="b597f-114">[out] Un puntatore all'indirizzo virtuale relativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="b597f-115">[out] Puntatore ai flag di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b597f-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b597f-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b597f-116">Requirements</span></span>  
 <span data-ttu-id="b597f-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b597f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b597f-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b597f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b597f-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b597f-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b597f-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b597f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b597f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b597f-121">See also</span></span>
- [<span data-ttu-id="b597f-122">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b597f-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b597f-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b597f-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
