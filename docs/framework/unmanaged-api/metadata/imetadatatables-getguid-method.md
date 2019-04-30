---
title: Metodo IMetaDataTables::GetGuid
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70a22e7e37a0fd88bcb8673846f5313d35971a15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992251"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="cd3b3-102">Metodo IMetaDataTables::GetGuid</span><span class="sxs-lookup"><span data-stu-id="cd3b3-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="cd3b3-103">Ottiene un GUID della riga in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="cd3b3-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd3b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd3b3-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd3b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd3b3-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="cd3b3-106">[in] L'indice della riga da cui ottenere il GUID.</span><span class="sxs-lookup"><span data-stu-id="cd3b3-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="cd3b3-107">[out] Un puntatore a un puntatore al GUID.</span><span class="sxs-lookup"><span data-stu-id="cd3b3-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd3b3-108">Note</span><span class="sxs-lookup"><span data-stu-id="cd3b3-108">Remarks</span></span>  
 <span data-ttu-id="cd3b3-109">Non è consigliabile l'uso di questo metodo, perché non restituire risultati coerenti.</span><span class="sxs-lookup"><span data-stu-id="cd3b3-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="cd3b3-110">Per informazioni sulla tabella di GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="cd3b3-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="cd3b3-111">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="cd3b3-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd3b3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd3b3-112">Requirements</span></span>  
 <span data-ttu-id="cd3b3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd3b3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd3b3-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cd3b3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd3b3-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cd3b3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cd3b3-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd3b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3b3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd3b3-117">See also</span></span>

- [<span data-ttu-id="cd3b3-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="cd3b3-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cd3b3-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="cd3b3-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
