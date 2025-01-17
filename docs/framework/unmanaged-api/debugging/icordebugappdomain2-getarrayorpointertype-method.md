---
title: Metodo ICorDebugAppDomain2::GetArrayOrPointerType
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc38ef23a8b802d674a7a6dc4807371e432f73d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593511"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>Metodo ICorDebugAppDomain2::GetArrayOrPointerType
Ottiene una matrice di tipo specificato, o un puntatore o riferimento al tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `elementType`  
 [in] Valore dell'enumerazione CorElementType che specifica il tipo nativo sottostante (una matrice, un puntatore o riferimento) deve essere creato.  
  
 `nRank`  
 [in] La classificazione (vale a dire, numero di dimensioni) della matrice. Questo valore deve essere 0 se `elementType` specifica un tipo puntatore o riferimento.  
  
 `pTypeArg`  
 [in] Un puntatore a un oggetto ICorDebugType che rappresenta il tipo di matrice, puntatore o riferimento deve essere creato.  
  
 `ppType`  
 [out] Un puntatore all'indirizzo di un `ICorDebugType` il tipo di oggetto che rappresenta la matrice costruita, tipo di puntatore o riferimento.  
  
## <a name="remarks"></a>Note  
 Il valore di *elementType* deve essere uno dei seguenti:  
  
- ELEMENT_TYPE_PTR  
  
- ELEMENT_TYPE_BYREF  
  
- ELEMENT_TYPE_ARRAY o ELEMENT_TYPE_SZARRAY  
  
 Se il valore di *elementType* rappresenti ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR *nDimensioni* deve essere zero.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
