---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11a75ca89a3537ce8ee72e8ba24401800eacff20
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939737"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="09e6d-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="09e6d-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="09e6d-103">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="09e6d-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09e6d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="09e6d-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="09e6d-106">[in] Il token di metadati dei metodi.</span><span class="sxs-lookup"><span data-stu-id="09e6d-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="09e6d-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="09e6d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09e6d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09e6d-108">Return Value</span></span>  
 <span data-ttu-id="09e6d-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="09e6d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e6d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09e6d-110">Requirements</span></span>  
 <span data-ttu-id="09e6d-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="09e6d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e6d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09e6d-112">See also</span></span>

- [<span data-ttu-id="09e6d-113">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="09e6d-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
