---
title: Metodo INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf36b9e09f5e9eeb28930a6adc48426927a60e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145691"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="847c4-102">Metodo INotifySink2::OnSyncCallOut</span><span class="sxs-lookup"><span data-stu-id="847c4-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="847c4-103">Viene richiamato quando una chiamata non è più valido.</span><span class="sxs-lookup"><span data-stu-id="847c4-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="847c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="847c4-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="847c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="847c4-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="847c4-106">[in] ID della chiamata che non è più valido. Visualizzare [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="847c4-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="847c4-107">[out] Chiamare il buffer.</span><span class="sxs-lookup"><span data-stu-id="847c4-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="847c4-108">[out] Dimensioni del buffer di chiamate, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="847c4-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="847c4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="847c4-109">Return Value</span></span>  
 <span data-ttu-id="847c4-110">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="847c4-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="847c4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="847c4-111">Requirements</span></span>  
 <span data-ttu-id="847c4-112">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="847c4-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="847c4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="847c4-113">See also</span></span>

- [<span data-ttu-id="847c4-114">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="847c4-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="847c4-115">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="847c4-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="847c4-116">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="847c4-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
