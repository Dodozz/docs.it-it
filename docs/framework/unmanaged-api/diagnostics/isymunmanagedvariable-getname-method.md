---
title: Metodo ISymUnmanagedVariable::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e863640e18ca64de084331327e0fa39468b54b60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176241"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="86cd8-102">Metodo ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="86cd8-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="86cd8-103">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="86cd8-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86cd8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86cd8-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86cd8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86cd8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="86cd8-106">[in] La lunghezza del buffer che il `pcchName` punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="86cd8-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="86cd8-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="86cd8-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="86cd8-108">[out] Buffer che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="86cd8-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86cd8-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="86cd8-109">Return Value</span></span>  
 <span data-ttu-id="86cd8-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="86cd8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86cd8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86cd8-111">Requirements</span></span>  
 <span data-ttu-id="86cd8-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="86cd8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86cd8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86cd8-113">See also</span></span>

- [<span data-ttu-id="86cd8-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="86cd8-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
