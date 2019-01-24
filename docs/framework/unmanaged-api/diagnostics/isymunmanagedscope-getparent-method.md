---
title: Metodo ISymUnmanagedScope::GetParent
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 606b9b496380a00ab9615ab7fe7febdc749b3ee2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663531"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="f9d6f-102">Metodo ISymUnmanagedScope::GetParent</span><span class="sxs-lookup"><span data-stu-id="f9d6f-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="f9d6f-103">Ottiene l'ambito padre di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="f9d6f-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9d6f-104">Syntax</span></span>  
  
```  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9d6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9d6f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f9d6f-106">[out] Un puntatore al valore restituito [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9d6f-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9d6f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f9d6f-107">Return Value</span></span>  
 <span data-ttu-id="f9d6f-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f9d6f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d6f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9d6f-109">Requirements</span></span>  
 <span data-ttu-id="f9d6f-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f9d6f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d6f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9d6f-111">See also</span></span>
- [<span data-ttu-id="f9d6f-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="f9d6f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="f9d6f-113">Metodo GetChildren</span><span class="sxs-lookup"><span data-stu-id="f9d6f-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
