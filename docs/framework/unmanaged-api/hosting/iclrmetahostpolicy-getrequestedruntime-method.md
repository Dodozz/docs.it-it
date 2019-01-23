---
title: Metodo ICLRMetaHostPolicy::GetRequestedRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9820ddff742e66743d6ad6b2a8abab0bd8b4e09e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555908"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>Metodo ICLRMetaHostPolicy::GetRequestedRuntime
Fornisce un'interfaccia a una versione preferita di Common Language Runtime (CLR) in base a criteri di hosting, un assembly gestito, una stringa di versione e un flusso di configurazione. Questo metodo non è effettivamente caricare o attivare il CLR, si limita a restituire il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia che rappresenta il risultato dei criteri. Questo metodo sostituisce le [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), e [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) metodi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetRequestedRuntime(  
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,  
    [in]  LPCWSTR pwzBinary,  
    [in]  IStream *pCfgStream,  
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,  
    [in, out]  DWORD *pcchVersion,  
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,  
    [in, out]  DWORD *pcchImageVersion,  
    [out] DWORD *pdwConfigFlags,  
    [in]  REFIID  riid  
    [out, iid_is(riid), retval] LPVOID *ppRuntime);  
```  
  
#### <a name="parameters"></a>Parametri  
  
|nome|Descrizione|  
|----------|-----------------|  
|`dwPolicyFlags`|[in] Obbligatorio. Specifica un membro del [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumerazione, che rappresenta un criterio di binding e un numero qualsiasi di modificatori. Gli unici criteri attualmente disponibili sono [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).<br /><br /> I modificatori includono [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), e [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).|  
|`pwzBinary`|[in] Facoltativo. Specifica il percorso del file di assembly.|  
|`pCfgStream`|[in] Facoltativo. Specifica il file di configurazione come oggetto <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|  
|`pwzVersion`|[in, out] Facoltativo. Specifica o restituisce la versione di CLR preferita da caricare.|  
|`pcchVersion`|[in, out] Obbligatorio. Specifica la dimensione prevista di `pwzVersion` come input per evitare sovraccarichi del buffer. Se `pwzVersion` è null, `pcchVersion` contiene le dimensioni previste di `pwzVersion` quando `GetRequestedRuntime` restituisce un valore, per consentire la preallocazione. In caso contrario, `pcchVersion` contiene il numero di caratteri scritti in `pwzVersion`.|  
|`pwzImageVersion`|[out] Facoltativo. Quando `GetRequestedRuntime` restituito, contiene la versione di CLR corrispondente per il [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia restituita.|  
|`pcchImageVersion`|[in, out] Facoltativo. Specifica la dimensione di `pwzImageVersion` come input per evitare sovraccarichi del buffer. Se `pwzImageVersion` è null, `pcchImageVersion` contiene la dimensione richiesta di `pwzImageVersion` quando viene restituito `GetRequestedRuntime`, per consentire la preallocazione.|  
|`pdwConfigFlags`|[out] Facoltativo. Se `GetRequestedRuntime` Usa un file di configurazione durante il processo di associazione, al momento della restituzione `pdwConfigFlags` contiene una [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) valore che indica se la [ \<avvio >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) elemento presenta il `useLegacyV2RuntimeActivationPolicy` attributo set e il valore dell'attributo. Si applicano i [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) mask `pdwConfigFlags` per ottenere i valori attinenti a `useLegacyV2RuntimeActivationPolicy`.|  
|`riid`|[in] Specifica l'identificatore di interfaccia IID_ICLRRuntimeInfo per l'oggetto richiesto [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.|  
|`ppRuntime`|[out] Quando `GetRequestedRuntime` restituito, contiene un puntatore all'oggetto corrispondente [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaccia.|  
  
## <a name="remarks"></a>Note  
 Quando questo metodo ha esito positivo presenta l'effetto collaterale di combinare flag aggiuntivi con i flag di avvio predefiniti correnti dell'interfaccia di runtime restituita, se e solo se uno o più degli elementi seguenti esiste nel flusso di configurazione all'interno della sezione `<configuration><runtime>`:  
  
-   `<gcServer enabled="true"/>` comporta l'impostazione di `STARTUP_SERVER_GC`.  
  
-   `<etwEnable enabled="true"/>` comporta l'impostazione di `STARTUP_ETW`.  
  
-   `<appDomainResourceMonitoring enabled="true"/>` comporta l'impostazione di `STARTUP_ARM`.  
  
 Il valore `STARTUP_FLAGS` predefinito risultante è la combinazione OR bit per bit dei valori che vengono impostati dall'elenco precedente con i flag di avvio predefiniti.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|E_POINTER|`pwzVersion` non è null e `pcchVersion` è null.<br /><br /> -oppure-<br /><br /> `pwzImageVersion` non è null e `pcchImageVersion` è null.|  
|E_INVALIDARG|`dwPolicyFlags` non specifica `METAHOST_POLICY_HIGHCOMPAT`.|  
|ERROR_INSUFFICIENT_BUFFER|La memoria allocata a `pwzVerison` è inadeguata.<br /><br /> -oppure-<br /><br /> La memoria allocata a `pwzImageVerison` è inadeguata.|  
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` include METAHOST_POLICY_APPLY_UPGRADE_POLICY e `pwzVersion` e `pcchVersion` sono null.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)
- [Interfacce di hosting CLR aggiunte in .NET Framework 4 e 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
