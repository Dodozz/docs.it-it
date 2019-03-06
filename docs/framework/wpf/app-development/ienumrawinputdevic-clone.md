---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355019"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea un altro enumeratore del dispositivo di input non elaborato con lo stesso stato dell'enumeratore corrente per eseguire l'iterazione dello stesso elenco.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppenum`  
  
 [out] Indirizzo della variabile di output che riceve la [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) puntatore a interfaccia. Se il metodo ha esito negativo, il valore di questa variabile di output non è definito.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 HRESULT: Questo metodo supporta i valori restituiti standard E_INVALIDARG ed E_OUTOFMEMORY E_UNEXPECTED.  
  
## <a name="remarks"></a>Note  
 Questo metodo rende possibile registrare un punto nella sequenza di enumerazione per tornare a quel punto in un secondo momento. Il chiamante deve rilasciare il nuovo enumeratore separatamente dal primo enumeratore.
