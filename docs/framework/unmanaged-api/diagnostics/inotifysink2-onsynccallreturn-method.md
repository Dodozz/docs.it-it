---
title: Metodo INotifySink2::OnSyncCallReturn
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0adc6ec1db3f12d1850bb6ff9a01d5b6cc5f90c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940348"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="a80f2-102">Metodo INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="a80f2-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="a80f2-103">Viene richiamato quando una chiamata termina.</span><span class="sxs-lookup"><span data-stu-id="a80f2-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a80f2-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a80f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a80f2-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="a80f2-106">[in] ID della restituito dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a80f2-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="a80f2-107">Visualizzare [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="a80f2-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="a80f2-108">[in] Chiamare il buffer.</span><span class="sxs-lookup"><span data-stu-id="a80f2-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="a80f2-109">[in] Dimensioni del buffer di chiamate, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="a80f2-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a80f2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a80f2-110">Return Value</span></span>  
 <span data-ttu-id="a80f2-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a80f2-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80f2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a80f2-112">Requirements</span></span>  
 <span data-ttu-id="a80f2-113">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a80f2-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80f2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a80f2-114">See also</span></span>

- [<span data-ttu-id="a80f2-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="a80f2-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="a80f2-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="a80f2-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="a80f2-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="a80f2-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
