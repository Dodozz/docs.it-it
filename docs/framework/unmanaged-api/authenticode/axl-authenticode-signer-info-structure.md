---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 024837870aade6b0beb76fe758a571b15fd14d59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948977"
---
# <a name="axlauthenticodesignerinfo-structure"></a>Struttura AXL_AUTHENTICODE_SIGNER_INFO
Definisce le informazioni su chi ha apposto la firma Authenticode.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`cbSize`|Dimensione della struttura.|  
|`dwError`|Codice di errore.|  
|`algHash`|Algoritmo hash.|  
|`pwszHash`|Hash.|  
|`pwszDescription`|Descrizione.|  
|`pwszDescriptionUrl`|URL della descrizione.|  
|`pChainContext`|Contesto della catena del firmatario. Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.|  
  
## <a name="see-also"></a>Vedere anche

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
