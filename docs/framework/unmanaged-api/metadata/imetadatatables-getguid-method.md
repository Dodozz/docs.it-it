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
ms.openlocfilehash: 94df2192b0b02f6cf0e068cb554afc6e7f9ec74d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486940"
---
# <a name="imetadatatablesgetguid-method"></a>Metodo IMetaDataTables::GetGuid
Ottiene un GUID della riga in corrispondenza dell'indice specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ixGuid`  
 [in] L'indice della riga da cui ottenere il GUID.  
  
 `ppGuid`  
 [out] Un puntatore a un puntatore al GUID.  
  
## <a name="remarks"></a>Note  
 Non è consigliabile l'uso di questo metodo, perché non restituire risultati coerenti. Per informazioni sulla tabella di GUID, vedere la documentazione di Common Language Infrastructure (CLI), in particolare "Partition II: Metadata Definition and Semantics". La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataTables](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
