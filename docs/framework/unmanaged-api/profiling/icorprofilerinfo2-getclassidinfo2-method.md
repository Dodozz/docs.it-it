---
title: Metodo ICorProfilerInfo2::GetClassIDInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b98746be189e211572e5517aac1f06825973b39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779782"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>Metodo ICorProfilerInfo2::GetClassIDInfo2
Ottiene il modulo padre e i metadati token per aprirla definizione generica della classe specificata, il `ClassID` della relativa classe padre e il `ClassID` per ogni argomento di tipo, se presente, della classe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 [in] ID della classe per la quale verranno recuperate le informazioni.  
  
 `pModuleId`  
 [out] Puntatore all'ID del modulo padre per la definizione generica aperta della classe specificata.  
  
 `pTypeDefToken`  
 [out] Puntatore al token di metadati per la definizione generica aperta della classe specificata.  
  
 `pParentClassId`  
 [out] Puntatore all'ID della classe padre.  
  
 `cNumTypeArgs`  
 [in] Dimensione della matrice `typeArgs`.  
  
 `pcNumTypeArgs`  
 [out] Puntatore al numero complessivo di elementi disponibili.  
  
 `typeArgs`  
 [out] Matrice di valori `ClassID`, ognuno dei quali rappresenta l'ID di un argomento di tipo della classe. Quando il metodo restituisce i risultati, `typeArgs` conterrà alcuni o tutti i valori `ClassID` disponibili.  
  
## <a name="remarks"></a>Note  
 Il `GetClassIDInfo2` metodo è simile al [ICorProfilerInfo:: GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) metodo, ma `GetClassIDInfo2` Ottiene informazioni aggiuntive su un tipo generico.  
  
 Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) per ottenere un [metadati](../../../../docs/framework/unmanaged-api/metadata/index.md) interfaccia per un determinato modulo. Il token di metadati restituito al percorso a cui viene fatto riferimento tramite `pTypeDefToken` può quindi essere usato per accedere ai metadati per la classe.  
  
 Dopo il completamento del metodo `GetClassIDInfo2`, è necessario verificare che il buffer `typeArgs` sia abbastanza grande per contenere tutti i valori `ClassID`. A tale scopo, confrontare il valore a cui punta `pcNumTypeArgs` con il valore del parametro `cNumTypeArgs`. Se `pcNumTypeArgs` punta a un valore maggiore di `cNumTypeArgs`, allocare un buffer `typeArgs` più grande, aggiornare `cNumTypeArgs` con la nuova dimensione e chiamare nuovamente `GetClassIDInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetClassIDInfo2` con un buffer `typeArgs` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer `typeArgs` sul valore restituito in `pcNumTypeArgs` e chiamare nuovamente `GetClassIDInfo2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
