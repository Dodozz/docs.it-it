---
title: Metodo ICorRuntimeHost::CurrentDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb5ff5300a7fd2577e602b3077dd816cf7dfbe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936916"
---
# <a name="icorruntimehostcurrentdomain-method"></a>Metodo ICorRuntimeHost::CurrentDomain
Ottiene un puntatore di interfaccia di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio caricato sul thread corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAppDomain`  
 [out] Un puntatore di tipo <xref:System.AppDomain?displayProperty=nameWithType> che rappresenta il dominio del thread corrente dell'applicazione. Il puntatore è tipizzato `IUnknown`, in modo che i chiamanti in genere consigliabile chiamare `QueryInterface` per ottenere un puntatore di tipo <xref:System._AppDomain>.  
  
## <a name="return-value"></a>Valore restituito  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'operazione è riuscita.|  
|S_FALSE|Impossibile completare l'operazione.|  
|E_FAIL|Si è verificato un errore irreversibile sconosciuto. Se un metodo viene restituito E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo. Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vedere anche

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Interfaccia ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
