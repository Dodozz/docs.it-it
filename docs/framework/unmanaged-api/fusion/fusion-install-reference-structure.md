---
title: Struttura FUSION_INSTALL_REFERENCE
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936487"
---
# <a name="fusioninstallreference-structure"></a>Struttura FUSION_INSTALL_REFERENCE
Rappresenta un riferimento da un'applicazione a un assembly che l'applicazione è installata nella global assembly cache.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbSize`|Le dimensioni della struttura in byte.|  
|`dwFlags`|Riservato per un'estendibilità futura. Questo valore deve essere 0 (zero).|  
|`guidScheme`|L'entità che aggiunge il riferimento. Questo campo può avere uno dei valori seguenti:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: L'assembly viene fatto riferimento da un'applicazione che è stata installata utilizzando il programma di installazione di Microsoft Windows. Il `szIdentifier` campo è impostato su `MSI`e il `szNonCanonicalData` campo è impostato su `Windows Installer`. Questo schema viene usato per gli assembly side-by-side di Windows.<br />-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: L'assembly viene fatto riferimento da un'applicazione che viene visualizzato nei **Aggiungi/Rimuovi programmi** interfaccia. Il `szIdentifier` campo fornisce il token che registra l'applicazione con il **Aggiungi/Rimuovi programmi** interfaccia.<br />-   FUSION_REFCOUNT_FILEPATH_GUID: L'assembly viene fatto riferimento da un'applicazione che è rappresentata da un file nel file system. Il `szIdentifier` campo fornisce il percorso del file.<br />-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: L'assembly viene fatto riferimento da un'applicazione che è rappresentata solo da una stringa opaca. Il `szIdentifier` campo fornisce questa stringa opaca. Global assembly cache non verifica l'esistenza di riferimenti opachi quando si rimuove questo valore.<br />-   FUSION_REFCOUNT_OSINSTALL_GUID: Questo valore è riservato.|  
|`szIdentifier`|Una stringa univoca che identifica l'applicazione che ha installato l'assembly nella global assembly cache. Il valore dipende dal valore della `guidScheme` campo.|  
|`szNonCanonicalData`|Stringa che viene riconosciuta solo dall'entità che aggiunge il riferimento. Global assembly cache archivia la stringa, ma non lo utilizza.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [Global Assembly Cache](../../../../docs/framework/app-domains/gac.md)
