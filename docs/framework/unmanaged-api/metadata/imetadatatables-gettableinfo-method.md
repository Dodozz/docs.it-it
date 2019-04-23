---
title: Metodo IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82c88c75d5799134d8c683c91e28f956743b84ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194513"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="566be-102">Metodo IMetaDataTables::GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="566be-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="566be-103">Ottiene il nome, dimensioni delle righe, numero di righe, il numero di colonne e indice della colonna chiave della tabella specificata.</span><span class="sxs-lookup"><span data-stu-id="566be-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="566be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="566be-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="566be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="566be-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="566be-106">[in] L'identificatore della tabella le cui proprietà da restituire.</span><span class="sxs-lookup"><span data-stu-id="566be-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="566be-107">[out] Un puntatore alla dimensione, espressa in byte, di una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="566be-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="566be-108">[out] Puntatore al numero di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="566be-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="566be-109">[out] Puntatore al numero di colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="566be-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="566be-110">[out] Un puntatore all'indice della colonna chiave, oppure -1 se la tabella non dispone di alcuna colonna chiave.</span><span class="sxs-lookup"><span data-stu-id="566be-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="566be-111">[out] Un puntatore a un puntatore al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="566be-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="566be-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="566be-112">Requirements</span></span>  
 <span data-ttu-id="566be-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="566be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="566be-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="566be-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="566be-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="566be-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="566be-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="566be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="566be-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="566be-117">See also</span></span>

- [<span data-ttu-id="566be-118">Interfaccia IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="566be-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="566be-119">Interfaccia IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="566be-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
