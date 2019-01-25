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
# <a name="imetadataimportgetmethodprops-method"></a>Metodo IMetaDataImport::GetMethodProps
Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
#### <a name="parameters"></a>Parametri  
 `mb`  
 [in] Il token MethodDef che rappresenta il metodo per restituire i metadati.  
  
 `pClass`  
 [out] Un puntatore a un token TypeDef che rappresenta il tipo che implementa il metodo.  
  
 `szMethod`  
 [out] Un puntatore a un buffer che contiene il nome del metodo.  
  
 `cchMethod`  
 [in] La dimensione richiesta del `szMethod`.  
  
 `pchMethod`  
 [out] Un puntatore alla dimensione in caratteri wide di `szMethod`, o in caso di troncamento, il numero effettivo di caratteri "wide" nel nome del metodo.  
  
 `pdwAttr`  
 [out] Puntatore a nessun flag associato al metodo.  
  
 `ppvSigBlob`  
 [out] Un puntatore per la firma binaria dei metadati del metodo.  
  
 `pcbSigBlob`  
 [out] Un puntatore alla dimensione in byte del `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Un puntatore all'indirizzo virtuale relativo del metodo.  
  
 `pdwImplFlags`  
 [out] Puntatore ai flag di implementazione del metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
