---
title: Metodo ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ec6e25452a40ae67570badde8a883878d103f95
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187402"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="30b2e-102">Metodo ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="30b2e-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="30b2e-103">Restituisce il token di metadati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="30b2e-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30b2e-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30b2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30b2e-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="30b2e-106">[out] Un puntatore a un `mdMethodDef` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="30b2e-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30b2e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30b2e-107">Return Value</span></span>  
 <span data-ttu-id="30b2e-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="30b2e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30b2e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30b2e-109">Requirements</span></span>  
 <span data-ttu-id="30b2e-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30b2e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b2e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b2e-111">See also</span></span>

- [<span data-ttu-id="30b2e-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="30b2e-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
