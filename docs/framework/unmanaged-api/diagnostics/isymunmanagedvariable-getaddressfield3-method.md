---
title: Metodo ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8b03b96c8cab43046d109d0dd11ae135cb70c9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797592"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="2c3f5-102">Metodo ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="2c3f5-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="2c3f5-103">Ottiene il terzo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="2c3f5-104">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c3f5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c3f5-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c3f5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c3f5-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="2c3f5-107">[out] Un puntatore a un `ULONG32` che riceve il terzo campo dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c3f5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c3f5-108">Return Value</span></span>  
 <span data-ttu-id="2c3f5-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2c3f5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c3f5-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c3f5-110">Requirements</span></span>  
 <span data-ttu-id="2c3f5-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2c3f5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c3f5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c3f5-112">See also</span></span>

- [<span data-ttu-id="2c3f5-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="2c3f5-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="2c3f5-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="2c3f5-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="2c3f5-115">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="2c3f5-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="2c3f5-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="2c3f5-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
