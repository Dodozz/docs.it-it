---
title: Metodo IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e89fda72371f197efeeeef8f31ec396c334cfcb2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122031"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="1bfec-102">Metodo IMetaDataAssemblyEmit::DefineExportedType</span><span class="sxs-lookup"><span data-stu-id="1bfec-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="1bfec-103">Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="1bfec-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bfec-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bfec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bfec-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="1bfec-106">[in] Il nome del tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="1bfec-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="1bfec-107">Per la versione 1.1 di common language runtime, il nome del tipo esportato deve corrispondere esattamente al nome fornito nel `TypeDef` per il tipo.</span><span class="sxs-lookup"><span data-stu-id="1bfec-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="1bfec-108">[in] Un token che specifica in cui viene implementato il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="1bfec-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="1bfec-109">I valori validi e i relativi significati associati sono:</span><span class="sxs-lookup"><span data-stu-id="1bfec-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="1bfec-110">`mdFile` Il tipo è implementato in un altro file all'interno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1bfec-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="1bfec-111">`mdAssemblyRef` Il tipo è implementato in un assembly diverso.</span><span class="sxs-lookup"><span data-stu-id="1bfec-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="1bfec-112">`mdExportedTYpe` Il tipo è annidato all'interno di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="1bfec-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="1bfec-113">`mdFileNil` Il tipo è nello stesso file del manifesto e non è un tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="1bfec-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="1bfec-114">[in] Un token per i metadati che specifica il tipo da esportare.</span><span class="sxs-lookup"><span data-stu-id="1bfec-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="1bfec-115">Questo valore viene immesso nel `TypeDef` tabella del file che implementa il tipo e che è pertinente solo se tale file si trova in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="1bfec-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="1bfec-116">[in] Una combinazione bit per bit di [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori di enumerazione che definiscono le impostazioni delle proprietà per il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="1bfec-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="1bfec-117">[out] Puntatore al token di metadati restituito che indica il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="1bfec-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bfec-118">Note</span><span class="sxs-lookup"><span data-stu-id="1bfec-118">Remarks</span></span>  
 <span data-ttu-id="1bfec-119">Un `ExportedType` struttura dei metadati deve essere definito per ogni tipo che viene esposta dall'assembly e che viene implementato in un modulo diverso da quello contenente il manifesto.</span><span class="sxs-lookup"><span data-stu-id="1bfec-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfec-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bfec-120">Requirements</span></span>  
 <span data-ttu-id="1bfec-121">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bfec-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfec-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1bfec-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bfec-123">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1bfec-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1bfec-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bfec-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfec-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bfec-125">See also</span></span>

- [<span data-ttu-id="1bfec-126">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="1bfec-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
