---
title: Metodo ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 622e57aedf6c49e95dc2d7e40ba598361b3e6a26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753453"
---
# <a name="importtypes-method"></a>Metodo ImportTypes
Avvia l'importazione di tipi da ogni ambito importato attraverso [metodo ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly da importare.  
  
 `FileToken`  
 ID del file da importare da.  
  
 `dwScope`  
 Ambito in base zero da importare.  
  
 `phEnum`  
 Riceve l'handle di enumeratore per i tipi in questo ambito.  
  
 `ppImportScope`  
 Facoltativamente, riceve [interfaccia di IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia.  
  
 `pdwCountOfTypes`  
 Facoltativamente, riceve il numero di tipi nell'ambito indicato.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [Alink (API)](../../../../docs/framework/unmanaged-api/alink/index.md)
