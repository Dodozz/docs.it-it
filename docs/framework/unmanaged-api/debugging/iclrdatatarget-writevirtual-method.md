---
title: Metodo ICLRDataTarget::WriteVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 540f9d1a765ff46235f3c3d62f5da4a00b8ab85a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745480"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="b7943-102">Metodo ICLRDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="b7943-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="b7943-103">Scrive i dati dal buffer specificato per l'indirizzo di memoria virtuale specificato.</span><span class="sxs-lookup"><span data-stu-id="b7943-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7943-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7943-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7943-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7943-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b7943-106">[in] CLRDATA_ADDRESS che archivia l'indirizzo di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="b7943-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b7943-107">[in] Un puntatore a un buffer che archivia i dati da scrivere.</span><span class="sxs-lookup"><span data-stu-id="b7943-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="b7943-108">[in] Il numero di byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="b7943-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="b7943-109">[out] Puntatore al numero effettivo di byte che sono state scritte.</span><span class="sxs-lookup"><span data-stu-id="b7943-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7943-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7943-110">Requirements</span></span>  
 <span data-ttu-id="b7943-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7943-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7943-112">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b7943-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b7943-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7943-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7943-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7943-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7943-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7943-115">See also</span></span>
- [<span data-ttu-id="b7943-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="b7943-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
