---
title: Metodo IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c9debf041a26af128dea3cde214630f5a95eac71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992537"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="23b67-102">Metodo IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="23b67-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="23b67-103">Crea un riferimento al tipo specificato che viene definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="23b67-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23b67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23b67-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23b67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23b67-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="23b67-106">[in] Un' [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="23b67-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="23b67-107">[in] Matrice che contiene il valore hash per l'assembly specificato da `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="23b67-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="23b67-108">[in] Numero di byte nella matrice di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="23b67-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="23b67-109">[in] Un' [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="23b67-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="23b67-110">[in] Un `mdTypeDef` token che specifica il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="23b67-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="23b67-111">[in] Un' [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="23b67-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="23b67-112">[out] Il `mdTypeRef` token definito nell'ambito corrente per il riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="23b67-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23b67-113">Note</span><span class="sxs-lookup"><span data-stu-id="23b67-113">Remarks</span></span>  
 <span data-ttu-id="23b67-114">Prima di chiamare il [DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) metodo, è possibile usare il `DefineImportType` metodo per creare un riferimento di tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.</span><span class="sxs-lookup"><span data-stu-id="23b67-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23b67-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23b67-115">Requirements</span></span>  
 <span data-ttu-id="23b67-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23b67-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23b67-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="23b67-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23b67-118">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="23b67-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23b67-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23b67-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b67-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b67-120">See also</span></span>

- [<span data-ttu-id="23b67-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="23b67-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="23b67-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="23b67-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
