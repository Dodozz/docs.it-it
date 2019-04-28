---
title: Metodo ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca7aee79b5b8c3d58b4beb8f1ff886a7d55afab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782707"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="75605-102">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="75605-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="75605-103">Restituisce il nome di dominio completo o l'indirizzo IPv4 del computer di destinazione per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="75605-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="75605-104">IPV6 non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="75605-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75605-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75605-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="75605-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="75605-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="75605-107">[in] Le dimensioni, in caratteri, del `szHostName` buffer.</span><span class="sxs-lookup"><span data-stu-id="75605-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="75605-108">Se il parametro è 0 (zero), `szHostName` deve essere Null.</span><span class="sxs-lookup"><span data-stu-id="75605-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="75605-109">[out] Numero di caratteri, incluso un terminatore Null, nel nome host o nell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="75605-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="75605-110">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="75605-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="75605-111">[out] Buffer contenente il nome host o l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="75605-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75605-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="75605-112">Return Value</span></span>  
 <span data-ttu-id="75605-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="75605-113">S_OK</span></span>  
 <span data-ttu-id="75605-114">Il nome host o l'indirizzo IP è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="75605-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="75605-115">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="75605-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="75605-116">Impossibile restituire il nome host o l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="75605-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75605-117">Note</span><span class="sxs-lookup"><span data-stu-id="75605-117">Remarks</span></span>  
 <span data-ttu-id="75605-118">Questo metodo viene implementato dal writer del debugger.</span><span class="sxs-lookup"><span data-stu-id="75605-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="75605-119">Deve seguire il paradigma di chiamate multiple: Alla prima chiamata, il chiamante passa null sia `cchHostName` e `szHostName`, e `pcchHostName` restituisce le dimensioni del buffer richiesto.</span><span class="sxs-lookup"><span data-stu-id="75605-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="75605-120">Nella seconda chiamata, la dimensione che è stata restituita in precedenza viene passata a `cchHostName` e un buffer di dimensioni appropriate viene passato a `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="75605-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75605-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75605-121">Requirements</span></span>  
 <span data-ttu-id="75605-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75605-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75605-123">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="75605-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="75605-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75605-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75605-125">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="75605-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75605-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75605-126">See also</span></span>

- [<span data-ttu-id="75605-127">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="75605-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="75605-128">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="75605-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
