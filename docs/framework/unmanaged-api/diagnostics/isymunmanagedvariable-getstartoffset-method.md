---
title: Metodo ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a30dff869075a201a669d1e703bc003b011fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797515"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="bf6ef-102">Metodo ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="bf6ef-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="bf6ef-103">Ottiene l'offset di inizio di questa variabile all'interno di relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="bf6ef-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="bf6ef-104">Se si tratta di una variabile locale all'interno di un ambito, l'offset iniziale rientrerà negli offset definiti per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="bf6ef-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf6ef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf6ef-105">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf6ef-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bf6ef-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bf6ef-107">[out] Un puntatore a un `ULONG32` che riceve l'offset iniziale.</span><span class="sxs-lookup"><span data-stu-id="bf6ef-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf6ef-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bf6ef-108">Return Value</span></span>  
 <span data-ttu-id="bf6ef-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bf6ef-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf6ef-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf6ef-110">Requirements</span></span>  
 <span data-ttu-id="bf6ef-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bf6ef-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6ef-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf6ef-112">See also</span></span>

- [<span data-ttu-id="bf6ef-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="bf6ef-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="bf6ef-114">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="bf6ef-114">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)
