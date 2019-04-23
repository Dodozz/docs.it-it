---
title: Metodo ICorDebugCode::GetEnCRemapSequencePoints
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 785defaa69609fc30852be9996531e6063586ceb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977743"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="5bf96-102">Metodo ICorDebugCode::GetEnCRemapSequencePoints</span><span class="sxs-lookup"><span data-stu-id="5bf96-102">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>
<span data-ttu-id="5bf96-103">Questo metodo non è implementato nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bf96-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf96-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bf96-104">Syntax</span></span>  
  
```  
HRESULT GetEnCRemapSequencePoints(  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        ULONG32 offsets[]  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bf96-105">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bf96-105">See also</span></span>
