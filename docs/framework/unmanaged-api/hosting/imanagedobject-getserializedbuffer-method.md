---
title: Metodo IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7930e993640e1ae88ce65b6c2025a5b62a0d0999
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502462"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a>Metodo IManagedObject::GetSerializedBuffer
Ottiene la rappresentazione di stringa dell'oggetto gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pBSTR`  
 [out] Puntatore a una stringa che rappresenta l'oggetto serializzato.  
  
## <a name="remarks"></a>Note  
 Il `GetSerializedBuffer` metodo serializza l'oggetto che può essere sottoposta a marshalling al client.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IManagedObject](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
