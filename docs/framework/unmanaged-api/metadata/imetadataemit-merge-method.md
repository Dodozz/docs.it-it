---
title: Metodo IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ebc86ad9c1f84156e7e228c1ddf3fe7b86b7e60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576265"
---
# <a name="imetadataemitmerge-method"></a>Metodo IMetaDataEmit::Merge
Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pImport`  
 [in] Un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) oggetto che identifica l'ambito importato da unire.  
  
 `pIMap`  
 [in] Un puntatore a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) oggetto che specifica il nuovo mapping dei token.  
  
 `pHandleer`  
 [in] Un puntatore a un [IUnknown](/cpp/atl/iunknown) oggetto che specifica gli errori.  
  
## <a name="remarks"></a>Note  
 Chiamare [MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) per attivare l'unione dei metadati in un singolo ambito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
