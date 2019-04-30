---
title: Enumerazione CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045630"
---
# <a name="cormethodsemanticsattr-enumeration"></a>Enumerazione CorMethodSemanticsAttr
Contiene valori che descrivono la relazione tra un metodo e una proprietà o evento associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`msSetter`|Specifica che il metodo è un `set` della funzione di accesso per una proprietà.|  
|`msGetter`|Specifica che il metodo è un `get` della funzione di accesso per una proprietà.|  
|`msOther`|Specifica che il metodo ha una relazione a una proprietà o un evento diverso da quelli definiti qui.|  
|`msAddOn`|Specifica che il metodo aggiunge i metodi del gestore per un evento.|  
|`msRemoveOn`|Specifica il metodo che rimuove i metodi gestore per un evento.|  
|`msFire`|Specifica che il metodo genera un evento.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
