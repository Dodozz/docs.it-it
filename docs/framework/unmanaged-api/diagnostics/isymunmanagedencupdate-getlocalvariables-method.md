---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44b30d571e6786ad840308a21fb185270c6e5ae7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509870"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="1831d-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="1831d-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="1831d-103">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1831d-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1831d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1831d-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1831d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1831d-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="1831d-106">[in] Il token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="1831d-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="1831d-107">[in] Oggetto `ULONG` che indica le dimensioni del `rgLocals` parametro.</span><span class="sxs-lookup"><span data-stu-id="1831d-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="1831d-108">[out] La matrice restituita di [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) istanze.</span><span class="sxs-lookup"><span data-stu-id="1831d-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1831d-109">[out] Un puntatore a un `ULONG` che riceve le dimensioni del `rgLocals` buffer necessario per contenere variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1831d-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1831d-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1831d-110">Return Value</span></span>  
 <span data-ttu-id="1831d-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1831d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1831d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1831d-112">Requirements</span></span>  
 <span data-ttu-id="1831d-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1831d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1831d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1831d-114">See also</span></span>
- [<span data-ttu-id="1831d-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="1831d-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
