---
title: Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f20039318d6e1230ccc0fbd203fc44686806bb2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604470"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="12080-102">Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="12080-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="12080-103">Visualizzare [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="12080-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12080-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12080-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12080-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12080-105">Parameters</span></span>  
  
|<span data-ttu-id="12080-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="12080-106">Parameter</span></span>|<span data-ttu-id="12080-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12080-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="12080-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="12080-108">Return Value</span></span>  
 <span data-ttu-id="12080-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="12080-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12080-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12080-110">Requirements</span></span>  
 <span data-ttu-id="12080-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12080-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12080-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12080-112">See also</span></span>
- [<span data-ttu-id="12080-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="12080-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
